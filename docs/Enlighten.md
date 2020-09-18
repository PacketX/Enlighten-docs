Enlighten
================

Features
------------

* `ALPN`.
* `ARP`, `NDP` Cache and Responser.
* `DH Param`.
* `Downgrade Attack Prevention`.
* `Graceful Shutdown Connections`.
* `IPv4/IPv6`.
* `JA3`, `JA3S`.
* `Log Rotation`.
* `Perfect Forward Secrecy`.
* `Secure Renegotiation`.
* `SSL/TLS` Cipher Suite.
* `SSL/TLS` Engine.
* `SSL/TLS` Session Cache.
* `SSL/TLS` Session Reuse.
* `SSL/TLS` Session Ticket.
* `SSL/TLS` Supported Groups.
* `SSL/TLS` Versions: `SSLv2(Deprecated)`, `SSLv3`, `TLSv1.0`, `TLSv1.1`, `TLSv1.2` and `TLSv1.3`.
* `TLSv1.3` Early Data(0-RTT).
* Bandwidth Control.
* Block/Allow List of `4-Tuple` and `Domain`.
* Dynamic `SSL/TLS` Connections Detection.
* Network Simulator.
* Statistics.
* Syslog.
* TCP/IP Stack Adjustment.
* Timer resolution.

Proxy mode
-------------

1. `TCP to TCP`(Plain-Text forward)
2. `SSL/TLS to SSL/TLS`(Cipher-Text forward)
3. `SSL/TLS to TCP`(Offload forward)
4. `TCP to SSL/TLS`(Onload forward)
5. `SSL/TLS to TCP - TCP to SSL/TLS`(IPS mode)

Dynamic Generating Forged Certificates
-------------

* Proxy mode is `SSL/TLS to SSL/TLS` or `SSL/TLS to TCP - TCP to SSL/TLS`, auto sign a certificate for client, according to server gave certificate information.

Key Exchange(Base on OpenSSL Built)
-------------

1. `ECDHE`
2. `DHE`
3. `RSA`

Supported Named Groups(Base on OpenSSL Built)
-------------

1. `X25519`
2. `X448`
3. `P-256`
4. `P-384`
5. `P-521`

Symmetric Key(Base on OpenSSL Built)
-------------

1. `AES-CBC`
2. `AES-GCM`
3. `ChaCha20`

Cryptographic Message Authentication Code(Base on OpenSSL Built)
-------------

1. `SHA1`
2. `SHA128`
3. `SHA256`
4. `SHA384`
5. `SHA512`
6. `Poly1305`

Digital Signature Algorithm(Base on OpenSSL Built)
-------------

1. `RSA`
2. `ECDSA`

Load Balance
-------------

1. `Round Robin`
2. `Least Connection`
3. `Source Hash`
4. `Destination Hash`

SSL/TLS Session Reuse
-------------

1. `Session ID`
2. `Session Ticket`
3. `PSK(for TLSv1.3)`

SSL/TLS Extensions
-------------

1. `Application-Layer Protocol Negotiation(ALPN)`
2. `Server Name Indication(SNI)`

SSL/TLS Versions(Base on OpenSSL Built)
-------------

1. `SSLv2(Deprecated)`
2. `SSLv3`
3. `TLSv1.0`
4. `TLSv1.1`
5. `TLSv1.2`
6. `TLSv1.3`

Statistics
-------------

