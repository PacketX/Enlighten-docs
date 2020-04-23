neigh
===========

管理`Enlighten`內部的ARP及NDP表。

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

Example 1 增加一筆ARP項目並列出
-----------

```
$ neigh arp --add 192.168.1.2-02:00:00:00:00:00@pktx2

$ neigh arp --list
      Interface      Proto addr           Hw addr
          pktx2     192.168.1.2 02:00:00:00:00:00
```

Example 2 刪除一筆ARP項目
-----------

```
$ neigh arp --delete 192.168.1.2@pktx2

$ neigh arp --delete 192.168.1.99@pktx2
neigh: '192.168.1.99@pktx2' is not found
```

Example 3 清空ARP表
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

第一種是根據介面清空；第二種是根據IP地址清空；第三種是完全清空。

Example 4 將ARP表從共享記憶體中刪除
-----------

```
$ sudo neigh arp --destroy
neigh: warning: it will cause process(10693) segmentation fault that used
```

該指定等同於：

```
$ sudo shm destroy --name ARP-Table
```

該操作會造成用該記憶體的程式損毀。

Example 5 增加一筆NDP項目並列出
-----------

```
$ neigh ndp --add fe80::1-02:00:00:00:00:00@pktx2

$ neigh ndp --list
      Interface                                     Link addr           Hw addr
          pktx2                                       fe80::1 02:00:00:00:00:00
```

Example 6 刪除一筆NDP項目
-----------

```
$ neigh ndp --delete fe80::1@pktx2

$ neigh ndp --delete fe80::99@pktx2
neigh: 'fe80::99@pktx2' is not found
```

Example 7 清空NDP表
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

第一種是根據介面清空；第二種是根據IP地址清空；第三種是完全清空。

Example 8 將NDP表從共享記憶體中刪除
-----------

```
$ sudo neigh ndp --destroy
neigh: warning: it will cause process(10693) segmentation fault that used
```

該指定等同於：

```
$ sudo shm destroy --name NDP-Table
```

該操作會造成用該記憶體的程式損毀。
