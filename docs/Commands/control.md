control
===========

Control the `Enlighten` and `www`.

Help
-----------

```
$ control help
Usage: control [GROUP] [OPTION...]
Control the Enlighten and www

Start the Enlighten
    start
        --configure,  -c    Configuration file, default: /usr/local/Enlighten/etc/enlighten/enlighten.json

Stop the Enlighten
    stop
        --pid,        -p    Enlighten process ID
        --wait,       -w    Waiting seconds, default: 10 seconds

Quit the Enlighten
    quit
        --pid,        -p    Enlighten process ID
        --wait,       -w    Waiting seconds, default: 10 seconds

Restart the Enlighten
    restart
        --pid,        -p    Enlighten process ID
        --wait,       -w    Waiting seconds, default: 10 seconds
        --configure,  -c    Configuration file, default: /usr/local/Enlighten/etc/enlighten/enlighten.json

Force stop the Enlighten
    kill

Rotate the Enlighten log
    rotate-log
        --pid,        -p    Enlighten process ID

Reload the Enlighten
    reload
        --pid,        -p    Enlighten process ID

Stop the Enlighten workers gracefully
    graceful-quit
        --pid,        -p    Enlighten process ID

Start the www
    start-www

Stop the www
    stop-www
        --pid,        -p    Www process ID
        --wait,       -w    Waiting seconds, default: 10 seconds

Restart the www
    restart-www
        --pid,        -p    Www process ID
        --wait,       -w    Waiting seconds, default: 10 seconds

Force stop the www
    kill-www

Print running process information
    proc-list
        --json,       -j    Output in json format

Print the help
    help

Report bugs to <tubear.chen@packetx.biz>.
```

Example 1 Start `Enlighten`
-----------

```
$ sudo control start
'enlighten' is starting...

$ sudo control start
control: 'enlighten' is running
```

Root privileges is needed.

Example 2 Stop `Enlighten`
-----------

```
$ sudo control stop
control: 'enlighten' is stopping...
control: 'enlighten' is stopped

$ sudo control stop
control: 'enlighten' is not running
```

Root privileges is needed.

Example 3 Quit `Enlighten`
-------------

```
$ sudo control quit
control: 'enlighten' is quitting...
control: 'enlighten' is quitted

$ sudo control quit
control: 'enlighten' is not running
```

Root privileges is needed.

Example 4 Restart `Enlighten`
-------------

```
$ sudo control restart
control: 'enlighten' is stopping...
control: 'enlighten' is stopped
'enlighten' is starting...
```

Root privileges is needed. Command is same as:

```
$ sudo control stop
$ sudo control start
```

Example 5 Force stop `Enlighten`
------------

```
$ sudo control kill
```

Root privileges is needed.

Example 6 Log rotation
------------

```
$ sudo control rotate-log
```

Root privileges is needed.

Example 7 Reload
------------

```
$ sudo control reload
```

Root privileges is needed.

Example 8 Graceful shutdown `Enlighten`
------------

```
$ sudo control graceful-quit
```

Root privileges is needed.

Example 9 Start `www`
-----------

```
$ sudo control start-www
'www' is starting...

$ sudo control start-www
control: 'www' is running
```

Root privileges is needed.

Example 10 Stop `www`
-----------

```
$ sudo control stop-www
control: 'www' is stopping...
control: 'www' is stopped

$ sudo control stop-www
control: 'www' is not running
```

Root privileges is needed.

Example 11 Restart `www`
-------------

```
$ sudo control restart-www
control: 'www' is stopping...
control: 'www' is stopped
'www' is starting...
```

Root privileges is needed. Command is same as:

```
$ sudo control stop-www
$ sudo control start-www
```

Example 12 Force stop `www`
------------

```
$ sudo control kill-www
```

Root privileges is needed.

Example 13 List processes information
------------

```
$ sudo control proc-list
      Name        PID        Location   Position   CPU-List
 Enlighten      17166               -       Core        0-3
       www      17142               -          -        0-3
   Nethook      17272           pktx2     Master        0-3
   Nethook      17273           pktx1     Master        0-3
   Nethook      17347           pktx1     Worker        0-3
   Nethook      17350           pktx2     Worker        0-3
 Listening      17356      pktx1:8443     Master        0-3
 Listening      17357      pktx1:8443     Worker          0
 Listening      17358      pktx1:8443     Worker          1
```

Root privileges is needed.
