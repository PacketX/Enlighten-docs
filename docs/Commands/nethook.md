nethook
===========

封包處理程式，決定哪些封包要進處理資料階段，哪些直接透通。

Help
-------------

```
$ nethook help
Usage: nethook [GROUP] [OPTION...]
Nethook, raw packet handler

Main Nethook event loop
    core
        --configure,  -c    Configuration file
        --test,       -t    Test configuration file

Print the help
    help

Report bugs to <tubear.chen@packetx.biz>.
```

Example 1 指定設定檔執行
-------------

```
$ sudo nethook core --configure /usr/local/Enlighten/etc/nethook/nh_pktx0.json
```

`nethook`必須使用root權限。

Example 2 檢查設定檔是否錯誤
-------------

```
$ nethook core --configure /usr/local/Enlighten/etc/nethook/nh_pktx0.json --test
$ echo $?
0

$ nethook core --configure /usr/local/Enlighten/etc/nethook/nh_pktx0.json --test
nethook:pktx0: 'PacketModule' is not pass validation
$ echo $?
1
```

執行完後檢查回傳值：`echo $?`，`0`為正確，`1`為錯誤。

Configuration
-------------

See [Nethook Configuration](Configuration/Nethook-Configuration.md)。
