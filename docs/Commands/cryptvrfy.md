cryptvrfy
===========

Verify SSL and cryptography related parameters.

Help
---------

```
$ cryptvrfy help
Usage: cryptvrfy [GROUP] [OPTION...]
Verify SSL and cryptography related parameters

Verify curve list
    curve-list
        --curve-list,  -c    Curve list to verify

Verify SSL ciphers
    ciphers
        --ciphers,     -c    Ciphers to verify

Verify SSL version
    ssl-version
        --ssl-version,  -s    SSL version string to verify
        --json,         -j    Output in json format

Print the help
    help

Report bugs to <tubear.chen@packetx.biz>.
```

Example 1 Verify curve list
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

`echo $?`, `0` is ok and `2` is error.

Example 2 Verify SSL ciphers
-------------

```
$ cryptvrfy ciphers --ciphers 'ALL:!EXPORT:!LOW:!aNULL:!eNULL:!SSLv2' 
$ echo $?
0

$ cryptvrfy ciphers --ciphers dummy
$ echo $?
2
```

`echo $?`, `0` is ok and `2` is error.

Example 3 Verify SSL version
-----------

```
$ cryptvrfy ssl-version --ssl-version TLSv1.0
$ echo $?
0

$ cryptvrfy ssl-version --ssl-version dummy
$ echo $?
2
```

`echo $?`, `0` is ok and `2` is error.
