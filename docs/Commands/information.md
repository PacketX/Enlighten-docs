information
==============

Anything information about `Enlighten`.

Help
-----------

```
$ information
Usage: information [GROUP] [OPTION...]
Anything information about Enlighten

Requiring specific information
    core
        --prefix,         -p    Append prefix
        --bug,            -m    Bug report address
        --timestamp,      -t    Timestamp of build-time
        --pkg-version,    -v    Package version
        --libelt,         -l    Enlighten library version
        --sys-types,      -s    System types
        --compiler,       -C    C and Go compiler
        --git,            -g    Git information
        --defaults,       -d    Default files
        --commands,       -c    Enlighten commands
        --sys-commands,   -S    System command
        --extensions,     -e    Extensions
        --configuration,  -a    ./configure time values
        --3-party,        -3    Third party library information
        --json,           -j    Output in json format

Print the help
    help

Report bugs to <tubear.chen@packetx.biz>.
```

Example 1 Information
-------------

```
$ information core
Prefix: /usr/local/Enlighten
BugReportAddress: tubear.chen@packetx.biz
BuildTimestamp: 2020-06-24T00:14:53+0800
PackageVersion: 0.0.0
LibraryVersion: 1.1.12-stable
SystemTypes:
    Endianness: Little Endian
    Machine: x86_64
    CacheLine: 64
    Platform: POC
Compiler:
    CPreprocessor: ccache gcc -E
    CCompiler: ccache gcc
    CCFLAGS: -ggdb -g2 -O2 -finline-functions
    CLDFLAGS: -Wl,-R/usr/local/lib -Wl,-R/usr/local/ssl/lib
    CLIBS: 
    CWarningCFLAGS: -Wall -Wno-sign-compare -Wno-type-limits -Wno-missing-field-initializers -Wno-unused-parameter -Werror=switch -Werror=nonnull -Werror=unused-result
    CExtraCFLAGS: -static -std=gnu11 
    CExtraLDFLAGS: -static -Wl,--whole-archive,$(top_srcdir)/lib/.libs/libelt.a,--no-whole-archive 
    CExtraLIBS: -lm -lpthread -lrt -ldl -lgcc_s 
    GoCompiler: go
    GoCompilerVersion: 1.14.1
    GoOS: linux
    GoArch: amd64
Git:
    Branch: develop
    LatestHash: a1501b85c00001cfc6c11951c3d3a1bafbbf6cbc
Defaults:
    EnlightenConfigurationFilename: /usr/local/Enlighten/etc/enlighten/enlighten.json
    EnlightenConfigurationFilenameFound: true
    EnlightenPIDFilename: /usr/local/Enlighten/run/enlighten.pid
    ListeningTrustedCertificate: /usr/local/Enlighten/etc/trusted_cert.crt
    ListeningTrustedCertificateFound: true
    WwwConfigurationFilename: /usr/local/Enlighten/etc/www/www.json
    WwwConfigurationFilenameFound: true
    WwwPIDFilename: /usr/local/Enlighten/run/www.pid
    KerctlConfigurationFilename: /usr/local/Enlighten/etc/kerctl/kerctl.json
    KerctlConfigurationFilenameFound: true
Commands:
    enlighten:
        FullPath: /usr/local/Enlighten/sbin/enlighten
        Found: true
        Version: 1.0.5-stable
    nethook:
        FullPath: /usr/local/Enlighten/libexec/nethook
        Found: true
        Version: 1.0.15-stable
    listening:
        FullPath: /usr/local/Enlighten/libexec/listening
        Found: true
        Version: 1.0.27-stable
    www:
        FullPath: /usr/local/Enlighten/sbin/www
        Found: true
        Version: 1.0.1-stable
    neigh:
        FullPath: /usr/local/Enlighten/libexec/neigh
        Found: true
        Version: 1.0.0-stable
    shm:
        FullPath: /usr/local/Enlighten/libexec/shm
        Found: true
        Version: 1.0.1-stable
    cleaner:
        FullPath: /usr/local/Enlighten/libexec/cleaner
        Found: true
        Version: 1.0.2-stable
    daemonize:
        FullPath: /usr/local/Enlighten/libexec/daemonize
        Found: true
        Version: 1.0.0-stable
    intf:
        FullPath: /usr/local/Enlighten/libexec/intf
        Found: true
        Version: 1.0.2-stable
    tracking:
        FullPath: /usr/local/Enlighten/libexec/tracking
        Found: true
        Version: 1.0.0-stable
    control:
        FullPath: /usr/local/Enlighten/sbin/control
        Found: true
        Version: 1.0.8-stable
    information:
        FullPath: /usr/local/Enlighten/bin/information
        Found: true
        Version: 1.1.1-stable
    config:
        FullPath: /usr/local/Enlighten/bin/config
        Found: true
        Version: 1.0.5-stable
    kerctl:
        FullPath: /usr/local/Enlighten/libexec/kerctl
        Found: true
        Version: 1.0.2-stable
    cryptvrfy:
        FullPath: /usr/local/Enlighten/libexec/cryptvrfy
        Found: true
        Version: 1.0.0-stable
    upelt:
        FullPath: /usr/local/Enlighten/sbin/upelt
        Found: true
        Version: 1.0.2-stable
SystemCommands:
    ip:
        FullPath: /sbin/ip
        Found: true
    route:
        FullPath: /sbin/route
        Found: true
    sysctl:
        FullPath: /sbin/sysctl
        Found: true
    sed:
        FullPath: /bin/sed
        Found: true
    tar:
        FullPath: /bin/tar
        Found: true
    cp:
        FullPath: /bin/cp
        Found: true
    rm:
        FullPath: /bin/rm
        Found: true
    chown:
        FullPath: /bin/chown
        Found: true
Extensions:
    jemalloc: true
    128-BitInteger: true
Configuration:
    SharedMemoryHashTableKeySize: 288
    ARPTableSize: 512
    NDPTableSize: 512
    TrackingTableEntries: 98304
ThirdPartyLibrary:
    jemalloc:
        Version: 5.2.1
        CFLAGS: -I/usr/local/include -include jemalloc/jemalloc.h
        LDFLAGS: -L/usr/local/lib
        LIBS: -ljemalloc -ljemalloc_pic -ldl
    OpenSSL:
        HeaderVersion: 1.1.1g  21 Apr 2020
        LibraryVersion: 1.1.1g  21 Apr 2020
        CompilerFlags: gcc -fPIC -pthread -m64 -Wa,--noexecstack -Wall -O3 -DOPENSSL_USE_NODELETE -DL_ENDIAN -DOPENSSL_PIC -DOPENSSL_CPUID_OBJ -DOPENSSL_IA32_SSE2 -DOPENSSL_BN_ASM_MONT -DOPENSSL_BN_ASM_MONT5 -DOPENSSL_BN_ASM_GF2m -DSHA1_ASM -DSHA256_ASM -DSHA512_ASM -DKECCAK1600_ASM -DRC4_ASM -DMD5_ASM -DAESNI_ASM -DVPAES_ASM -DGHASH_ASM -DECP_NISTZ256_ASM -DX25519_ASM -DPOLY1305_ASM -DNDEBUG
        InternalDatatypeOptions:
            [0]: bn(64,64)
            [1]: rc4(16x,int)
            [2]: des(int)
            [3]: idea(int)
            [4]: blowfish(ptr)
        TargetBuildPlatform: linux-x86_64
        SSLVersion:
            [0]: SSLv3
            [1]: TLSv1.0
            [2]: TLSv1.1
            [3]: TLSv1.2
            [4]: TLSv1.3
        CFLAGS: -I/usr/local/ssl/include
        LDFLAGS: -L/usr/local/ssl/lib
        LIBS: -lssl -lcrypto -ldl
    Libevent:
        Version: 2.1.11-stable
        CFLAGS: -I/usr/local/include
        LDFLAGS: -L/usr/local/lib
        LIBS: -levent -levent_extra -levent_pthreads
    json-c:
        Version: 0.13.1
        CFLAGS: -I/usr/local/include
        LDFLAGS: -L/usr/local/lib
        LIBS: -ljson-c
    libpcap:
        Version: 1.9.1 (with TPACKET_V2)
        CFLAGS: -I/usr/local/include
        LDFLAGS: -L/usr/local/lib
        LIBS: -lpcap
```

Example 2 Specify information
-------------

```
$ information core --configuration --bug --json
{
   "BugReportAddress": "tubear.chen@packetx.biz",
   "Configuration": {
     "SharedMemoryHashTableKeySize": 288,
     "ARPTableSize": 512,
     "NDPTableSize": 512,
     "TrackingTableEntries": 98304
   }
 }
```