1. `Decryption side accepting downstream`
2. `Decryption side accepted downstream`
3. `Encryption side accepting downstream`
4. `Encryption side accepted downstream`
5. `Accepting downstream denied`
6. `Accepting downstream`
7. `Accepted downstream`
8. `Decryption side connecting upstream`
9. `Decryption side connecting upstream timeout`
10. `Decryption side connecting upstream reset`
11. `Decryption side connected upstream`
12. `Encryption side connecting upstream`
13. `Encryption side connecting upstream timeout`
14. `Encryption side connecting upstream reset`
15. `Encryption side connected upstream`
16. `Connecting upstream`
17. `Connecting upstream timeout`
18. `Connecting upstream reset`
19. `Connected upstream`
20. `Decryption side established`
21. `Encryption side established`
22. `Decryption side TCP session concurrent`
23. `Encryption side TCP session concurrent`
24. `Established`
25. `TCP session concurrent`
26. `SSL peek ClientHello timeout`
27. `Is not SSL`
28. `Block SNI`
29. `Bypass SNI`
30. `SSL connecting upstream`
31. `SSL connecting upstream timeout`
32. `SSL connecting upstream failed`
33. `SSL connected upstream`
34. `SSL accepting downstream`
35. `SSL accepting downstream timeout`
36. `SSL accepting downstream failed`
37. `SSL accepted downstream`
38. `SSL established`
39. `SSL session concurrent`
40. `Decryption side downstream received bytes`
41. `Decryption side downstream sent bytes`
42. `Decryption side upstream received bytes`
43. `Decryption side upstream sent bytes`
44. `Encryption side downstream received bytes`
45. `Encryption side downstream sent bytes`
46. `Encryption side upstream received bytes`
47. `Encryption side upstream sent bytes`
48. `Downstream received bytes`
49. `Downstream sent bytes`
50. `Upstream received bytes`
51. `Upstream sent bytes`
52. `Decryption side downstream received bytes per second`
53. `Decryption side downstream sent bytes per second`
54. `Decryption side upstream received bytes per second`
55. `Decryption side upstream sent bytes per second`
56. `Encryption side downstream received bytes per second`
57. `Encryption side downstream sent bytes per second`
58. `Encryption side upstream received bytes per second`
59. `Encryption side upstream sent bytes per second`
60. `Downstream received bytes per second`
61. `Downstream sent bytes per second`
62. `Upstream received bytes per second`
63. `Upstream sent bytes per second`
64. `Decryption side downstream received bytes per second peak`
65. `Decryption side downstream sent bytes per second peak`
66. `Decryption side upstream received bytes per second peak`
67. `Decryption side upstream sent bytes per second peak`
68. `Encryption side downstream received bytes per second peak`
69. `Encryption side downstream sent bytes per second peak`
70. `Encryption side upstream received bytes per second peak`
71. `Encryption side upstream sent bytes per second peak`
72. `Downstream received bytes per second peak`
73. `Downstream sent bytes per second peak`
74. `Upstream received bytes per second peak`
75. `Upstream sent bytes per second peak`
76. `Decryption side TCP session concurrent peak`
77. `Encryption side TCP session concurrent peak`
78. `TCP session concurrent peak`
79. `SSL session concurrent peak`
80. `Certificate in cache`
81. `Downstream SSL version`
    * `SSLv2`
    * `SSLv3`
    * `TLSv1.0`
    * `TLSv1.1`
    * `TLSv1.2`
    * `TLSv1.3`
    * `Unknown`
82. `Upstream SSL version`
    * `SSLv2`
    * `SSLv3`
    * `TLSv1.0`
    * `TLSv1.1`
    * `TLSv1.2`
    * `TLSv1.3`
    * `Unknown`
83. `Downstream SSL cipher`
84. `Upstream SSL cipher`

Network Simulator
------------------

1. Simulating decrypted data transmission as raw packet, IDS can do analyzation.
2. Save as `.pcap` format.
3. Save as raw content.
4. Disable simulation according to `5-tuple`, `Domain` and `Certificate fingerprint`(in `sha256`).

Syslog
-------------------

