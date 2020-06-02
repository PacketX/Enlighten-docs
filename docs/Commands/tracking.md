tracking
===========

`Enlighten`連線資訊表。

Help
------------

```
$ tracking help
Usage: tracking [GROUP] [OPTION...]
Manipulate the Enlighten connection tracking table

Tracking table to list
    list
        --name,  -n    Tracking table name

Print the help
    help

Report bugs to <tubear.chen@packetx.biz>.
```

Example 1 列出連線資訊表內容
------------

```
$ tracking list --name ST3
[0]
    IP version: 4
    Downstream IP address: 172.16.95.138
    Downstream port: 59100
    Upstream IP address: 31.13.87.36
    Upstream port: 443
    Bind port: 13229
    SNI: star-mini.c10r.facebook.com
    ALPN: no
    Create time: 2020-04-21T12:09:12.954000Z
    Last touch time: 2020-04-21T12:09:13.094467Z
    Downstream sent FIN: no
    Upstream sent FIN: no
    Got any RST: no

[1]
    IP version: 4
    Downstream IP address: 172.16.95.138
    Downstream port: 59160
    Upstream IP address: 1.1.1.1
    Upstream port: 443
    Bind port: 49763
    SNI: cloudflare-dns.com
    ALPN: no
    Create time: 2020-04-21T12:12:03.238939Z
    Last touch time: 2020-04-21T12:12:27.240536Z
    Downstream sent FIN: no
    Upstream sent FIN: yes
    Got any RST: yes

2 entries in table
```
