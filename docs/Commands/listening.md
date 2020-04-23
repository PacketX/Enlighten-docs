listening
==============

Socket處理程式，負責所有資料轉送、建立以及處理。

Help
-----------

```
$ listening help
Usage: listening [GROUP] [OPTION...]
Listening, socket proxy

Main Listening event loop
    core
        --configure,  -c    configuration file
        --test,       -t    test configuration file

Print the help
    help

Report bugs to <tubear.chen@packetx.biz>.
```

Example 1 指定設定檔執行
-------------

```
$ sudo listening core --configure /usr/local/Enlighten/etc/listening/ls_3128.json
```

`listening`必須使用root權限。

Example 2 檢查設定檔是否錯誤
-------------

```
$ listening core --configure /usr/local/Enlighten/etc/listening/ls_3128.json --test
$ echo $?
0

$ listening core --configure /usr/local/Enlighten/etc/listening/ls_3128.json --test
listening:pktx0:3128: 'MaxCore' is not pass validation
$ echo $?
1
```

執行完後檢查回傳值：`echo $?`，`0`為正確，`1`為錯誤。

Configuration
-------------

See [Listening Configuration](../UI/08.Listening-Configuration.md)。
