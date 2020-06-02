shm
==============

管理由`Enlighten`產生的有名共享記憶體。

Help
---------

```
$ shm help
Usage: shm [GROUP] [OPTION...]
Manipulate named shared memory which mounted under '/dev/shm'

List all named shared memory
    list

Destroy named shared memory
    destroy
        --name,  -n    Shared memory name to destroy

Clear all named shared memory that belong to Enlighten
    clear

Print the help
    help

Report bugs to <tubear.chen@packetx.biz>.
```

Example 1 列出全部共享記憶體資訊
---------------

```
$ shm list
                     Name       Size  Enlighten    Owner
                 ST2-Port   151.99MB        yes    10586
                   ST2-St   151.99MB        yes    10586
                NDP-Table   534.02KB        yes    10479
                ARP-Table   534.02KB        yes    10479
              Core-Shared     64.00B        yes    10479
```

Example 2 刪除共享記憶體
-------------

```
$ shm destroy --name ST2-Port
shm: destroying 'ST2-Port' was permission denied

$ sudo shm destroy --name ST2-Port
```

必須使用root權限才能操作刪除。

Example 3 刪除所有`Enlighten`產生的共享記憶體
------------

```
$ sudo shm clear
```
