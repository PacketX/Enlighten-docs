shm
==============

Manipulate named shared memory which mounted under `/dev/shm`.

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

Example 1 List all named shared memory
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

Example 2 Destroy named shared memory
-------------

```
$ shm destroy --name ST2-Port
shm: destroying 'ST2-Port' was permission denied

$ sudo shm destroy --name ST2-Port
```

Root privileges is needed.

Example 3 Clear all named shared memory that belong to `Enlighten`
------------

```
$ sudo shm clear
```
