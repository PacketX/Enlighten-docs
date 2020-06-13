nethook
===========

Nethook, raw packet handler.

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

Example 1 Run with configuration file
-------------

```
$ sudo nethook core --configure /usr/local/Enlighten/etc/nethook/nh_pktx0.json
```

Root privileges is needed.

Example 2 Check configuration content
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

`echo $?`, `0` is ok and `1` is error.

Configuration
-------------

See [Nethook Configuration](Configuration/Nethook-Configuration.md).
