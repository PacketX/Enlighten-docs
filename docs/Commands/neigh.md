neigh
===========

Manipulate the Enlighten ARP and NDP cache.

Help
-----------

```
$ neigh help
Usage: neigh [GROUP] [OPTION...]
Manipulate the Enlighten ARP and NDP cache

ARP table
    arp
        --list,     -l    List ARP table
        --add,      -a    Add an ARP entry, format: [IPv4 address]-[MAC address]@[interface]
        --delete,   -d    Delete an ARP entry, format: [IPv4 address]@[interface]
        --clear,    -c    Clear ARP table, format: *@[interface], [IPv4 address]@*, *@*
        --destroy,  -D    Destroy ARP table, warning: it will cause process segmentation fault that used

NDP table
    ndp
        --list,     -l    List NDP table
        --add,      -a    Add an NDP entry, format: [IPv6 address]-[MAC address]@[interface]
        --delete,   -d    Delete an NDP entry, format: [IPv6 address]@[interface]
        --clear,    -c    Clear NDP table, format: *@[interface], [IPv6 address]@*, *@*
        --destroy,  -D    Destroy NDP table, warning: it will cause process segmentation fault that used

Print the help
    help

Report bugs to <tubear.chen@packetx.biz>.
```

Example 1 Add an ARP entry and list
-----------

```
$ neigh arp --add 192.168.1.2-02:00:00:00:00:00@pktx2

$ neigh arp --list
      Interface      Proto addr           Hw addr
          pktx2     192.168.1.2 02:00:00:00:00:00
```

Example 2 Delete an ARP entry
-----------

```
$ neigh arp --delete 192.168.1.2@pktx2

$ neigh arp --delete 192.168.1.99@pktx2
neigh: '192.168.1.99@pktx2' is not found
```

Example 3 Clear ARP table
-----------

```
$ neigh arp --clear *@pktx2
'192.168.1.18@pktx2' is removed
'192.168.1.5@pktx2' is removed
'192.168.1.2@pktx2' is removed
3 entries are removed

$ neigh arp --clear 192.168.1.2@*
'192.168.1.2@pktx2' is removed
1 entry is removed

$ neigh arp --clear *@*
'192.168.1.18@pktx2' is removed
'192.168.1.5@pktx2' is removed
'192.168.1.2@pktx2' is removed
3 entries are removed
```

Example 4 Destroy ARP table
-----------

```
$ sudo neigh arp --destroy
neigh: warning: it will cause process(10693) segmentation fault that used
```

Command is same as:

```
$ sudo shm destroy --name ARP-Table
```

**Don't do this.**

Example 5 Add a NDP entry and list
-----------

```
$ neigh ndp --add fe80::1-02:00:00:00:00:00@pktx2

$ neigh ndp --list
      Interface                                     Link addr           Hw addr
          pktx2                                       fe80::1 02:00:00:00:00:00
```

Example 6 Delete a NDP entry
-----------

```
$ neigh ndp --delete fe80::1@pktx2

$ neigh ndp --delete fe80::99@pktx2
neigh: 'fe80::99@pktx2' is not found
```

Example 7 Clear NDP table
-----------

```
$ neigh ndp --clear *@pktx2
'fe80::12@pktx2' is removed
'fe80::8@pktx2' is removed
'fe80::1@pktx2' is removed
3 entries are removed

$ neigh ndp --clear fe80::8@*
'fe80::8@pktx2' is removed
1 entry is removed

$ neigh ndp --clear *@*
'fe80::12@pktx2' is removed
'fe80::8@pktx2' is removed
'fe80::1@pktx2' is removed
3 entries are removed
```

Example 8 Destroy NDP table
-----------

```
$ sudo neigh ndp --destroy
neigh: warning: it will cause process(10693) segmentation fault that used
```

Command is same as:

```
$ sudo shm destroy --name NDP-Table
```

**Don't do this.**
