enlighten
==============

`Enlighten`, proxy anything.

Help
-----------

```
$ enlighten help
Usage: enlighten [GROUP] [OPTION...]
Enlighten, proxy anything

Main Enlighten event loop
    core
        --configure,  -c    Configuration file, default: /usr/local/Enlighten/etc/enlighten/enlighten.json
        --test,       -t    Test configuration file

Print the help
    help

Report bugs to <tubear.chen@packetx.biz>.
```

Example 1 Run with configuration file
-------------

```
$ sudo enlighten core --configure /usr/local/Enlighten/etc/enlighten/enlighten.json
```

Root privileges is needed.

Example 2 Run with default configuration file
-------------

```
$ sudo enlighten core
```

Default: `${prefix}/etc/enlighten/enlighten.json`.

Example 3 Check configuration content
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

`echo $?`, `0` is ok and `1` is error.

Message: "`'BindNethook' interface 'pktx2' may not exist, but still working`" is still ok.

Configuration
-------------

See [Enlighten Configuration](Configuration/Enlighten-Configuration.md).
