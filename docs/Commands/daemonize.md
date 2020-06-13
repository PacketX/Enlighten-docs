daemonize
=============

Make process daemonize. Command will be found in `$PATH` or in absolute path.

Help
---------

```
$ daemonize
Usage: daemonize command [parameters]...
```

Example 1
-----------

```
$ daemonize ping 127.0.0.1

$ ps aux|grep ping
enlight+  10354  0.0  0.0 128464  1900 ?        Ss   19:01   0:00 /usr/bin/ping 127.0.0.1
```

Example 2
-----------

```
$ daemonize `which ping` 127.0.0.1

$ ps aux|grep ping
enlight+  10369  0.0  0.0 128464  1888 ?        Ss   19:04   0:00 /usr/bin/ping 127.0.0.1
```
