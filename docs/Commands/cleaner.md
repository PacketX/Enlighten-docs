cleaner
============

Clean something expired.

Help
-------------

```
$ cleaner help
Usage: cleaner [GROUP] [OPTION...]
Clean something expired

Clean expired certificate
    certificate
        --path,  -p    Certificate path to clean

Clean expired tracking table entry
    tracking
        --name,  -n    Tracking table name to clean

Clear all named shared memory that belong to Enlighten
    shm

Print the help
    help

Report bugs to <tubear.chen@packetx.biz>.
```

Example 1 Clean expired certificate
------------

```
$ sudo cleaner certificate --path /usr/local/Enlighten/var/cache/forged-cert/pktx0-3129
17 certificate is removed
```

Root privileges is needed.

Example 2 Clean expired tracking table entry
-----------

```
$ sudo cleaner tracking --name ST1
42 entry is removed
```

Root privileges is needed.

Example 3 Clear all named shared memory that belong to `Enlighten`
-----------

```
$ sudo cleaner shm
```

Root privileges is needed. Command is same as:

```
$ sudo shm clear
```
