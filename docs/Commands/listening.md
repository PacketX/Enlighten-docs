listening
==============

Listening, socket proxy.

Help
-----------

```
$ listening help
Usage: listening [GROUP] [OPTION...]
Listening, socket proxy

Main Listening event loop
    core
        --configure,  -c    Configuration file
        --test,       -t    Test configuration file

Print the help
    help

Report bugs to <tubear.chen@packetx.biz>.
```

Example 1 Run with configuration file
-------------

```
$ sudo listening core --configure /usr/local/Enlighten/etc/listening/ls_3128.json
```

Root privileges is needed.

Example 2 Check configuration content
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

`echo $?`, `0` is ok and `1` is error.

Configuration
-------------

See [Listening Configuration](Configuration/Listening-Configuration.md).
