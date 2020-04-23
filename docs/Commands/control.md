control
===========

管理`Enlighten`啟動、關閉、重新啟動、log輪替...等動作。

Help
-----------

```
$ control help
Usage: control [GROUP] [OPTION...]
Control the Enlighten

Start the Enlighten
    start

Stop the Enlighten
    stop
        --pid,   -p    Enlighten process ID
        --wait,  -w    waiting seconds, default: 10 seconds

Stop the Enlighten immediately
    quit
        --pid,   -p    Enlighten process ID
        --wait,  -w    waiting seconds, default: 10 seconds

Restart the Enlighten
    restart
        --pid,   -p    Enlighten process ID
        --wait,  -w    waiting seconds, default: 10 seconds

Force stop the Enlighten
    kill

Rotate the Enlighten log
    rotate-log
        --pid,   -p    Enlighten process ID

Reload the Enlighten
    reload
        --pid,   -p    Enlighten process ID

Print running process information
    pid-list

Print the help
    help

Report bugs to <tubear.chen@packetx.biz>.
```

Example 1 啟動`Enlighten`
-----------

```
$ sudo control start
'enlighten' is starting...

$ sudo control start
control: 'enlighten' is running
```

啟動必須使用root權限。

Example 2 停止`Enlighten`
-----------

```
$ sudo control stop
control: 'enlighten' is stopping...
control: 'enlighten' is stopped

$ sudo control stop
control: 'enlighten' is not running
```

停止必須使用root權限。

Example 3 馬上停止`Enlighten`
-------------

```
$ sudo control quit
control: 'enlighten' is quitting...
control: 'enlighten' is quitted

$ sudo control quit
control: 'enlighten' is not running
```

馬上停止必須使用root權限。

Example 4 重新啟動`Enlighten`
-------------

```
$ sudo control restart
control: 'enlighten' is stopping...
control: 'enlighten' is stopped
'enlighten' is starting...
```

重新啟動停止必須使用root權限；效果等同於：

```
$ sudo control stop
$ sudo control start
```

Example 5 強迫停止`Enlighten`
------------

```
$ sudo control kill
```

強迫停止必須使用root權限。

Example 6 要求log輪替
------------

```
$ sudo control rotate-log
```

要求log輪替必須使用root權限。

Example 7 重新讀取設定檔
------------

```
$ sudo control reload
```

重新讀取設定檔必須使用root權限；重新讀取只能重讀部分內容。

Example 8 列出程序資訊
------------

```
$ sudo control pid-list
      Name        PID        Location   Position   CPU List
 Enlighten      80636               -       Core        0-3
       www     106880               -          -        0-3
   Nethook      80742           pktx2     Master        0-3
   Nethook      80743           pktx1     Master        0-3
   Nethook      80817           pktx1     Worker        0-3
   Nethook      80818           pktx2     Worker        0-3
 Listening      80825      pktx2:4438     Master        0-3
 Listening      80826      pktx1:8443     Master        0-3
 Listening      80827      pktx1:8443     Worker          0
 Listening      80828      pktx2:4438     Worker          2
 Listening      80829      pktx1:8443     Worker          1
 Listening      80830      pktx2:4438     Worker          3
```

列出程序資訊必須使用root權限。
