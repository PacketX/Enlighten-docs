kerctl
=============

Configure `kernel` parameters at runtime.

Help
--------

```
$ kerctl
Usage: kerctl [GROUP] [OPTION...]
Configure kernel parameters at runtime

Set kernel state
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
$ sudo kerctl core --configure /usr/local/Enlighten/etc/kerctl/kerctl.json
```

Root privileges is needed.

Example 2 Run with default configuration file
-------------

```
$ sudo kerctl core
```

Default: `${prefix}/etc/kerctl/kerctl.json`.

Example 3 Check configuration content
-------------

```
$ kerctl core --test
$ echo $?
0

$ kerctl core --test
$ echo $?
1
```

`echo $?`, `0` is ok and `1` is error.

Configuration
-------------

See [kerctl Configuration](../Configuration/kerctl-Configuration.md).
