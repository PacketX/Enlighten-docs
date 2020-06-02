enlighten
==============

`Enlighten`核心程式；並不會背景執行，需要使用`daemonlize`或`control`。

Help
-----------

```
$ enlighten help
Usage: enlighten [GROUP] [OPTION...]
Enlighten, proxy anything

Main Enlighten event loop
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
$ sudo enlighten core --configure /usr/local/Enlighten/etc/enlighten/enlighten.json
```

`enlighten`必須使用root權限。

Example 2 使用預設設定檔執行
-------------

```
$ sudo enlighten core
```

預設設定檔位置為：`${prefix}/etc/enlighten`；如果`./configure`時指定`--prefix=/usr/local/Enlighten`的話，那預設檔案為：`/usr/local/Enlighten/etc/enlighten/enlighten.json`。

Example 3 檢查設定檔是否錯誤
-------------

```
$ enlighten core --test
'BindNethook' interface 'pktx2' may not exist, but still working
'BindNethook' interface 'pktx1' may not exist, but still working
$ echo $?
0

$ enlighten core --test
nethook:pktx2: 'LAN' is not pass validation
listening: 'BindNethook' interface 'pktx2' may not exist, but still working
listening:pktx2:4438: 'MaxCore' is not pass validation
listening: 'BindNethook' interface 'pktx1' may not exist, but still working
$ echo $?
1
```

執行完後檢查回傳值：`echo $?`，`0`為正確，`1`為錯誤；`'BindNethook' interface 'pktx2' may not exist, but still working`訊息為：因`listening`執行需要搭配`nethook`，所以只能預設猜測`listening`設定中對應的`nethook`設定是存在的。

Configuration
-------------

See [Enlighten Configuration](../UI/06.Enlighten-Configuration.md)。
