upelt
===========

更新`Enlighten`工具。

Help
---------

```
$ upelt
Usage: upelt [GROUP] [OPTION...]
Upgrade Enlighten system

Upgrade Enlighten
    core
        --file,      -f    Tarball of Enlighten, default: Enlighten-bin.tar.gz
        --force,     -F    Force upgrade, number of ignoration
        --override,  -O    Override upgrade, must append '--force [num]' option
        --verbose,   -V    Verbose output

Print the help
    help

Report bugs to <tubear.chen@packetx.biz>.
```

Example 1 更新`Enlighten`（失敗）
---------------

```
$ sudo upelt core --file Enlighten-bin.tar.gz
upelt: starting upgrade...
upelt: extracting tarball...
upelt: creating directory '/tmp/elt'
upelt: the build timestamp from current package '2020-06-02T22:38:35+0800'
upelt: the build timestamp from newer package '2020-06-02T21:43:08+0800'
upelt: the build timestamp of newer package is older than current package, increase '--force' option to ignore timestamp incorrection
upelt: cleaning up...
```

更新必須使用root權限。

Example 2 強迫更新`Enlighten`（成功）
-------------

```
$ sudo upelt core --file Enlighten-bin.tar.gz --force 1
upelt: starting upgrade...
upelt: extracting tarball...
upelt: creating directory '/tmp/elt'
upelt: the build timestamp from current package '2020-06-02T22:50:40+0800'
upelt: the build timestamp from newer package '2020-06-02T21:43:08+0800'
upelt: the build timestamp of newer package is older than current package(ignored)
upelt: recursive copying directories and files...
upelt: creating directory '/usr/local/Enlighten/bin/'...
upelt: creating directory '/usr/local/Enlighten/sbin/'...
upelt: creating directory '/usr/local/Enlighten/libexec/'...
upelt: creating directory '/usr/local/Enlighten/etc/geoip/country/'...
upelt: creating directory '/usr/local/Enlighten/etc/geoip2/country/'...
upelt: creating directory '/usr/local/Enlighten/etc/model/'...
upelt: creating directory '/usr/local/Enlighten/etc/cert/default/'...
upelt: creating directory '/usr/local/Enlighten/etc/rootCA/default/'...
upelt: changing files owner...
upelt: upgrade is done!
upelt: cleaning up...
```

更新必須使用root權限，`--force`選項後的數字是可以接受幾次警告。

Example 3 複寫更新`Enlighten`（成功）
----------

```
$ sudo upelt core --file Enlighten-bin.tar.gz --override --force 1
upelt: starting upgrade...
upelt: override upgrade is dangerous(ignored)
upelt: extracting tarball...
upelt: changing files owner...
upelt: upgrade is done!
upelt: cleaning up...
```

複寫更新必須帶選項`--force`。
