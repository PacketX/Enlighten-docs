kerctl
=============

`sysctl`設定。

Help
--------

```
$ kerctl
Usage: kerctl [GROUP] [OPTION...]
Kerctl, configure kernel parameters at runtime

Set kernel state
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
$ sudo kerctl core --configure /usr/local/Enlighten/etc/kerctl/kerctl.json
```

`kerctl`必須使用root權限。

Example 2 使用預設設定檔執行
-------------

```
$ sudo kerctl core
```

預設設定檔位置為：`${prefix}/etc/kerctl`；如果`./configure`時指定`--prefix=/usr/local/Enlighten`的話，那預設檔案為：`/usr/local/Enlighten/etc/kerctl/kerctl.json`。

Example 3 檢查設定檔是否錯誤
-------------

```
$ kerctl core --test
$ echo $?
0

$ kerctl core --test
$ echo $?
1
```

執行完後檢查回傳值：`echo $?`，`0`為正確，`1`為錯誤。

Configuration
-------------

See [kerctl Configuration](../Configuration/kerctl-Configuration.md)。
