Listening Configuration
==========

Example
----------

```
{
    "MessageLog": true,
    "ErrorLog": true,
    "SessionLog": true,
    "SSLErrorLog": true,
    "MaxCore": 2,
    "BindNethook": "pktx0",
    "BindPort": 3129,
    "Backlog": 511,
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
    "JA3": true,
    "JA3S": true,
    "Deny": {
        "Tuple": [
            /* deny source from 192.168.1.2 to any 80 port */
            {
                "SourceIpAddress": [ "192.168.1.2", "192.168.2.0/24" ],
                "SourcePort": [],
                "DestinationIpAddress": [],
                "DestinationPort": [ 80 ]
            },
            /* deny all 81 port */
            {
                "SourceIpAddress": [],
                "SourcePort": [],
                "DestinationIpAddress": [],
                "DestinationPort": [ 81 ]
            }
        ]
    },
    "SSLEngine": "dynamic",
    "SSLEarlyData": false,
    "DropNotSSL": false,
    "SSLDownstream": true,
    "SSLDownstreamALPNAcception": [
        "h2",
        "http\/1.1"
    ],
    "SSLDownstreamBypass": {
        "Tuple": [],
        "Domain": [
            "*.googlevideo.com",
            "*.packetx.com",
            "*.bypass.com"
        ]
    },
    "SSLDownstreamBlock": {
        "Tuple": [],
        "Domain": [
            "*.block.com"
        ]
    },
    "SSLRootCA": "default/PacketX_ECDSA.crt",
    "SSLRootCAKey": "default/PacketX_ECDSA.key",
    "SSLRootCAPasswordFile": [],
    "SSLDownstreamHandshakeTimeout": 60000,
    "SSLDHparam": "",
    "SSLECDHCurve": "auto",
    "SSLDownstreamCiphers": "ALL:!EXPORT:!LOW:!aNULL:!eNULL:!SSLv2",
    "SSLPreferServerCiphers": false,
    "SSLDownstreamMinVersion": "SSLv3",
    "SSLDownstreamMaxVersion": "TLSv1.3",
    "SSLSessionTimeout": 300,
    "SSLSessionCache": "16777216", /* "off", "none" */
    "SSLSessionTickets": true,
    "SSLSessionTicketKey": [],
    "SSLUpstream": true,
    "SSLUpstreamHandshakeTimeout": 60000,
    "SSLUpstreamCiphers": "DEFAULT",
    "SSLUpstreamMinVersion": "SSLv3",
    "SSLUpstreamMaxVersion": "TLSv1.3",
    "SSLSessionReuse": true,
    "_NetworkSimulator": [
        {
            "MTU": 1450,
            "FixedDestinationPort": 80,
            "SendPort": "P6",
            "PcapPath": "default",
            "ContentPath": "default",
            "Hidden": {
                "Tuple": [],
                "Domain": [
                    "*.googlevideo.com",
                    "*.packetx.com",
                    "*.bypass.com"
                ],
                "CertificateFingerprint": [
                    "60ef838e2fdde480bfd0c12b9a55be8748cdb062544f7d20b27952bf45309070"
                ]
            }
        }
    ],
    "Sysloger": [
        {
            "DestinationIpv4Address": "127.0.0.1",
            "DestinationPort": 514,
            "AcceptingDownstream": true,
            "AcceptingDownstreamDenied": true,
            "AcceptedDownstream": true,
            "ConnectingUpstream": true,
            "ConnectingUpstreamTimeout": true,
            "ConnectingUpstreamReset": true,
            "ConnectedUpstream": true,
            "TCPEstablished": true,
            "ForwardingFinished": true,
            "SSLPeekClientHelloTimeout": true,
            "NotSSL": true,
            "JA3": true,
            "BlockSNI": true,
            "BypassSNI": true,
            "SSLConnectingUpstream": true,
            "SSLConnectingUpstreamTimeout": true,
            "SSLConnectingUpstreamFailed": true,
            "JA3S": true,
            "SSLConnectedUpstream": true,
            "SSLAcceptingDownstream": true,
            "SSLAcceptingDownstreamTimeout": true,
            "SSLAcceptingDownstreamFailed": true,
            "SSLAcceptedDownstream": true,
            "SSLEstablished": true,
            "SSLUpstreamCertificateChain": true,
            "SSLUpstreamCertificateAllInOne": true,
            "SSLUpstreamCertificateSerialNumber": true,
            "SSLUpstreamCertificateSignatureAlgorithm": true,
            "SSLUpstreamCertificateDateValidation": true,
            "SSLUpstreamCertificateSelfSigned": true,
            "SSLUpstreamCertificateIssuer": true,
            "SSLUpstreamCertificateSubject": true,
            "SSLUpstreamCertificatePublicKey": true,
            "SSLUpstreamCertificateExtensionKeyUsage": true,
            "SSLUpstreamCertificateExtensionSAN": true,
            "SSLUpstreamCertificateFingerprintSHA1": true,
            "SSLUpstreamCertificateFingerprintSHA256": true
        }
    ]
}
```

