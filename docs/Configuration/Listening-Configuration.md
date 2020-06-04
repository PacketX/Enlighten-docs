Listening Configuration
==========

`Listening`第一個參數`IPS`會改變整個執行方式，有些參數也不同（會標記）。

Configuration
----------

<h3>Core</h3>

|              Key              |              Prompt              |    Json Type    |             Style             |        Validation       |                     Note                     |
|:-----------------------------:|:--------------------------------:|:---------------:|:-----------------------------:|:-----------------------:|:--------------------------------------------:|
|           IPS          |            -           |     Boolean     |            -           |            -            |                       Don't Change Default Value                      |
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
|        TimerResolution        |         Timer Resolution         |     Integer     |        Textbox(Number)        | Greater or Equal to 0 |                       -                      |
|           KeepAccept          |            Keep Accept           |     Boolean     |            Checkbox           |            -            |                       -                      |
|           TCPNoDelay          |           TCP No Delay           |     Boolean     |            Checkbox           |            -            |                       -                      |
|          TCPKeepAlive         |          TCP Keep Alive          |     Boolean     |            Checkbox           |            -            |                       -                      |
|        ProxyBufferSize        |         Proxy Buffer Size        |     Integer     |        Textbox(Number)        |      Greater Than 0     |                       -                      |
|         ConnectTimeout        |          Connect Timeout         |     Integer     |        Textbox(Number)        |      Greater Than 0     |                       -                      |
|          ConnectRetry         |           Connect Retry          |     Integer     |        Textbox(Number)        | Greater or Equal to 0 |                       -                      |
|          ProxyTimeout         |           Proxy Timeout          |     Integer     |        Textbox(Number)        |      Greater Than 0     |                       -                      |
|          DownloadRate         |           Download Rate          |     Integer     |        Textbox(Number)        | Greater or Equal to 0 |                       -                      |
|           UploadRate          |            Upload Rate           |     Integer     |        Textbox(Number)        | Greater or Equal to 0 |                       -                      |
|           IPv6          |            IPv6           |     Boolean     |            Checkbox           |            -            |                       -                      |
|           IPv6Only          |            IPv6 Only           |     Boolean     |            Checkbox           |            -            |                       -                      |
|         GracefulTimeout        |          Graceful Timeout         |     Integer     |        Textbox(Number)        |      Greater Than 0     |                       -                      |
|              JA3              |                JA3               |     Boolean     |            Checkbox           |            -            |                       -                      |
|              JA3S             |               JA3S               |     Boolean     |            Checkbox           |            -            |                       -                      |
|              Deny             |               Deny               |      Object     |               -               |        Must Exist       |             See [Bundle](#Bundle)            |
|           SSLEngine           |                 -                |      String     |               -               |            -            |                       -                      |
|          SSLEarlyData         |          SSL Early Data          |     Boolean     |            Checkbox           |            -            |                       -                      |
|           DropNotSSL          |           Drop Not SSL           |     Boolean     |            Checkbox           |            -            |                       -                      |
|         SSLDownstream         |          -          |     Boolean     |            -           |            -            |              Don't Change Default Value             |
|   SSLDownstreamALPNAcception  |   SSL Downstream ALPN Acception  | Array of String | Textarea(String per One Line) |            -            |                       -                      |
|      SSLDownstreamBypass      |       SSL Downstream Bypass      |      Object     |               -               |            -            |             See [Bundle](#Bundle)            |
|       SSLDownstreamBlock      |       SSL Downstream Block       |      Object     |               -               |            -            |             See [Bundle](#Bundle)            |
|           SSLRootCA           |            SSL Root CA           |      String     |     Upload File(One File)     |      Must One File      |       -      |
|          SSLRootCAKey         |          SSL Root CA Key          |      String     |     Upload File(One File)     |      Must One File      |       -      |
|     SSLRootCAPasswordFile     |     SSL Root CA Password File    | Array of String |   Upload Files(Multi-Files)   |            -            |       -      |
| SSLDownstreamHandshakeTimeout | SSL Downstream Handshake Timeout |     Integer     |        Textbox(Number)        |      Greater Than 0     |                       -                      |
|           SSLDHparam          |           SSL DH Param           |      String     |     Upload File(One File)     |            -            |       -      |
|          SSLECDHCurve         |          SSL ECDH Curve          |      String     |            Textbox            |     -    |              -             |
|      SSLDownstreamCiphers     |      SSL Downstream Ciphers      |      String     |            Textbox            |      -      |            -           |
|     SSLPreferServerCiphers    |     SSL Prefer Server Ciphers    |     Boolean     |            Checkbox           |            -            |                       -                      |
|    SSLDownstreamMinVersion    |  SSL Downstream Minimum Version  |      String     |         Select Option         |    -    |        -       |
|    SSLDownstreamMaxVersion    |  SSL Downstream Maximum Version  |      String     |         Select Option         |    -    |        -       |
|       SSLSessionTimeout       |        SSL Session Timeout       |     Integer     |        Textbox(Number)        |      Greater Than 0     |                       -                      |
|        SSLSessionCache        |         SSL Session Cache        |      String     |               -               |            -            | - |
|       SSLSessionTickets       |        SSL Session Tickets       |     Boolean     |            Checkbox           |            -            |                       -                      |
|      SSLSessionTicketKey      |      SSL Session Ticket Key      | Array of String |   Upload Files(Multi-Files)   |            -            |       -      |
|          SSLUpstream          |           -           |     Boolean     |            -           |            -            |              Don't Change Default Value             |
|  SSLUpstreamHandshakeTimeout  |  SSL Upstream Handshake Timeout  |     Integer     |        Textbox(Number)        |      Greater Than 0     |                       -                      |
|       SSLUpstreamCiphers      |       SSL Upstream Ciphers       |      String     |            Textbox            |      -      |            -           |
|     SSLUpstreamMinVersion     |   SSL Upstream Minimum Version   |      String     |         Select Option         |    -    |        -       |
|     SSLUpstreamMaxVersion     |   SSL Upstream Maximum Version   |      String     |         Select Option         |    -    |        -       |
|        SSLSessionReuse        |         SSL Session Reuse        |     Boolean     |            Checkbox           |            -            |                       -                      |
|        NetworkSimulator       |         Network Simulator        | Array of Object |               -               |            -            |  See [Network Simulator](#Network_Simulator) |
|            Sysloger           |             Sysloger             | Array of Object |               -               |            -            |           See [Sysloger](#Sysloger)          |
|          LoadBalance          |                 -                | Array of Object |               -               |            -            |                Unused for Now                |
|            Offload            |              Offload             | Array of Object |               -               |            -            |            See [Offload](#Offload)           |
|             Onload            |              Onload              | Array of Object |               -               |            -            |             See [Onload](#Onload)            |

<h3 id="Bundle">Bundle</h3>

|           Key          |          Prompt         |    Json Type    |              Style             |               Validation              |                        Note                        |
|:----------------------:|:-----------------------:|:---------------:|:------------------------------:|:-------------------------------------:|:--------------------------------------------------:|
|          Tuple         |          Tuple          |      Object     |                -               |                   -                   | See [4-Tuple](Configuration/Nethook-Configuration.md#4_Tuple) |
|         Domain         |          Domain         | Array of String |  Textarea(String per One Line) |                   -                   |             Wildcard Domain is Accepted            |
| CertificateFingerprint | Certificate Fingerprint | Array of String | Textarea(SHA-256 per One Line) | Valid Length and Character of SHA-256 |                  Case Insensitive                  |

<h3 id="SSL_Session_Cache_Mode">Session Cache</h3>

支援三種輸入方式，`off`、`none`以及輸入數字，數字的話必須大於0。

<h3 id="Network_Simulator">Network Simulator</h3>

|          Key         |         Prompt         | Json Type |      Style      |                                   Validation                                  |          Note         |
|:--------------------:|:----------------------:|:---------:|:---------------:|:-----------------------------------------------------------------------------:|:---------------------:|
|          MTU         |           MTU          |  Integer  | Textbox(Number) |                                  1000 to 1500                                 |           -           |
| FixedDestinationPort | Fixed Destination Port |  Integer  | Textbox(Number) |                                    0-65535                                    |           -           |
|       SendPort       |        Send Port       |   String  |  Select Option  | - |           -           |
|       PcapPath       |            -           |   String  |        -        |                                       -                                       |     Unused for Now    |
|      ContentPath     |            -           |   String  |        -        |                                       -                                       |     Unused for Now    |
|        Hidden        |         Hidden         |   Object  |        -        |                                       -                                       | See [Bundle](#Bundle) |

<h3 id="Sysloger">Sysloger</h3>

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
|       SSLAcceptingDownstreamFailed      |       SSL Accepting Downstream Failed       |  Boolean  |     Checkbox    |      -     |             -            |
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
|  SSLUpstreamCertificateKeyUsage | SSL Upstream Certificate Key Usage |  Boolean  |     Checkbox    |      -     |             -            |
|  SSLUpstreamCertificateExtensionKeyUsage | SSL Upstream Certificate Extension Key Usage |  Boolean  |     Checkbox    |      -     |             -            |
|    SSLUpstreamCertificateExtensionSAN    |    SSL Upstream Certificate Extension SAN    |  Boolean  |     Checkbox    |      -     |             -            |
|   SSLUpstreamCertificateFingerprintSHA1  |   SSL Upstream Certificate Fingerprint SHA1  |  Boolean  |     Checkbox    |      -     |             -            |
|  SSLUpstreamCertificateFingerprintSHA256 |  SSL Upstream Certificate Fingerprint SHA256 |  Boolean  |     Checkbox    |      -     |             -            |

<h3 id="Sysloger_IPS_Mode">Sysloger(IPS Mode)</h3>

|                    Key                   |                    Prompt                    | Json Type |      Style      | Validation |           Note           |
|:----------------------------------------:|:--------------------------------------------:|:---------:|:---------------:|:----------:|:------------------------:|
|          DestinationIpv4Address          |           Destination IPv4 Address           |   String  |     Textbox     |    IPv4    |             -            |
|              DestinationPort             |               Destination Port               |  Integer  | Textbox(Number) |   0-65535  |             -            |
| DecryptAcceptingDownstream | Decryption Side Accepting Downstream |  Boolean  |     Checkbox    |      -     |             -            |
| DecryptAcceptedDownstream | Decryption Side Accepted Downstream |  Boolean  |     Checkbox    |      -     |             -            |
| AcceptingDownstreamDenied | Decryption Side Accepting Downstream Denied |  Boolean  |     Checkbox    |      -     |             -            |
| EncryptAcceptingDownstream | Encryption Side Accepting Downstream |  Boolean  |     Checkbox    |      -     |             -            |
| EncryptAcceptedDownstream | Encryption Side Accepted Downstream |  Boolean  |     Checkbox    |      -     |             -            |
| EncryptAcceptingDownstreamTimeout | Encryption Side Accepting Downstream Timeout |  Boolean  |     Checkbox    |      -     |             -            |
| DecryptConnectingUpstream | Decryption Side Connecting Upstream |  Boolean  |     Checkbox    |      -     |             -            |
| DecryptConnectingUpstreamTimeout | Decryption Connecting Upstream Timeout |  Boolean  |     Checkbox    |      -     |             -            |
| DecryptConnectingUpstreamReset | Decryption Connecting Upstream Reset |  Boolean  |     Checkbox    |      -     |             -            |
| DecryptConnectedUpstream | Decryption Connected Upstream |  Boolean  |     Checkbox    |      -     |             -            |
| DecryptTCPEstablished | Decryption TCP Established |  Boolean  |     Checkbox    |      -     |             -            |
| DecryptForwardingFinished | Decryption Forwarding Finished |  Boolean  |     Checkbox    |      -     |             -            |
| EncryptConnectingUpstream | Encryption Connecting Upstream |  Boolean  |     Checkbox    |      -     |             -            |
| EncryptConnectingUpstreamTimeout | Encryption Connecting Upstream Timeout |  Boolean  |     Checkbox    |      -     |             -            |
| EncryptConnectingUpstreamReset | Encryption Connecting Upstream Reset |  Boolean  |     Checkbox    |      -     |             -            |
| EncryptConnectedUpstream | Encryption Connected Upstream |  Boolean  |     Checkbox    |      -     |             -            |
| EncryptTCPEstablished | Encryption TCP Established |  Boolean  |     Checkbox    |      -     |             -            |
| EncryptForwardingFinished | Encryption Forwarding Finished |  Boolean  |     Checkbox    |      -     |             -            |
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
|       SSLAcceptingDownstreamFailed      |       SSL Accepting Downstream Failed       |  Boolean  |     Checkbox    |      -     |             -            |
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
|  SSLUpstreamCertificateKeyUsage | SSL Upstream Certificate Key Usage |  Boolean  |     Checkbox    |      -     |             -            |
|  SSLUpstreamCertificateExtensionKeyUsage | SSL Upstream Certificate Extension Key Usage |  Boolean  |     Checkbox    |      -     |             -            |
|    SSLUpstreamCertificateExtensionSAN    |    SSL Upstream Certificate Extension SAN    |  Boolean  |     Checkbox    |      -     |             -            |
|   SSLUpstreamCertificateFingerprintSHA1  |   SSL Upstream Certificate Fingerprint SHA1  |  Boolean  |     Checkbox    |      -     |             -            |
|  SSLUpstreamCertificateFingerprintSHA256 |  SSL Upstream Certificate Fingerprint SHA256 |  Boolean  |     Checkbox    |      -     |             -            |

<h3 id="Offload">Offload</h3>

|           Key           |         Prompt         | Json Type |         Style         |   Validation  |                Note               |
|:-----------------------:|:----------------------:|:---------:|:---------------------:|:-------------:|:---------------------------------:|
|   DestinationIpAddress  | Destination IP Address |   String  |        Textbox        |  IPv4 or IPv6 |                 -                 |
|      DowngradePort      |     Downgrade Port     |  Integer  |    Textbox(Number)    |    0-65535    |                 -                 |
|       Certificate       |       Certificate      |   String  | Upload File(One File) | Must One File | - |
|      CertificateKey     |     Certificate Key    |   String  | Upload File(One File) | Must One File | - |
| CertificatePasswordFile |            -           |   String  |           -           |       -       |           Unused for Now          |

<h3 id="Onload">Onload</h3>

|          Key         |         Prompt         |    Json Type    |             Style             |  Validation  | Note |
|:--------------------:|:----------------------:|:---------------:|:-----------------------------:|:------------:|:----:|
| DestinationIpAddress | Destination IP Address |      String     |            Textbox            | IPv4 or IPv6 |   -  |
|      UpgradePort     |      Upgrade Port      |     Integer     |        Textbox(Number)        |    0-65535   |   -  |
|          SNI         |           SNI          |      String     |            Textbox            |       -      |   -  |
|       ALPNList       |        ALPN List       | Array of String | Textarea(String per One Line) |  Must Exist  |   -  |
