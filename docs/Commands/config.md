config
=============

產生預設設定檔。

Help
----------

```
$ config
Usage: config [GROUP] [OPTION...]
Generate default configuration

Enlighten dynamic certificate forward
    enlighten-dynamic-certificate-forward
        --write,  -W    Write to file

Enlighten constant certificate forward
    enlighten-constant-certificate-forward
        --write,  -W    Write to file

Nethook dynamic certificate forward
    nethook-dynamic-certificate-forward
        --lan,    -l    LAN port
        --wan,    -w    WAN port
        --write,  -W    Write to file

Nethook SSL/TLS onload
    nethook-ssl-onload
        --lan,    -l    LAN port
        --wan,    -w    WAN port
        --write,  -W    Write to file

Nethook SSL/TLS offload
    nethook-ssl-offload
        --lan,    -l    LAN port
        --wan,    -w    WAN port
        --write,  -W    Write to file

Listening TCP forward
    listening-tcp-forward
        --write,  -W    Write to file

Listening SSL forward
    listening-ssl-forward
        --write,  -W    Write to file

Listening SSL onload
    listening-ssl-onload
        --write,  -W    Write to file

Listening SSL offload
    listening-ssl-offload
        --write,  -W    Write to file

Kerctl defaults
    kerctl
        --write,  -W    Write to file

Print the help
    help

Report bugs to <tubear.chen@packetx.biz>.
```

Example 1 產生`Listening`TCP forward預設設定檔
----------

```
$ config listening-tcp-forward
{
   "MessageLog": true,
   "ErrorLog": true,
   "SessionLog": true,
   "MaxCore": 4,
   "BindNethook": "pktx0",
   "BindPort": 3128,
   "Backlog": 65536,
   "MaxConcurrent": 98304,
   "TrackingTableName": "ST1",
   "TimerResolution": 0,
   "KeepAccept": false,
   "TCPNoDelay": true,
   "TCPKeepAlive": true,
   "ProxyBufferSize": 16384,
   "ConnectTimeout": 5000,
   "ConnectRetry": 3,
   "ProxyTimeout": 600000,
   "DownloadRate": 0,
   "UploadRate": 0,
   "JA3": false,
   "JA3S": false,
   "Deny": {
     "Tuple": [
     ]
   },
   "SSLDownstream": false,
   "SSLUpstream": false,
   "Sysloger": [
     {
       "DestinationIpv4Address": "127.0.0.1",
       "DestinationPort": 514,
       "AcceptingDownstream": false,
       "AcceptingDownstreamDenied": false,
       "AcceptedDownstream": false,
       "ConnectingUpstream": false,
       "ConnectingUpstreamTimeout": false,
       "ConnectingUpstreamReset": false,
       "ConnectedUpstream": false,
       "TCPEstablished": false,
       "ForwardingFinished": false,
       "SSLPeekClientHelloTimeout": false,
       "NotSSL": false,
       "JA3": false,
       "BlockSNI": false,
       "BypassSNI": false,
       "SSLConnectingUpstream": false,
       "SSLConnectingUpstreamTimeout": false,
       "SSLConnectingUpstreamFailed": false,
       "JA3S": false,
       "SSLConnectedUpstream": false,
       "SSLAcceptingDownstream": false,
       "SSLAcceptingDownstreamTimeout": false,
       "SSLAcceptingDownstreamFailed": false,
       "SSLAcceptedDownstream": false,
       "SSLEstablished": false,
       "SSLUpstreamCertificateChain": false,
       "SSLUpstreamCertificateAllInOne": false,
       "SSLUpstreamCertificateSerialNumber": false,
       "SSLUpstreamCertificateSignatureAlgorithm": false,
       "SSLUpstreamCertificateDateValidation": false,
       "SSLUpstreamCertificateSelfSigned": false,
       "SSLUpstreamCertificateIssuer": false,
       "SSLUpstreamCertificateSubject": false,
       "SSLUpstreamCertificatePublicKey": false,
       "SSLUpstreamCertificateExtensionKeyUsage": false,
       "SSLUpstreamCertificateExtensionSAN": false,
       "SSLUpstreamCertificateFingerprintSHA1": false,
       "SSLUpstreamCertificateFingerprintSHA256": false
     }
   ]
 }
```

Example 2 產生`Kerctl`預設設定檔並存檔
------------

```
$ config kerctl --write /usr/local/Enlighten/etc/kerctl/kerctl.json 
{
   "Kerctl": {
     "net.ipv4.tcp_tw_recycle": 1,
     "net.ipv4.tcp_tw_reuse": 1,
     "net.ipv4.tcp_timestamps": 0,
     "net.ipv4.tcp_syncookies": 1,
     "net.ipv4.tcp_fin_timeout": 5,
     "net.ipv4.tcp_max_syn_backlog": 65536,
     "net.core.netdev_max_backlog": 32768,
     "net.core.somaxconn": 32768,
     "net.ipv4.tcp_max_tw_buckets": 4096,
     "net.ipv4.tcp_syn_retries": 3,
     "net.ipv4.tcp_synack_retries": 3,
     "net.ipv4.tcp_retries1": 3,
     "net.ipv4.tcp_retries2": 10,
     "net.ipv4.tcp_keepalive_time": 1200,
     "net.ipv4.tcp_keepalive_intvl": 30,
     "net.ipv4.tcp_keepalive_probes": 3,
     "net.ipv6.conf.default.dad_transmits": 0,
     "net.ipv6.conf.all.dad_transmits": 0,
     "net.ipv6.conf.default.accept_dad": 0,
     "net.ipv6.conf.all.accept_dad": 0,
     "net.ipv6.conf.default.optimistic_dad": 0,
     "net.ipv6.conf.all.optimistic_dad": 0,
     "net.ipv6.conf.all.use_tempaddr": 0,
     "net.ipv6.conf.default.use_tempaddr": 0,
     "net.ipv4.tcp_max_orphans": 3276800,
     "net.core.wmem_default": 8388608,
     "net.core.rmem_default": 8388608,
     "net.core.rmem_max": 16777216,
     "net.core.wmem_max": 16777216,
     "net.core.optmem_max": 81920,
     "net.ipv4.tcp_sack": 1,
     "net.ipv4.tcp_fack": 1,
     "net.ipv4.tcp_dsack": 1,
     "net.ipv4.tcp_window_scaling": 1,
     "vm.overcommit_memory": 1,
     "vm.swappiness": 0,
     "net.ipv4.tcp_moderate_rcvbuf": 1,
     "net.ipv4.tcp_rfc1337": 0,
     "net.ipv4.tcp_no_metrics_save": 1,
     "fs.nr_open": 4999999,
     "fs.file-max": 5000000,
     "net.ipv4.tcp_early_retrans": 3,
     "net.ipv4.tcp_thin_linear_timeouts": 0,
     "net.ipv4.tcp_thin_dupack": 0,
     "net.ipv4.tcp_reordering": 3,
     "net.ipv4.tcp_mem": "786432 1048576 1572864",
     "net.ipv4.tcp_rmem": "32768 436600 873200",
     "net.ipv4.tcp_wmem": "32768 436600 873200",
     "net.ipv4.ip_local_port_range": "1024 65535"
   }
 }
```