1. `Syslog` take [`RFC 5424`](https://tools.ietf.org/html/rfc5424) format.
2.  Format: `<priority(Facility + Level)>VERSION TIMESTAMP(ISO-8601) HOSTNAME APP-NAME PROCID MSGID STRUCTURED-DATA MSG`.
3. `Facility` is always `Local0`.
4. `VERSION` is 1.
5. Timestamp: [`ISO-8601`](https://www.iso.org/iso-8601-date-and-time-format.html)，`2020-03-03T02:02:02.000012Z`.
6. `HOSTNAME` if not used, setted to `-`.
7. `APP-NAME` current: `listening`.
8. `PROCID` is always `-`.
9. `STRUCTURED-DATA` is always `-`.
10. `MSG` is using `UTF-8` encoding, message start with a [`BOM`](https://tools.ietf.org/html/rfc5424#page-37)(0xEF 0xBB 0xBF).
11. `Source port` is `514`.

<h3>Listening Syslog</h3>

* `%Z`: Timestamp.
* `%P`: `[IPv4/IPv6 address]:Port`.
* `%S`: `SNI`, may a empty string.
* `%J`: `JA3` string.
* `%e`: error message or reason, may a empty string.
* `%dr`: `Listening` received bytes from Downstream.
* `%ds`: `Listening` sent bytes to Downstream.
* `%ur`: `Listening` received bytes from Upstream.
* `%us`: `Listening` sent bytes to Upstream.

<h4>Accepting Downstream(MSGID: 1)</h4>

* `<134>1 %Z - enlighten - 1 - BOM%P and %P downstream is accepting`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 1 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 downstream is accepting`

<h4>Accepting Downstream Denied(MSGID: 2)</h4>

* `<133>1 %Z - enlighten - 2 - BOM%P and %P downstream accepting is denied`
* `<local0.notice>1 2020-03-03T02:02:02.000012Z - enlighten - 2 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 downstream accepting is denied`

<h4>Accepted Downstream(MSGID: 3)</h4>

* `<134>1 %Z - enlighten - 3 - BOM%P and %P downstream is accepted`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 3 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 downstream is accepted`

<h4>Connecting Upstream(MSGID: 4)</h4>

* `<134>1 %Z - enlighten - 4 - BOM%P and %P upstream is connecting`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 4 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 upstream is connecting`

<h4>Connecting Upstream Timeout(MSGID: 5)</h4>

* `<133>1 %Z - enlighten - 5 - BOM%P and %P upstream connecting is timeout`
* `<local0.notice>1 2020-03-03T02:02:02.000012Z - enlighten - 5 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 upstream connecting is timeout`

<h4>Connecting Upstream Reset(MSGID: 6)</h4>

* `<133>1 %Z - enlighten - 6 - BOM%P and %P upstream connecting is reset`
* `<local0.notice>1 2020-03-03T02:02:02.000012Z - enlighten - 6 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 upstream connecting is reset`

<h4>Connected Upstream(MSGID: 7)</h4>

* `<134>1 %Z - enlighten - 7 - BOM%P and %P upstream is connected`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 7 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 upstream is connected`

<h4>Established(MSGID: 8)</h4>

* `<134>1 %Z - enlighten - 8 - BOM%P and %P stream proxy has been established`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 8 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 stream proxy has been established`

<h4>Forwarding Finished(MSGID: 9)</h4>

* `<134>1 %Z - enlighten - 9 - BOM%P and %P SNI '%S' downstream received '%dr bytes', sent '%ds bytes', upstream received '%ur bytes', sent '%us bytes'`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 9 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SNI 'www.example.com' downstream received '32 bytes', sent '128 bytes', upstream received '128 bytes', sent '32 bytes'`

<h4>SSL Peek ClientHello Timeout(MSGID: 10)</h4>

* `<133>1 %Z - enlighten - 10 - BOM%P and %P SSL peek ClientHello is timeout`
* `<local0.notice>1 2020-03-03T02:02:02.000012Z - enlighten - 10 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL peek ClientHello is timeout`

<h4>NotSSL(MSGID: 11)</h4>

* `<132>1 %Z - enlighten - 11 - BOM%P and %P is not a SSL connection`
* `<local0.warning>1 2020-03-03T02:02:02.000012Z - enlighten - 11 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 is not a SSL connection`

<h4>JA3(MSGID: 12)</h4>

* `<134>1 %Z - enlighten - 12 - BOM%P and %P JA3 SNI '%S' string '%J'`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 12 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 JA3 SNI 'www.example.com' string '771,49196-49162-49195-52393-49161-49200-49172-49199-52392-49171-159-57-56-107-158-52394-51-50-103-22-19-157-53-61-156-47-60-10-5-4,0-65281-10-11-13,29-23-24-25,0'`

<h4>BlockSNI(MSGID: 13)</h4>

* `<132>1 %Z - enlighten - 13 - BOM%P and %P SSL connection SNI '%S' has been blocked`
* `<local0.warning>1 2020-03-03T02:02:02.000012Z - enlighten - 13 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL connection SNI 'www.example.com' has been blocked`

<h4>BypassSNI(MSGID: 14)</h4>

* `<133>1 %Z - enlighten - 14 - BOM%P and %P SSL connection SNI '%S' has been bypassed`
* `<local0.notice>1 2020-03-03T02:02:02.000012Z - enlighten - 14 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL connection SNI 'www.example.com' has been bypassed`

<h4>SSL Connecting Upstream(MSGID: 15)</h4>

* `<134>1 %Z - enlighten - 15 - BOM%P and %P SSL upstream SNI '%S' is connecting`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 15 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL upstream SNI 'www.example.com' is connecting`

<h4>SSL Connecting Upstream Timeout(MSGID: 16)</h4>

* `<133>1 %Z - enlighten - 16 - BOM%P and %P SSL upstream SNI '%S' connecting is timeout`
* `<local0.notice>1 2020-03-03T02:02:02.000012Z - enlighten - 16 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL upstream SNI 'www.example.com' connecting is timeout`

<h4>SSL Connecting Upstream Failed(MSGID: 17)</h4>

* `<133>1 %Z - enlighten - 17 - BOM%P and %P SSL upstream SNI '%S' connecting is failed, '%e'`
* `<local0.notice>1 2020-03-03T02:02:02.000012Z - enlighten - 17 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL upstream SNI 'www.example.com' connecting is failed, 'error message here'`

<h4>JA3S(MSGID: 18)</h4>

* `<134>1 %Z - enlighten - 18 - BOM%P and %P JA3S SNI '%S' string '%J'`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 18 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 JA3S SNI 'www.example.com' string '771,49196,65281-0-11-35-23'`

<h4>SSL Connected Upstream(MSGID: 19)</h4>

* `<134>1 %Z - enlighten - 19 - BOM%P and %P SSL upstream SNI '%S' is connected`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 19 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL upstream SNI 'www.example.com' is connected`

<h4>SSL Accepting Downstream(MSGID: 20)</h4>

* `<134>1 %Z - enlighten - 20 - BOM%P and %P SSL downstream SNI '%S' is accepting`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 20 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL downstream SNI 'www.example.com' is accepting`

<h4>SSL Accepting Downstream Timeout(MSGID: 21)</h4>

* `<133>1 %Z - enlighten - 21 - BOM%P and %P SSL downstream SNI '%S' accepting is timeout`
* `<local0.notice>1 2020-03-03T02:02:02.000012Z - enlighten - 21 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL downstream SNI 'www.example.com' accepting is timeout`

<h4>SSL Accepting Downstream Failed(MSGID: 22)</h4>

* `<133>1 %Z - enlighten - 22 - BOM%P and %P SSL downstream SNI '%S' accepting is failed, '%e'`
* `<local0.notice>1 2020-03-03T02:02:02.000012Z - enlighten - 22 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL downstream SNI 'www.example.com' accepting is failed, 'error message here'`

<h4>SSL Accepted Downstream(MSGID: 23)</h4>

* `<134>1 %Z - enlighten - 23 - BOM%P and %P SSL downstream SNI '%S' is accepted`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 23 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL downstream SNI 'www.example.com' is accepted`

<h4>SSL Established(MSGID: 24)</h4>

* `<134>1 %Z - enlighten - 24 - BOM%P and %P SSL SNI '%S' stream proxy has been established`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 24 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL SNI 'www.example.com' stream proxy has been established`

<h4>SSL Upstream Certifiacte All in One(MSGID: 25)</h4>

Certificate information combine into one message, the disabled item is show as `-` or `0`.

* `<134>1 %Z - enlighten - 25 - BOM%P and %P SSL upstream SNI '%s' certificate '%d/%d' serial number: '%s', signature algorithm: '%s', not before: '%s'(%s), not after: '%s'(%s), issuer: '%s', subject: '%s', public key: '%s', '%u' bits, key usage: '%s', extension key usage: '%s', extension SAN, DNS: '%s', IPv4: '%s', IPv6: '%s', fingerprint(SHA1): '%s', fingerprint(SHA256): '%s'`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 25 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL SNI 'www.example.com' certificate '1/3' serial number: '47:e2:00:00:00:01:25:67:38:1f:16:b7:03:09:bb:0d', signature algorithm: 'sha256WithRSAEncryption', not before: 'Apr 17 10:41:32 2018 GMT'(Valid), not after: 'Apr 17 15:59:59 2020 GMT'(Not expired), issuer: '/C=TW/O=TAIWAN-CA/OU=Secure SSL Sub-CA/CN=TWCA Secure SSL Certification Authority', subject: '/C=TW/ST=Taiwan/L=Kaohsiung/O=National Kaohsiung University of Hospitality and Tourism/OU=edu/CN=*.nkuht.edu.tw', public key: 'RSA', '2048' bits, key usage: 'Digital Signature, Key Encipherment', extension key usage: 'TLS Web Server Authentication, TLS Web Client Authentication', extension SAN, DNS: '*.nkuht.edu.tw', IPv4: '', IPv6: '', fingerprint(SHA1): '20:95:ef:9b:6b:be:28:4a:eb:d3:06:27:7a:d9:6e:5058:3e:6a:40', fingerprint(SHA256): '8e:7c:d0:27:7d:0f:2a:1c:2e:93:45:5c:6f:19:08:69df:64:8b:19:ee:5f:77:4c:7d:d8:cb:cc:65:83:15:73'`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 25 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL SNI 'www.example.com' certificate '1/3' serial number: '40:01:33:53:e4:00:00:00:00:00:00:0c:ca:5d:1b:69', signature algorithm: 'sha256WithRSAEncryption', not before: 'Oct 28 07:38:31 2014 GMT'(Valid), not after: 'Oct 28 15:59:59 2030 GMT'(Not expired), issuer: '/C=TW/O=TAIWAN-CA/OU=Root CA/CN=TWCA Root Certification Authority', subject: '-', public key: 'RSA', '4096' bits, key usage: '-', extension key usage: '-', extension SAN, DNS: '-', IPv4: '-', IPv6: '-', fingerprint(SHA1): '-', fingerprint(SHA256): '8a:d4:7f:6d:70:a4:4f:a8:0a:f0:f9:31:12:5f:fe:3a76:87:6f:fa:d2:19:a4:d4:0a:13:c0:38:dc:85:e6:9e'`

<h4>SSL Upstream Certificate Serial Number(MSGID: 26)</h4>

* `<134>1 %Z - enlighten - 26 - BOM%P and %P SSL upstream SNI '%S' certificate '%d/%d' serial number: '%s'`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 26 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL SNI 'www.example.com' certificate '1/3' serial number: '7c:b8:49:16:b0:9a:48:7d:02:00:00:00:00:5b:67:79'`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 26 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL SNI 'www.example.com' certificate '1/3' serial number: '-7c:b8:49:16:b0:9a:48:7d:02:00:00:00:00:5b:67:79'`

<h4>SSL Upstream Certificate Signature Algorithm(MSGID: 27)</h4>

* `<134>1 %Z - enlighten - 27 - BOM%P and %P SSL upstream SNI '%S' certificate '%d/%d' signature algorithm: '%s'`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 27 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL SNI 'www.example.com' certificate '1/3' signature algorithm: 'sha256WithRSAEncryption'`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 27 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL SNI 'www.example.com' certificate '1/3' signature algorithm: 'ecdsa-with-SHA256'`

<h4>SSL Upstream Certificate Date Validation(MSGID: 28)</h4>

* `<134>1 %Z - enlighten - 28 - BOM%P and %P SSL upstream SNI '%S' certificate '%d/%d' not before: '%s'(%s), not after: '%s'(%s)`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 28 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL SNI 'www.example.com' certificate '1/3' not before: 'Jan 28 00:00:00 2019 GMT'(Valid), not after: 'Feb  1 12:00:00 2021 GMT'(Not expired)`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 28 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL SNI 'www.example.com' certificate '1/3' not before: 'Jan 28 00:00:00 2019 GMT'(Not valid), not after: 'Feb  1 12:00:00 2021 GMT'(Expired)`

<h4>SSL Upstream Certificate Self Signed(MSGID: 29)</h4>

* `<132>1 %Z - enlighten - 29 - BOM%P and %P SSL upstream SNI '%S' certificate '%d/%d' is a self signed certificate`
* `<local0.warning>1 2020-03-03T02:02:02.000012Z - enlighten - 29 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL SNI 'www.example.com' certificate '1/3' is a self signed certificate`

<h4>SSL Upstream Certificate Issuer(MSGID: 30)</h4>

* `<134>1 %Z - enlighten - 30 - BOM%P and %P SSL upstream SNI '%S' certificate '%d/%d' issuer: '%s'`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 30 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL SNI 'www.example.com' certificate '1/3' issuer: '/C=US/O=DigiCert Inc/OU=www.digicert.com/CN=DigiCert Global Root CA'`

<h4>SSL Upstream Certificate Subject(MSGID: 31)</h4>

* `<134>1 %Z - enlighten - 31 - BOM%P and %P SSL upstream SNI '%S' certificate '%d/%d' subject: '%s'`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 31 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL SNI 'www.example.com' certificate '1/3' subject: '/C=US/ST=California/L=San Francisco/O=Cloudflare, Inc./CN=cloudflare-dns.com'`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 31 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL SNI 'www.example.com' certificate '1/3' subject: '/C=TW/L=臺北市/O=中華電信股份有限公司/CN=www.cht.com.tw'`

<h4>SSL Upstream Certificate Public Key(MSGID: 32)</h4>

* `<134>1 %Z - enlighten - 32 - BOM%P and %P SSL upstream SNI '%S' certificate '%d/%d' public key: '%s', '%u' bits`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 32 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL SNI 'www.example.com' certificate '1/3' public key: 'EC', '256' bits`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 32 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL SNI 'www.example.com' certificate '1/3' public key: 'RSA', '2048' bits`

<h4>SSL Upstream Certificate Extension Key Usage(MSGID: 33)</h4>

* `<134>1 %Z - enlighten - 33 - BOM%P and %P SSL upstream SNI '%S' certificate '%d/%d' extension key usage: '%s'`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 33 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL SNI 'www.example.com' certificate '1/3' extension key usage: 'TLS Web Server Authentication, TLS Web Client Authentication'`

<h4>SSL Upstream Certificate Extension SAN(MSGID: 34)</h4>

* `<134>1 %Z - enlighten - 34 - BOM%P and %P SSL upstream SNI '%S' certificate '%d/%d' extension SAN, DNS: '%s', IPv4: '%s', IPv6: '%s'`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 34 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL SNI 'www.example.com' certificate '1/3' extension SAN, DNS: 'cloudflare-dns.com, *.cloudflare-dns.com, one.one.one.one', IPv4: '1.1.1.1, 1.0.0.1, 162.159.132.53, 162.159.36.1, 162.159.46.1', IPv6: '2606:4700:4700::1111, 2606:4700:4700::1001, 2606:4700:4700::64, 2606:4700:4700::6400'`
* `<134>1 %Z - enlighten - 34 - BOM%P and %P SSL upstream SNI '%S' certificate '%d/%d' extension SAN, DNS: 'www.cht.com.tw, eshop.cht.com.tw, eshop2.cht.com.tw, eshop3.cht.com.tw, handicapfree.cht.com.tw', IPv4: '', IPv6: ''`

<h4>SSL Upstream Certificate Fingerprint SHA1(MSGID: 35)</h4>

* `<134>1 %Z - enlighten - 35 - BOM%P and %P SSL upstream SNI '%S' certificate '%d/%d' fingerprint(SHA1): '%s'`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 35 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL SNI 'www.example.com' certificate '1/3' fingerprint(SHA1): 'fd:54:e4:64:3b:49:70:5a:2a:ab:e5:06:53:c4:f5:6c2d:f8:07:3d'`

<h4>SSL Upstream Certificate Fingerprint SHA256(MSGID: 36)</h4>

* `<134>1 %Z - enlighten - 36 - BOM%P and %P SSL upstream SNI '%S' certificate '%d/%d' fingerprint(SHA256): '%s'`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 36 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL SNI 'www.example.com' certificate '1/3' fingerprint(SHA256): '8e:7c:d0:27:7d:0f:2d:1c:2e:93:45:5c:6f:19:08:69df:64:8b:20:ee:5f:77:4c:7d:d8:cb:cc:65:83:17:73'`

<h4>SSL Upstream Certificate Key Usage(MSGID: 37)</h4>

* `<134>1 %Z - enlighten - 37 - BOM%P and %P SSL upstream SNI '%S' certificate '%d/%d' key usage: '%s'`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 37 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL SNI 'www.example.com' certificate '1/3' key usage: 'Digital Signature, Key Encipherment'`

<h4>Decryption Side Accepting Downstream(MSGID: 38)</h4>

* `<134>1 %Z - enlighten - 38 - BOM%P and %P decrypt side downstream is accepting`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 38 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 decrypt side downstream is accepting`

<h4>Decryption Side Accepted Downstream(MSGID: 39)</h4>

* `<134>1 %Z - enlighten - 39 - BOM%P and %P decrypt side downstream is accepted`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 39 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 decrypt side downstream is accepted`

<h4>Decryption Side Connecting Upstream(MSGID: 40)</h4>

* `<134>1 %Z - enlighten - 40 - BOM%P and %P decrypt side upstream is connecting`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 40 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 decrypt side upstream is connecting`

<h4>Decryption Side Connecting Upstream Timeout(MSGID: 41)</h4>

* `<133>1 %Z - enlighten - 41 - BOM%P and %P decrypt side upstream connecting is timeout`
* `<local0.notice>1 2020-03-03T02:02:02.000012Z - enlighten - 41 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 decrypt side upstream connecting is timeout`

<h4>Decryption Side Connecting Upstream Reset(MSGID: 42)</h4>

* `<133>1 %Z - enlighten - 42 - BOM%P and %P decrypt side upstream connecting is reset`
* `<local0.notice>1 2020-03-03T02:02:02.000012Z - enlighten - 42 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 decrypt side upstream connecting is reset`

<h4>Decryption Side Connected Upstream(MSGID: 43)</h4>

* `<134>1 %Z - enlighten - 43 - BOM%P and %P decrypt side upstream is connected`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 43 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 decrypt side upstream is connected`

<h4>Decryption Side Established(MSGID: 44)</h4>

* `<134>1 %Z - enlighten - 44 - BOM%P and %P decrypt side stream proxy has been established`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 44 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 decrypt side stream proxy has been established`

<h4>Decryption Side Forwarding Finished(MSGID: 45)</h4>

* `<134>1 %Z - enlighten - 45 - BOM%P and %P decrypt side SNI '%S' downstream received '%dr bytes', sent '%ds bytes', upstream received '%ur bytes', sent '%us bytes'`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 45 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 decrypt side SNI 'www.example.com' downstream received '146 bytes', sent '1763 bytes', upstream received '1763 bytes', sent '146 bytes'`

<h4>Encryption Side Accepting Downstream(MSGID: 46)</h4>

* `<134>1 %Z - enlighten - 46 - BOM%P and %P encrypt side downstream is accepting`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 46 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 encrypt side downstream is accepting`

<h4>Encryption Side Accepted Downstream(MSGID: 47)</h4>

* `<134>1 %Z - enlighten - 47 - BOM%P and %P encrypt side downstream is accepted`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 47 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 encrypt side downstream is accepted`

<h4>Encryption Side Accepting Dowstream Timeout(MSGID: 48)</h4>

* `<133>1 %Z - enlighten - 48 - BOM%P and %P encrypt side downstream accepting is timeout`
* `<local0.notice>1 2020-03-03T02:02:02.000012Z - enlighten - 48 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 encrypt side downstream accepting is timeout`

<h4>Encryption Side Connecting Upstream(MSGID: 49)</h4>

* `<134>1 %Z - enlighten - 49 - BOM%P and %P encrypt side upstream is connecting`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 49 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 encrypt side upstream is connecting`

<h4>Encryption Side Connecting Upstream Timeout(MSGID: 50)</h4>

* `<133>1 %Z - enlighten - 50 - BOM%P and %P encrypt side upstream connecting is timeout`
* `<local0.notice>1 2020-03-03T02:02:02.000012Z - enlighten - 50 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 encrypt side upstream connecting is timeout`

<h4>Encryption Side Connecting Upstream Reset(MSGID: 51)</h4>

* `<133>1 %Z - enlighten - 51 - BOM%P and %P encrypt side upstream connecting is reset`
* `<local0.notice>1 2020-03-03T02:02:02.000012Z - enlighten - 51 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 encrypt side upstream connecting is reset`

<h4>Encryption Side Connected Upstream(MSGID: 52)</h4>

* `<134>1 %Z - enlighten - 52 - BOM%P and %P encrypt side upstream is connected`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 52 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 encrypt side upstream is connected`

<h4>Encryption Side Established(MSGID: 53)</h4>

* `<134>1 %Z - enlighten - 53 - BOM%P and %P encrypt side stream proxy has been established`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 53 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 encrypt side stream proxy has been established`

<h4>Encryption Side Forwarding Finished(MSGID: 54)</h4>

* `<134>1 %Z - enlighten - 54 - BOM%P and %P encrypt side SNI '%S' downstream received '%dr bytes', sent '%ds bytes', upstream received '%ur bytes', sent '%us bytes'`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 54 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 encrypt side SNI 'www.example.com' downstream received '146 bytes', sent '1763 bytes', upstream received '1763 bytes', sent '146 bytes'`
