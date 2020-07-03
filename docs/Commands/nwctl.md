nwctl
==========

Configure network settings.

Help
----------

```
$ nwctl
Usage: nwctl [GROUP] [OPTION...]
Configure network settings

Network configuration
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
$ sudo nwctl core --configure /usr/local/Enlighten/etc/nwctl/nwctl.json
```

Root privileges is needed.

Example 2 Run with default configuration file
-------------

```
$ sudo nwctl core
```

Default: `${prefix}/etc/nwctl/nwctl.json`.

Example 3 Check configuration content
-------------

```
$ nwctl core --test
$ echo $?
0

$ nwctl core --test
$ echo $?
1
```

`echo $?`, `0` is ok and `1` is error.

Configuration
-------------

See [nwctl Configuration](../Configuration/nwctl-Configuration.md).