Configuration
----------

<h3>Core</h3>

|              Key              |              Prompt              |    Json Type    |             Style             |        Validation       |                     Note                     |
|:-----------------------------:|:--------------------------------:|:---------------:|:-----------------------------:|:-----------------------:|:--------------------------------------------:|
|           MessageLog          |            Message Log           |     Boolean     |            Checkbox           |            -            |                       -                      |
|            ErrorLog           |             Error Log            |     Boolean     |            Checkbox           |            -            |                       -                      |
|           SessionLog          |            Session Log           |     Boolean     |            Checkbox           |            -            |                       -                      |
|          SSLErrorLog          |           SSL Error Log          |     Boolean     |            Checkbox           |            -            |                       -                      |
|            MaxCore            |                 -                |     Integer     |               -               |            -            |          Don't Change Default Value          |
|          BindNethook          |                 -                |      String     |               -               |            -            |          Don't Change Default Value          |
|            BindPort           |                 -                |     Integer     |               -               |            -            |          Don't Change Default Value          |
|            Backlog            |              Backlog             |     Integer     |        Textbox(Number)        | Greater or Equal to 511 |                       -                      |
|         MaxConcurrent         |                 -                |     Integer     |               -               |            -            |          Don't Change Default Value          |
|       TrackingTableName       |                 -                |      String     |               -               |            -            |          Don't Change Default Value          |
|        TimerResolution        |         Timer Resolution         |     Integer     |        Textbox(Number)        |            -            |                       -                      |
|           KeepAccept          |            Keep Accept           |     Boolean     |            Checkbox           |            -            |                       -                      |
|           TCPNoDelay          |           TCP No Delay           |     Boolean     |            Checkbox           |            -            |                       -                      |
|          TCPKeepAlive         |          TCP Keep Alive          |     Boolean     |            Checkbox           |            -            |                       -                      |
|        ProxyBufferSize        |         Proxy Buffer Size        |     Integer     |        Textbox(Number)        |      Greater Than 0     |                       -                      |
|         ConnectTimeout        |          Connect Timeout         |     Integer     |        Textbox(Number)        |      Greater Than 0     |                       -                      |
|          ConnectRetry         |           Connect Retry          |     Integer     |        Textbox(Number)        |            -            |                       -                      |
|          ProxyTimeout         |           Proxy Timeout          |     Integer     |        Textbox(Number)        |      Greater Than 0     |                       -                      |
|          DownloadRate         |           Download Rate          |     Integer     |        Textbox(Number)        |            -            |                       -                      |
|           UploadRate          |            Upload Rate           |     Integer     |        Textbox(Number)        |            -            |                       -                      |
|              JA3              |                JA3               |     Boolean     |            Checkbox           |            -            |                       -                      |
|              JA3S             |               JA3S               |     Boolean     |            Checkbox           |            -            |                       -                      |
|              Deny             |               Deny               |      Object     |               -               |        Must Exist       |             See [Bundle](#bundle)            |
|           SSLEngine           |                 -                |      String     |               -               |            -            |                       -                      |
|          SSLEarlyData         |          SSL Early Data          |     Boolean     |            Checkbox           |            -            |                       -                      |
|           DropNotSSL          |           Drop Not SSL           |     Boolean     |            Checkbox           |            -            |                       -                      |
|         SSLDownstream         |          -          |     Boolean     |            -           |            -            |              Don't Change Default Value             |
|   SSLDownstreamALPNAcception  |   SSL Downstream ALPN Acception  | Array of String | Textarea(String per One Line) |            -            |                       -                      |
|      SSLDownstreamBypass      |       SSL Downstream Bypass      |      Object     |               -               |            -            |             See [Bundle](#bundle)            |
|       SSLDownstreamBlock      |       SSL Downstream Block       |      Object     |               -               |            -            |             See [Bundle](#bundle)            |
|           SSLRootCA           |            SSL Root CA           |      String     |     Upload File(One File)     |      Must One File      |       See [Upload Files](#upload_files)      |
|          SSLRootCAKey         |          SSL Root CA Key          |      String     |     Upload File(One File)     |      Must One File      |       See [Upload Files](#upload_files)      |
|     SSLRootCAPasswordFile     |     SSL Root CA Password File    | Array of String |   Upload Files(Multi-Files)   |            -            |       See [Upload Files](#upload_files)      |
| SSLDownstreamHandshakeTimeout | SSL Downstream Handshake Timeout |     Integer     |        Textbox(Number)        |      Greater Than 0     |                       -                      |
|           SSLDHparam          |           SSL DH Param           |      String     |     Upload File(One File)     |            -            |       See [Upload Files](#upload_files)      |
|          SSLECDHCurve         |          SSL ECDH Curve          |      String     |            Textbox            |     See [Curve](#curve)    |              -             |
|      SSLDownstreamCiphers     |      SSL Downstream Ciphers      |      String     |            Textbox            |      See [Ciphers](#ciphers)      |            -           |
|     SSLPreferServerCiphers    |     SSL Prefer Server Ciphers    |     Boolean     |            Checkbox           |            -            |                       -                      |
|    SSLDownstreamMinVersion    |  SSL Downstream Minimum Version  |      String     |         Select Option         |    See [SSL Version](#ssl_version)    |        -       |
|    SSLDownstreamMaxVersion    |  SSL Downstream Maximum Version  |      String     |         Select Option         |    See [SSL Version](#ssl_version)    |        -       |
|       SSLSessionTimeout       |        SSL Session Timeout       |     Integer     |        Textbox(Number)        |      Greater Than 0     |                       -                      |
|        SSLSessionCache        |         SSL Session Cache        |      String     |               -               |            -            | See [Session Cache](#ssl_session_cache_mode) |
|       SSLSessionTickets       |        SSL Session Tickets       |     Boolean     |            Checkbox           |            -            |                       -                      |
|      SSLSessionTicketKey      |      SSL Session Ticket Key      | Array of String |   Upload Files(Multi-Files)   |            -            |       See [Upload Files](#upload_files)      |
|          SSLUpstream          |           -           |     Boolean     |            -           |            -            |              Don't Change Default Value             |
|  SSLUpstreamHandshakeTimeout  |  SSL Upstream Handshake Timeout  |     Integer     |        Textbox(Number)        |      Greater Than 0     |                       -                      |
|       SSLUpstreamCiphers      |       SSL Upstream Ciphers       |      String     |            Textbox            |      See [Ciphers](#ciphers)      |            -           |
|     SSLUpstreamMinVersion     |   SSL Upstream Minimum Version   |      String     |         Select Option         |    See [SSL Version](#ssl_version)    |        -       |
|     SSLUpstreamMaxVersion     |   SSL Upstream Maximum Version   |      String     |         Select Option         |    See [SSL Version](#ssl_version)    |        -       |
|        SSLSessionReuse        |         SSL Session Reuse        |     Boolean     |            Checkbox           |            -            |                       -                      |
|        NetworkSimulator       |         Network Simulator        | Array of Object |               -               |            -            |  See [Network Simulator](#network_simulator) |
|            Sysloger           |             Sysloger             | Array of Object |               -               |            -            |           See [Sysloger](#sysloger)          |
|          LoadBalance          |                 -                | Array of Object |               -               |            -            |                Unused for Now                |
|            Offload            |              Offload             | Array of Object |               -               |            -            |            See [Offload](#offload)           |
|             Onload            |              Onload              | Array of Object |               -               |            -            |             See [Onload](#onload)            |

<h3 id="bundle">Bundle</h3>

|           Key          |          Prompt         |    Json Type    |              Style             |               Validation              |                        Note                        |
|:----------------------:|:-----------------------:|:---------------:|:------------------------------:|:-------------------------------------:|:--------------------------------------------------:|
|          Tuple         |          Tuple          |      Object     |                -               |                   -                   | See [4-Tuple](07.Nethook-Configuration.md#4_tuple) |
|         Domain         |          Domain         | Array of String |  Textarea(String per One Line) |                   -                   |             Wildcard Domain is Accepted            |
| CertificateFingerprint | Certificate Fingerprint | Array of String | Textarea(SHA-256 per One Line) | Valid Length and Character of SHA-256 |                  Case Insensitive                  |

<h3 id="upload_files">Upload Files</h3>

**待補文件。**

<h3 id="curve">Curve</h3>

|          |               Template Curve              |
|:--------:|:-----------------------------------------:|
|  Method  |                    POST                   |
|   Path   |              /template/curve              |
|   Query  |                                           |
|   Form   |         { "Curve": "user input" }         |
| Response | {} or { "ErrorMessage": "Invalid Curve" } |

<h3 id="ciphers">Ciphers</h3>

|          |               Template Ciphers              |
|:--------:|:-------------------------------------------:|
|  Method  |                     POST                    |
|   Path   |              /template/ciphers              |
|   Query  |                                             |
|   Form   |         { "Ciphers": "user input" }         |
| Response | {} or { "ErrorMessage": "Invalid Ciphers" } |

<h3 id="ssl_version">SSL Version</h3>

|          |                            Template SSL Version                           |               Template SSL Version              |
|:--------:|:-------------------------------------------------------------------------:|:-----------------------------------------------:|
|  Method  |                                    GET                                    |                       POST                      |
|   Path   |                           /template/ssl_version                           |              /template/ssl_version              |
|   Query  |                                                                           |                                                 |
|   Form   |                                                                           |         { "SSL Version": "user input" }         |
| Response | { "SSLVersion": [ "SSLv3", "TLSv1.0", "TLSv1.1", "TLSv1.2", "TLSv1.3" ] } | {} or { "ErrorMessage": "Invalid SSL Version" } |

<h3 id="ssl_session_cache_mode">Session Cache</h3>

支援三種輸入方式，`off`、`none`以及輸入數字，數字的話必須大於0。

<h3 id="network_simulator">Network Simulator</h3>

|          Key         |         Prompt         | Json Type |      Style      |                                   Validation                                  |          Note         |
|:--------------------:|:----------------------:|:---------:|:---------------:|:-----------------------------------------------------------------------------:|:---------------------:|
|          MTU         |           MTU          |  Integer  | Textbox(Number) |                                  1000 to 1500                                 |           -           |
| FixedDestinationPort | Fixed Destination Port |  Integer  | Textbox(Number) |                                    0-65535                                    |           -           |
|       SendPort       |        Send Port       |   String  |  Select Option  | All AliasName Value of [GET /template/interface](05.Template.md#wizard_step2) |           -           |
|       PcapPath       |            -           |   String  |        -        |                                       -                                       |     Unused for Now    |
|      ContentPath     |            -           |   String  |        -        |                                       -                                       |     Unused for Now    |
|        Hidden        |         Hidden         |   Object  |        -        |                                       -                                       | See [Bundle](#bundle) |

<h3 id="sysloger">Sysloger</h3>

|                    Key                   |                    Prompt                    | Json Type |      Style      | Validation |           Note           |
|:----------------------------------------:|:--------------------------------------------:|:---------:|:---------------:|:----------:|:------------------------:|
|          DestinationIpv4Address          |           Destination IPv4 Address           |   String  |     Textbox     |    IPv4    |             -            |
|              DestinationPort             |               Destination Port               |  Integer  | Textbox(Number) |   0-65535  |             -            |
|            AcceptingDownstream           |             Accepting Downstream             |  Boolean  |     Checkbox    |      -     |             -            |
|         AcceptingDownstreamDenied        |          Accepting Downstream Denied         |  Boolean  |     Checkbox    |      -     |             -            |
|            AcceptedDownstream            |              Accepted Downstream             |  Boolean  |     Checkbox    |      -     |             -            |
|            ConnectingUpstream            |              Connecting Upstream             |  Boolean  |     Checkbox    |      -     |             -            |
|         ConnectingUpstreamTimeout        |          Connecting Upstream Timeout         |  Boolean  |     Checkbox    |      -     |             -            |
|          ConnectingUpstreamReset         |           Connecting Upstream Reset          |  Boolean  |     Checkbox    |      -     |             -            |
|             ConnectedUpstream            |              Connected Upstream              |  Boolean  |     Checkbox    |      -     |             -            |
|              TCPEstablished              |                TCP Established               |  Boolean  |     Checkbox    |      -     |             -            |
|            ForwardingFinished            |              Forwarding Finished             |  Boolean  |     Checkbox    |      -     |             -            |
|         SSLPeekClientHelloTimeout        |         SSL Peek ClientHello Timeout         |  Boolean  |     Checkbox    |      -     | Yes, It's "ClientHello". |
|                  NotSSL                  |                    Not SSL                   |  Boolean  |     Checkbox    |      -     |             -            |
|                    JA3                   |                      JA3                     |  Boolean  |     Checkbox    |      -     |             -            |
|                 BlockSNI                 |                   Block SNI                  |  Boolean  |     Checkbox    |      -     |             -            |
|                 BypassSNI                |                  Bypass SNI                  |  Boolean  |     Checkbox    |      -     |             -            |
|           SSLConnectingUpstream          |            SSL Connecting Upstream           |  Boolean  |     Checkbox    |      -     |             -            |
|       SSLConnectingUpstreamTimeout       |        SSL Connecting Upstream Timeout       |  Boolean  |     Checkbox    |      -     |             -            |
|        SSLConnectingUpstreamFailed       |        SSL Connecting Upstream Failed        |  Boolean  |     Checkbox    |      -     |             -            |
|           SSLConnectedUpstream           |            SSL Connected Upstream            |  Boolean  |     Checkbox    |      -     |             -            |
|                   JA3S                   |                     JA3S                     |  Boolean  |     Checkbox    |      -     |             -            |
|          SSLAcceptingDownstream          |           SSL Accepting Downstream           |  Boolean  |     Checkbox    |      -     |             -            |
|       SSLAcceptingDownstreamTimeout      |       SSL Accepting Downstream Timeout       |  Boolean  |     Checkbox    |      -     |             -            |
|           SSLAcceptedDownstream          |            SSL Accepted Downstream           |  Boolean  |     Checkbox    |      -     |             -            |
|              SSLEstablished              |                SSL Established               |  Boolean  |     Checkbox    |      -     |             -            |
|        SSLUpstreamCertificateChain       |        SSL Upstream Certificate Chain        |  Boolean  |     Checkbox    |      -     |             -            |
|      SSLUpstreamCertificateAllInOne      |      SSL Upstream Certificate All in One     |  Boolean  |     Checkbox    |      -     |             -            |
|    SSLUpstreamCertificateSerialNumber    |    SSL Upstream Certificate Serial Number    |  Boolean  |     Checkbox    |      -     |             -            |
| SSLUpstreamCertificateSignatureAlgorithm | SSL Upstream Certificate Signature Algorithm |  Boolean  |     Checkbox    |      -     |             -            |
|   SSLUpstreamCertificateDateValidation   |   SSL Upstream Certificate Date Validation   |  Boolean  |     Checkbox    |      -     |             -            |
|     SSLUpstreamCertificateSelfSigned     |     SSL Upstream Certificate Self Signed     |  Boolean  |     Checkbox    |      -     |             -            |
|       SSLUpstreamCertificateIssuer       |        SSL Upstream Certificate Issuer       |  Boolean  |     Checkbox    |      -     |             -            |
|       SSLUpstreamCertificateSubject      |       SSL Upstream Certificate Subject       |  Boolean  |     Checkbox    |      -     |             -            |
|      SSLUpstreamCertificatePublicKey     |      SSL Upstream Certificate Public Key     |  Boolean  |     Checkbox    |      -     |             -            |
|  SSLUpstreamCertificateExtensionKeyUsage | SSL Upstream Certificate Extension Key Usage |  Boolean  |     Checkbox    |      -     |             -            |
|    SSLUpstreamCertificateExtensionSAN    |    SSL Upstream Certificate Extension SAN    |  Boolean  |     Checkbox    |      -     |             -            |
|   SSLUpstreamCertificateFingerprintSHA1  |   SSL Upstream Certificate Fingerprint SHA1  |  Boolean  |     Checkbox    |      -     |             -            |
|  SSLUpstreamCertificateFingerprintSHA256 |  SSL Upstream Certificate Fingerprint SHA256 |  Boolean  |     Checkbox    |      -     |             -            |

<h3 id="offload">Offload</h3>

|           Key           |         Prompt         | Json Type |         Style         |   Validation  |                Note               |
|:-----------------------:|:----------------------:|:---------:|:---------------------:|:-------------:|:---------------------------------:|
|   DestinationIpAddress  | Destination IP Address |   String  |        Textbox        |  IPv4 or IPv6 |                 -                 |
|      DowngradePort      |     Downgrade Port     |  Integer  |    Textbox(Number)    |    0-65535    |                 -                 |
|       Certificate       |       Certificate      |   String  | Upload File(One File) | Must One File | See [Upload Files](#upload_files) |
|      CertificateKey     |     Certificate Key    |   String  | Upload File(One File) | Must One File | See [Upload Files](#upload_files) |
| CertificatePasswordFile |            -           |   String  |           -           |       -       |           Unused for Now          |

<h3 id="onload">Onload</h3>

|          Key         |         Prompt         |    Json Type    |             Style             |  Validation  | Note |
|:--------------------:|:----------------------:|:---------------:|:-----------------------------:|:------------:|:----:|
| DestinationIpAddress | Destination IP Address |      String     |            Textbox            | IPv4 or IPv6 |   -  |
|      UpgradePort     |      Upgrade Port      |     Integer     |        Textbox(Number)        |    0-65535   |   -  |
|          SNI         |           SNI          |      String     |            Textbox            |       -      |   -  |
|       ALPNList       |        ALPN List       | Array of String | Textarea(String per One Line) |  Must Exist  |   -  |
