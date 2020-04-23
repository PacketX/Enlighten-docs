cleaner
============

清除一些過期的資訊。

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

Example 1 清除過期憑證
------------

```
$ sudo cleaner certificate --path /usr/local/Enlighten/var/cache/forged-cert/pktx0-3129
17 certificate is removed
```

清除過期憑證必須使用root權限。

Example 2 清除過期連線資訊
-----------

```
$ sudo cleaner tracking --name ST1
42 entry is removed
```

清除過期連線資訊必須使用root權限。

Example 3 刪除所有`Enlighten`產生的共享記憶體
-----------

```
$ sudo cleaner shm
```

刪除所有`Enlighten`產生的共享記憶體必須使用root權限；效果等同於：

```
$ sudo shm clear
```
