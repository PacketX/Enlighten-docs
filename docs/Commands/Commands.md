Commands
================

Core
--------------

<h3>enlighten</h3>

`Enlighten`核心，管理`Nethook`以及`Listening`。

<h3>nethook</h3>

負責處理原始(raw)封包接收、修改和發送。

<h3>listening</h3>

負責處理Socket Server程式。

<h3>www</h3>

`Enlighten`網頁伺服器，提供網頁資源和Restful API。

Aid
--------------

<h3>daemonlize</h3>

將程式以`daemon`方式執行；需以絕對路徑傳入。

<h3>shm</h3>

管理以`shm_open()`所產生的共享記憶體。

<h3>neigh</h3>

管理共享記憶體內的ARP和NDP Table。

<h3>intf</h3>

取得可用的介面資訊，根據`./configure`階段傳入的`--with-platform`決定。

<h3>tracking</h3>

管理共享記憶體內的`Tracking Table`。

<h3>information</h3>

資源資訊。

<h3>control</h3>

訊號控制`Enlighten`的工具。

<h3>cleaner</h3>

清除過期資訊。

<h3>config</h3>

產生`Enlighten`、`Nethook`、`Listening`和`Kerctl`預設config。

<h3>kerctl</h3>

`sysctl`同名指令。

<h3>cryptvrfy</h3>

驗證或取得`OpenSSL`相關可用參數。

<h3>upelt</h3>

更新`Enlighten`輔助工具。
