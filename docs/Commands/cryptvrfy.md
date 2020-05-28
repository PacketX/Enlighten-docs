cryptvrfy
===========

檢查`OpenSSL`相關參數是否合法。

Help
---------

```
$ cryptvrfy help
Usage: cryptvrfy [GROUP] [OPTION...]
Verify SSL and cryptography related parameters

Verify curve list
    curve-list
        --curve-list,  -c    curve list to verify

Verify SSL ciphers
    ciphers
        --ciphers,     -c    ciphers to verify

Verify SSL version
    ssl-version
        --ssl-version,  -s    SSL version string to verify
        --json,         -j    output in json format

Print the help
    help

Report bugs to <tubear.chen@packetx.biz>.
```

Example 1 驗證橢圓曲線
-----------

```
$ cryptvrfy curve-list --curve-list auto
$ echo $?
0

$ cryptvrfy curve-list --curve-list secp256r1
$ echo $?
0

$ cryptvrfy curve-list --curve-list dummy
$ echo $?
2
```

執行完後檢查回傳值：`echo $?`，`0`為正確，`2`為錯誤。

Example 2 驗證SSL密碼套件
-------------

```
$ cryptvrfy ciphers --ciphers 'ALL:!EXPORT:!LOW:!aNULL:!eNULL:!SSLv2' 
$ echo $?
0

$ cryptvrfy ciphers --ciphers dummy
$ echo $?
2
```

執行完後檢查回傳值：`echo $?`，`0`為正確，`2`為錯誤。

Example 3 驗證SSL版本
-----------

```
$ cryptvrfy ssl-version --ssl-version TLSv1.0
$ echo $?
0

$ cryptvrfy ssl-version --ssl-version dummy
$ echo $?
2
```

執行完後檢查回傳值：`echo $?`，`0`為正確，`2`為錯誤。
