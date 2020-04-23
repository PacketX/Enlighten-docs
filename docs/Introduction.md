Introduction
===========

`Enlighten`有很多個子程式，其中兩個為主要程式: 處理封包的`Nethook`和處理Socket的`Listening`。

單獨執行一個程式並無作用，必須多個執行；例如一個`Nethook`和一個`Listening`可以達到一個最小的功能: `TCP Proxy`；`Nethook`和`Listening`各自有設定檔，意指幾個`Nethook`幾個`Listening`，就需要幾個設定檔。

How it works?
---------

```
                +-------------------------+
               /                         /|
              /        Enlighten        / |
             /                         /  +
            +-------------------------+  /
            |   0 1 2 3 4 5 6 7    #  | /
            +---+-+-----------+----+--+
                | |           |    +#######+[Mgmt]
                | |           |
                | |           | [Simulated Flow] +-----+
                | |           +------------------+ IDS |
   [Downstream] | | [Upstream]                   +-----+
>>>=============+ +=============>>>
```

`Downstream`: 靠近Client端（LAN），`Upstream`靠近Server端（WAN）；最少以一對物理介面為一個單位。

根據`Nethook`設定，命中的規則（例如TCP port 80）就會攔截下來送往`Enlighten`的`TCP/IP Stack`並紀錄一些資訊，其餘直接Inline到另一個介面。

`Listening`收到`Downstream`來的`TCP SYN`封包後就可以知道原本的連線資訊，並且向`Upstream`建起另一端連線。

<h3 id="Listening_Phases">Listening Phases</h3>

`Listening`完整的`Phases`以下:

1. `Access Phase`
2. `Connect Phase`
3. `SSL Peek Phase`
4. `SSL Connect Phase`
5. `SSL Accept Phase`
6. `Proxy Phase`
7. `Close Phase`

<h2 id="Instance">Instance</h2>

`Enlighten`目前支援以下幾種代理方式:

1. [`TCP Proxy`](#TCP_Proxy)
2. [`SSL Proxy`](#SSL_Proxy)
3. [`SSL Onload Proxy`](#SSL_Onload_Proxy)
4. [`SSL Offload Proxy`](#SSL_Offload_Proxy)

<!--
5. [`SSL IPS Proxy`](#SSL_IPS_Proxy)
-->

每一種代理方式都可以在同一時間獨立運行。

<h3 id="TCP_Proxy">TCP Proxy</h3>

`TCP Proxy`需要一個`Nethook`和一個`Listening`達成；需要的[`Listening Phases`](#Listening_Phases)為: `Access Phase`、`Connect Phase`、`Proxy Phase`以及`Close Phase`。

<h4>TCP Proxy Connection Lifetime</h4>

1. 收到`Downstream`的`TCP SYN`後與`Downstream`端建起連線，跳2。
2. `Access Phase`，檢查`Deny`列表，命中對`Downstream`端送`TCP Reset`並跳5；否則跳3。
3. `Connect Phase`，與`Upstream`建起連線，成功跳4；否則對`Downstream`端送`TCP Reset`並跳5。
4. `Proxy Phase`，代理`Dowstream`與`Upstream`資料，結束或失敗跳5。
5. `Close Phase`，如果`Upstream`有建立連線就關閉，關閉`Downstream`連線。

<h3 id="SSL_Proxy">SSL Proxy</h3>

`SSL Proxy`需要一個`Nethook`和一個`Listening`達成；需要的[`Listening Phases`](#Listening_Phases)為: `Access Phase`、`Connect Phase`、`SSL Peek Phase`、`SSL Connect Phase`、`SSL Accept Phase`、`Proxy Phase`以及`Close Phase`。

<h4>SSL Proxy Connection Lifetime</h4>

1. 收到`Downstream`的`TCP SYN`後與`Downstream`端建起連線，跳2。
2. `Access Phase`，檢查`Deny`列表，命中對`Downstream`端送`TCP Reset`並跳8；否則跳3。
3. `Connect Phase`，與`Upstream`建起連線，成功跳4；否則對`Downstream`端送`TCP Reset`並跳8。
4. `SSL Peek Phase`，等待`Downstream`端第一份資料，如果Timeout跳8；如果非`SSL`且有設定`DropNotSSL`則對`Downstream`端送`TCP Reset`並跳8，否則直接跳8；如果`SNI`命中`SSLDownstreamBlock`清單，對`Downstream`端送`TCP Reset`並跳8；如果`SNI`命中`SSLDownstreamBypass`清單直接跳7；其餘跳5。
5. `SSL Connect Phase`，嘗試與`Upstream`建立起`SSL`連線，如果Timeout或失敗，對`Downstream`端送`TCP Reset`並跳8；其餘跳6。
6. `SSL Accept Phase`，嘗試與`Downstream`建立起`SSL`連線，如果Timeout或失敗，對`Downstream`端送`TCP Reset`並跳8；其餘跳7。
7. `Proxy Phase`，代理`Dowstream`與`Upstream`資料，結束或失敗跳8。
8. `Close Phase`，如果`Upstream`有建立連線（包含`SSL/TLS`）就關閉，關閉`Downstream`連線（包含`SSL/TLS`）。

<h3 id="SSL_Offload_Proxy">SSL Offload Proxy</h3>

`SSL Offload Proxy`需要一個`Nethook`和一個`Listening`達成；需要的[`Listening Phases`](#Listening_Phases)為: `Access Phase`、`Connect Phase`、`SSL Peek Phase`、`SSL Accept Phase`、`Proxy Phase`以及`Close Phase`。

<h4>SSL Offload Proxy Connection Lifetime</h4>

1. 收到`Downstream`的`TCP SYN`後與`Downstream`端建起連線，跳2。
2. `Access Phase`，檢查`Deny`列表，命中對`Downstream`端送`TCP Reset`並跳7；否則跳3。
3. `Connect Phase`，與`Upstream`建起連線，成功跳4；否則對`Downstream`端送`TCP Reset`並跳7。
4. `SSL Peek Phase`，等待`Downstream`端第一份資料，如果Timeout跳7；如果非`SSL`且有設定`DropNotSSL`則對`Downstream`端送`TCP Reset`並跳7，否則直接跳7；如果`SNI`命中`SSLDownstreamBlock`清單，對`Downstream`端送`TCP Reset`並跳7；如果`SNI`命中`SSLDownstreamBypass`清單直接跳6；其餘跳5。
5. `SSL Accept Phase`，嘗試與`Downstream`建立起`SSL`連線，如果Timeout或失敗，對`Downstream`端送`TCP Reset`並跳7；其餘跳6。
6. `Proxy Phase`，代理`Dowstream`與`Upstream`資料，結束或失敗跳7。
7. `Close Phase`，如果`Upstream`有建立連線（包含`SSL/TLS`）就關閉，關閉`Downstream`連線（包含`SSL/TLS`）。

<h3 id="SSL_Onload_Proxy">SSL Onload Proxy</h3>

`SSL Onload Proxy`需要一個`Nethook`和一個`Listening`達成；需要的[`Listening Phases`](#Listening_Phases)為: `Access Phase`、`Connect Phase`、`SSL Connect Phase`、`Proxy Phase`以及`Close Phase`。

<h4>SSL Onload Proxy Connection Lifetime</h4>

1. 收到`Downstream`的`TCP SYN`後與`Downstream`端建起連線，跳2。
2. `Access Phase`，檢查`Deny`列表，命中對`Downstream`端送`TCP Reset`並跳6；否則跳3。
3. `Connect Phase`，與`Upstream`建起連線，成功跳4；否則對`Downstream`端送`TCP Reset`並跳6。
4. `SSL Connect Phase`，嘗試與`Upstream`建立起`SSL`連線，如果Timeout或失敗，對`Downstream`端送`TCP Reset`並跳6；其餘跳5。
5. `Proxy Phase`，代理`Dowstream`與`Upstream`資料，結束或失敗跳6。
6. `Close Phase`，如果`Upstream`有建立連線（包含`SSL/TLS`）就關閉，關閉`Downstream`連線（包含`SSL/TLS`）。

<!--
<h3 id="SSL_IPS_Proxy">SSL IPS Proxy</h3>

待補充。
-->

<h2 id="Template">Template</h2>

依照[`Instance`](#Instance)組合出不同的[`Template`](#Template)；實際的應用以[`Template`](#Template)為單位，設定以[`Instance`](#Instance)為單位，目前提供:

1. `Dynamic Certificate Forward`: [`TCP Proxy`](#TCP_Proxy) + [`SSL Proxy`](#SSL_Proxy)，最少使用兩個實體介面，需要一個`Nethook`和兩個`Listening`達成。
2. `Constant Certificate Forward`: [`SSL Offload Proxy`](#SSL_Offload_Proxy) + [`SSL Onload Proxy`](#SSL_Onload_Proxy)，最少使用四個實體介面，需要兩個`Nethook`和兩個`Listening`達成。
