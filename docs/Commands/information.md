information
==============

`Enlighten`的組態、參數，第三方相依性資訊。

Example 1 輸出資訊
-------------

```
$ information 
Prefix: /usr/local/Enlighten
Bug report address: tubear.chen@packetx.biz
Versions:
    library: 1.0.28-alpha
    enlighten: 1.0.1-alpha
    nethook: 1.0.9-alpha
    listening: 1.0.20-alpha
    www: 0.0.1-dev
    neigh: 1.0.0-stable
    shm: 1.0.1-stable
    cleaner: 1.0.2-stable
    daemonize: 1.0.0-stable
    intf: 1.0.2-stable
    tracking: 1.0.0-stable
    control: 1.0.5-stable
    information: 1.0.6-stable
    config: 1.0.3-stable
    kerctl: 1.0.0-stable
System types:
    endianness: Little Endian
    machine: x86_64
    cache line: 64 bytes
    platform: POC
    configured timestamp: 2020-04-22-21:19:16
C Compiler:
    C preprocessor: gcc -E
    C compiler: gcc
    CFLAGS: -g -O2 -finline-functions
    LDFLAGS: -Wl,-R/usr/local/ssl/lib
    LIBS: 
    WARN_CFLAGS: -Wall -Werror=switch -Werror=nonnull -Werror=unused-result 
    EXTRA_CFLAG: -static -std=gnu11 
    EXTRA_LDFLAG: -static 
    EXTRA_LIBS: -lm -lpthread -lrt -ldl -lgcc_s 
GO Compiler:
    Go compiler: go
    Go compiler version: 1.14.1
    Go OS: linux
    Go arch: amd64
Git:
    branch: develop
    latest git commit hash: 5f9b9f2cbda16d0987061c0efa07e3061be40c2c
Enlighten default settings:
    default configuration filename: /usr/local/Enlighten/etc/enlighten/enlighten.json(found)
    process ID lock filename: /usr/local/Enlighten/run/enlighten.pid
Listening default settings:
    trusted certificate filename: /usr/local/Enlighten/etc/trusted_cert.crt(found)
Www default settings:
    default configuration filename: /usr/local/Enlighten/etc/www/www.json(found)
    process ID lock filename: /usr/local/Enlighten/run/www.pid
Kerctl default settings:
    default configuration filename: /usr/local/Enlighten/etc/kerctl/kerctl.json(found)
Commands:
    enlighten: /usr/local/Enlighten/sbin/enlighten(found)
    nethook: /usr/local/Enlighten/libexec/nethook(found)
    listening: /usr/local/Enlighten/libexec/listening(found)
    www: /usr/local/Enlighten/sbin/www(found)
Aid Commands:
    neigh: /usr/local/Enlighten/libexec/neigh(found)
    shm: /usr/local/Enlighten/libexec/shm(found)
    cleaner: /usr/local/Enlighten/libexec/cleaner(found)
    daemonize: /usr/local/Enlighten/libexec/daemonize(found)
    intf: /usr/local/Enlighten/libexec/intf(found)
    tracking: /usr/local/Enlighten/libexec/tracking(found)
    control: /usr/local/Enlighten/libexec/control(found)
    information: /usr/local/Enlighten/libexec/information(found)
    config: /usr/local/Enlighten/libexec/config(found)
    kerctl: /usr/local/Enlighten/libexec/kerctl(found)
    cryptvrfy: /usr/local/Enlighten/libexec/cryptvrfy(found)
System Commands:
    ip: /sbin/ip(found)
    ethtool: /sbin/ethtool(found)
    route: /sbin/route(found)
    sysctl: /sbin/sysctl(found)
    sed: /bin/sed(found)
Configuration:
    shared memory hash table key size: 288 bytes
    ARP shared memory hash table size: 512 entries
    NDP shared memory hash table size: 512 entries
    tracking table entries: 98304 entries
    jemalloc:
        Version: 5.2.1
        CFLAGS: -I/usr/local/include -include jemalloc/jemalloc.h
        LDFLAGS: -L/usr/local/lib -Wl,-R/usr/local/lib
        LIBS: -ljemalloc -ljemalloc_pic -ldl
    OpenSSL:
        Header Version: 1.1.1d  10 Sep 2019
        Library Version: 1.1.1d  10 Sep 2019
        Compiled CFLAGS: -fPIC -pthread -m64 -Wa,--noexecstack -Wall -O3 -DOPENSSL_USE_NODELETE -DL_ENDIAN -DOPENSSL_PIC -DOPENSSL_CPUID_OBJ -DOPENSSL_IA32_SSE2 -DOPENSSL_BN_ASM_MONT -DOPENSSL_BN_ASM_MONT5 -DOPENSSL_BN_ASM_GF2m -DSHA1_ASM -DSHA256_ASM -DSHA512_ASM -DKECCAK1600_ASM -DRC4_ASM -DMD5_ASM -DVPAES_ASM -DGHASH_ASM -DECP_NISTZ256_ASM -DX25519_ASM -DPOLY1305_ASM -DNDEBUG
        CFLAGS: -I/usr/local/ssl/include
        LDFLAGS: -L/usr/local/ssl/lib -Wl,-R/usr/local/ssl/lib
        LIBS: -lssl -lcrypto -ldl
    libevent:
        Version: 2.1.11-stable
        CFLAGS: -I/usr/local/include
        LDFLAGS: -L/usr/local/lib -Wl,-R/usr/local/lib
        LIBS: -levent -levent_extra -levent_openssl -levent_pthreads
    json-c:
        Version: 0.13.1
        CFLAGS: -I/usr/local/include
        LDFLAGS: -L/usr/local/lib -Wl,-R/usr/local/lib
        LIBS: -ljson-c
    libpcap:
        Version: 1.9.1 (with TPACKET_V2)
        CFLAGS: -I/usr/local/include
        LDFLAGS: -L/usr/local/lib -Wl,-R/usr/local/lib
        LIBS: -lpcap
```
