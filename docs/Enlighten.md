Enlighten
================

**`This site is automatically generated, some pages are disabled.`**

Features
------------

* `ARP`, `NDP` Cache and Responser。
* `4-Tuple`和`Domain`之黑名單、白名單。
* 動態檢測所有Port是否為`SSL/TLS`連線並可阻斷或通知非`SSL/TLS`連線。
* `SSL/TLS` Engine。
* `SSL/TLS` [Cipher Suite](https://www.openssl.org/docs/man1.1.1/man1/ciphers.html)列表。
* `SSL/TLS` 版本控制，`SSLv2(Deprecated)`、`SSLv3`、`TLSv1.0`、`TLSv1.1`、`TLSv1.2`、`TLSv1.3`。
* `IPv4/IPv6`。
* [Network Simulator](#ns)。
* [Syslog](#syslog)。
* [`JA3`](https://engineering.salesforce.com/tls-fingerprinting-with-ja3-and-ja3s-247362855967)、[`JA3S`](https://engineering.salesforce.com/tls-fingerprinting-with-ja3-and-ja3s-247362855967)。
* `TLSv1.3` Early Data(0-RTT)。
*  頻寬控制。
* [`ALPN`](https://en.wikipedia.org/wiki/Application-Layer_Protocol_Negotiation)。
* DH Param。
* `SSL/TLS` Session Cache。
* `SSL/TLS` Session Ticket。
* `SSL/TLS` Session Reuse。
* 時間準確度誤差允許值。
* Perfect Forward Secrecy。
* Secure Renegotiation。
* Downgrade Attack Prevention。

Proxy
-------------

支援五種代理方式:

1. `TCP to TCP`(Plain-Text forward)
2. `SSL/TLS to SSL/TLS`(Cipher-Text forward)
3. `SSL/TLS to TCP`(Offload forward)
4. `TCP to SSL/TLS`(Onload forward)
5. `SSL/TLS to TCP - TCP to SSL/TLS`(IPS mode)

Dynamic Generating Forged Certificates
-------------

* Proxy mode為`SSL/TLS to SSL/TLS`時，會根據Server憑證資訊動態簽出一個憑證給Client。

Key Exchange(Base on OpenSSL Builds)
-------------

1. `ECDHE`
2. `DHE`
3. `RSA`

Supported Named Groups(Base on OpenSSL Builds)
-------------

1. `X25519`
2. `X448`
3. `P-256`
4. `P-384`
5. `P-521`

Symmetric Key(Base on OpenSSL Builds)
-------------

1. `RC4`
2. `3DES`
3. `AES-CBC`
4. `AES-GCM`
5. `ChaCha20`
6. `Camellia`
7. `SEED`


Cryptographic Message Authentication Code(Base on OpenSSL Builds)
-------------

1. `MD5`
2. `SHA256`
3. `SHA384`
4. `Poly1305`

Digital Signature Algorithm(Base on OpenSSL Builds)
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

SSL/TLS Versions(Base on OpenSSL Builds)
-------------

1. `SSLv2(Deprecated)`
2. `SSLv3`
3. `TLSv1.0`
4. `TLSv1.1`
5. `TLSv1.2`
6. `TLSv1.3`

Statistics
-------------

1. `Accepting downstream`
2. `Accepting downstream denied`
3. `Accepted downstream`
4. `Connecting upstream`
5. `Connecting upstream timeout`
6. `Connecting upstream reset`
7. `Connected upstream`
8. `TCP session concurrent`
9. `TCP established`
10. `SSL peek ClientHello timeout`
11. `Is not SSL`
12. `Block SNI`
13. `Bypass SNI`
14. `SSL connecting upstream`
15. `SSL connecting upstream timeout`
16. `SSL connecting upstream failed`
17. `SSL connected upstream`
18. `SSL accepting downstream`
19. `SSL accepting downstream timeout`
20. `SSL accepting downstream failed`
21. `SSL accepted downstream`
22. `SSL established`
23. `SSL session concurrent`
24. `Downstream recevied bytes`
25. `Downstream sent bytes`
26. `Upstream recevied bytes`
27. `Upstream sent bytes`
28. `Downstream recevied bytes per second`
29. `Downstream sent bytes per second`
30. `Upstream recevied bytes per second`
31. `Upstream sent bytes per sencod`
32. `TCP session concurrent peak`
33. `SSL session concurrent peak`
34. `Downstream recevied bytes per second peak`
35. `Downstream sent bytes per second peak`
36. `Upstream recevied bytes per second peak`
37. `Upstream sent bytes per sencod peak`
38. `Certificate in cache`
39. `Downstream SSL version`
40. `Upstream SSL version`
41. `Downstream SSL cipher`
42. `Upstream SSL cipher`

<h2 id="ns">Network Simulator</h2>

1. 網路模擬功能會將解密的資料再以封包方式拋出，讓外部的IDS設備接收分析。
2. 可儲存成`.pcap`封包檔案。
3. 可將原始資料儲存成檔案。
4. 可根據`5-tuple`、`Domain`以及`Certificate fingerprint`(`sha256`)來禁止模擬送出或儲存。

<h2 id="syslog">Syslog</h2>

1. `Syslog`採用[`RFC 5424`](https://tools.ietf.org/html/rfc5424)。
2.  大致格式為: `<priority(Facility + Level)>VERSION TIMESTAMP(ISO-8601) HOSTNAME APPLICATION PID MESSAGE-ID STRUCTURED-DATA MSG`。
3. `Facility`為`Local0`。
4. 目前`VERSION`為1。
5. 時戳格式為: [`ISO-8601`](https://www.iso.org/iso-8601-date-and-time-format.html)，`2020-03-03T02:02:02.000012Z`。
6. `HOSTNAME`若沒設定，為`-`。
7. `APPLICATION`為`enlighten`。
8. `PID`為`-`。
9. `STRUCTURED-DATA`為`-`。
10. `MSG`採`UTF-8`編碼，所以開頭會帶有[`BOM`](https://tools.ietf.org/html/rfc5424#page-37)(0xEF 0xBB 0xBF)。
11. `Source port`為`514`。

* `%Z`: 時戳。
* `%P`: `[IPv4/IPv6地址]:Port`。
* `%S`: `SNI`，可能為空字串。
* `%J`: `JA3`字串。
* `%e`: 錯誤訊息或原因，可能為空字串。
* `%dr`: `Enlighten`從Downstream端讀取的bytes數。
* `%ds`: `Enlighten`送往Downstream端的bytes數。
* `%ur`: `Enlighten`從Upstream端讀取的bytes數。
* `%us`: `Enlighten`送往Upstream端的bytes數。

<h3>Accepting Downstream(MSG-ID: 1)</h3>

* `<134>1 %Z - enlighten - 1 - BOM%P and %P TCP downstream is accepting`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 1 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 TCP downstream is accepting`

<h3>Accepting Downstream Denied(MSG-ID: 2)</h3>

* `<133>1 %Z - enlighten - 2 - BOM%P and %P TCP downstream accepting is denied`
* `<local0.notice>1 2020-03-03T02:02:02.000012Z - enlighten - 2 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 TCP downstream accepting is denied`

<h3>Accepted Downstream(MSG-ID: 3)</h3>

* `<134>1 %Z - enlighten - 3 - BOM%P and %P TCP downstream is accepted`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 3 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 TCP downstream is accepted`

<h3>Connecting Upstream(MSG-ID: 4)</h3>

* `<134>1 %Z - enlighten - 4 - BOM%P and %P TCP upstream is connecting`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 4 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 TCP upstream is connecting`

<h3>Connecting Upstream Timeout(MSG-ID: 5)</h3>

* `<133>1 %Z - enlighten - 5 - BOM%P and %P TCP upstream connecting is timeout`
* `<local0.notice>1 2020-03-03T02:02:02.000012Z - enlighten - 5 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 TCP upstream connecting is timeout`

<h3>Connecting Upstream Reset(MSG-ID: 6)</h3>

* `<133>1 %Z - enlighten - 6 - BOM%P and %P TCP upstream connecting is reset`
* `<local0.notice>1 2020-03-03T02:02:02.000012Z - enlighten - 6 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 TCP upstream connecting is reset`

<h3>Connected Upstream(MSG-ID: 7)</h3>

* `<134>1 %Z - enlighten - 7 - BOM%P and %P TCP upstream is connected`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 7 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 TCP upstream is connected`

<h3>TCP Established(MSG-ID: 8)</h3>

* `<134>1 %Z - enlighten - 8 - BOM%P and %P TCP stream proxy has been established`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 8 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 TCP stream proxy has been established`

<h3>Forwarding Finished(MSG-ID: 9)</h3>

* `<134>1 %Z - enlighten - 9 - BOM%P and %P SNI '%S', downstream received '%dr bytes', sent '%ds bytes', upstream received '%ur bytes', sent '%us bytes'`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 9 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SNI 'www.example.com', downstream received '32 bytes', sent '128 bytes', upstream received '128 bytes', sent '32 bytes'`

<h3>SSL Peek ClientHello Timeout(MSG-ID: 10)</h3>

* `<133>1 %Z - enlighten - 10 - BOM%P and %P SSL peek ClientHello is timeout`
* `<local0.notice>1 2020-03-03T02:02:02.000012Z - enlighten - 10 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL peek ClientHello is timeout`

<h3>NotSSL(MSG-ID: 11)</h3>

* `<132>1 %Z - enlighten - 11 - BOM%P and %P is not a SSL connection`
* `<local0.warning>1 2020-03-03T02:02:02.000012Z - enlighten - 11 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 is not a SSL connection`

<h3>JA3(MSG-ID: 12)</h3>

* `<134>1 %Z - enlighten - 12 - BOM%P and %P JA3 SNI '%S', string '%J'`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 12 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 JA3 SNI 'www.example.com', string '771,49196-49162-49195-52393-49161-49200-49172-49199-52392-49171-159-57-56-107-158-52394-51-50-103-22-19-157-53-61-156-47-60-10-5-4,0-65281-10-11-13,29-23-24-25,0'`

<h3>BlockSNI(MSG-ID: 13)</h3>

* `<132>1 %Z - enlighten - 13 - BOM%P and %P SSL connection SNI '%S' has been blocked`
* `<local0.warning>1 2020-03-03T02:02:02.000012Z - enlighten - 13 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL connection SNI 'www.example.com' has been blocked`

<h3>BypassSNI(MSG-ID: 14)</h3>

* `<133>1 %Z - enlighten - 14 - BOM%P and %P SSL connection SNI '%S' has been bypassed`
* `<local0.notice>1 2020-03-03T02:02:02.000012Z - enlighten - 14 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL connection SNI 'www.example.com' has been bypassed`

<h3>SSL Connecting Upstream(MSG-ID: 15)</h3>

* `<134>1 %Z - enlighten - 15 - BOM%P and %P SSL upstream SNI '%S' is connecting`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 15 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL upstream SNI 'www.example.com' is connecting`

<h3>SSL Connecting Upstream Timeout(MSG-ID: 16)</h3>

* `<133>1 %Z - enlighten - 16 - BOM%P and %P SSL upstream SNI '%S' connecting is timeout`
* `<local0.notice>1 2020-03-03T02:02:02.000012Z - enlighten - 16 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL upstream SNI 'www.example.com' connecting is timeout`

<h3>SSL Connecting Upstream Failed(MSG-ID: 17)</h3>

* `<133>1 %Z - enlighten - 17 - BOM%P and %P SSL upstream SNI '%S' connecting is failed, '%e'`
* `<local0.notice>1 2020-03-03T02:02:02.000012Z - enlighten - 17 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL upstream SNI 'www.example.com' connecting is failed, 'error message here'`

<h3>JA3S(MSG-ID: 18)</h3>

* `<134>1 %Z - enlighten - 18 - BOM%P and %P JA3S SNI '%S', string '%J'`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 18 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 JA3S SNI 'www.example.com' string '771,49196,65281-0-11-35-23'`

<h3>SSL Connected Upstream(MSG-ID: 19)</h3>

* `<134>1 %Z - enlighten - 19 - BOM%P and %P SSL upstream SNI '%S' is connected`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 19 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL upstream SNI 'www.example.com' is connected`

<h3>SSL Accepting Downstream(MSG-ID: 20)</h3>

* `<134>1 %Z - enlighten - 20 - BOM%P and %P SSL downstream SNI '%S' is accepting`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 20 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL downstream SNI 'www.example.com' is accepting`

<h3>SSL Accepting Downstream Timeout(MSG-ID: 21)</h3>

* `<133>1 %Z - enlighten - 21 - BOM%P and %P SSL downstream SNI '%S' accepting is timeout`
* `<local0.notice>1 2020-03-03T02:02:02.000012Z - enlighten - 21 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL downstream SNI 'www.example.com' accepting is timeout`

<h3>SSL Accepting Downstream Failed(MSG-ID: 22)</h3>

* `<133>1 %Z - enlighten - 22 - BOM%P and %P SSL downstream SNI '%S' accepting is failed, '%e'`
* `<local0.notice>1 2020-03-03T02:02:02.000012Z - enlighten - 22 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL downstream SNI 'www.example.com' accepting is failed, 'error message here'`

<h3>SSL Accepted Downstream(MSG-ID: 23)</h3>

* `<134>1 %Z - enlighten - 23 - BOM%P and %P SSL downstream SNI '%S' is accepted`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 23 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL downstream SNI 'www.example.com' is accepted`

<h3>SSL Established(MSG-ID: 24)</h3>

* `<134>1 %Z - enlighten - 24 - BOM%P and %P SSL SNI '%S' stream proxy has been established`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 24 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL SNI 'www.example.com' stream proxy has been established`

<h3>SSL Upstream Certifiacte All in One(MSG-ID: 25)</h3>

憑證相關資訊只用一條訊息送出，`disabled`的項目用`-`或`0`代替。

* `<134>1 %Z - enlighten - 25 - BOM%P and %P SSL upstream SNI '%s' certificate '%d/%d' serial number: '%s', signature algorithm: '%s', not before: '%s'(%s), not after: '%s'(%s), issuer: '%s', subject: '%s', public key: '%s', '%u' bits, extension key usage: '%s', extension SAN, DNS: '%s', IPv4: '%s', IPv6: '%s', fingerprint(SHA1): '%s', fingerprint(SHA256): '%s'`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 25 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL SNI 'www.example.com' certificate '1/3' serial number: '47:e2:00:00:00:01:25:67:38:1f:16:b7:03:09:bb:0d', signature algorithm: 'sha256WithRSAEncryption', not before: 'Apr 17 10:41:32 2018 GMT'(Valid), not after: 'Apr 17 15:59:59 2020 GMT'(Not expired), issuer: '/C=TW/O=TAIWAN-CA/OU=Secure SSL Sub-CA/CN=TWCA Secure SSL Certification Authority', subject: '/C=TW/ST=Taiwan/L=Kaohsiung/O=National Kaohsiung University of Hospitality and Tourism/OU=edu/CN=*.nkuht.edu.tw', public key: 'RSA', '2048' bits, extension key usage: 'Digital Signature, Key Encipherment', extension SAN, DNS: '*.nkuht.edu.tw', IPv4: '', IPv6: '', fingerprint(SHA1): '20:95:ef:9b:6b:be:28:4a:eb:d3:06:27:7a:d9:6e:5058:3e:6a:40', fingerprint(SHA256): '8e:7c:d0:27:7d:0f:2a:1c:2e:93:45:5c:6f:19:08:69df:64:8b:19:ee:5f:77:4c:7d:d8:cb:cc:65:83:15:73'`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 25 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL SNI 'www.example.com' certificate '1/3' serial number: '40:01:33:53:e4:00:00:00:00:00:00:0c:ca:5d:1b:69', signature algorithm: 'sha256WithRSAEncryption', not before: 'Oct 28 07:38:31 2014 GMT'(Valid), not after: 'Oct 28 15:59:59 2030 GMT'(Not expired), issuer: '/C=TW/O=TAIWAN-CA/OU=Root CA/CN=TWCA Root Certification Authority', subject: '-', public key: 'RSA', '4096' bits, extension key usage: '-', extension SAN, DNS: '-', IPv4: '-', IPv6: '-', fingerprint(SHA1): '-', fingerprint(SHA256): '8a:d4:7f:6d:70:a4:4f:a8:0a:f0:f9:31:12:5f:fe:3a76:87:6f:fa:d2:19:a4:d4:0a:13:c0:38:dc:85:e6:9e'`

<h3>SSL Upstream Certificate Serial Number(MSG-ID: 26)</h3>

* `<134>1 %Z - enlighten - 26 - BOM%P and %P SSL upstream SNI '%S' certificate '%d/%d' serial number: '%s'`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 26 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL SNI 'www.example.com' certificate '1/3' serial number: '7c:b8:49:16:b0:9a:48:7d:02:00:00:00:00:5b:67:79'`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 26 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL SNI 'www.example.com' certificate '1/3' serial number: '-7c:b8:49:16:b0:9a:48:7d:02:00:00:00:00:5b:67:79'`

<h3>SSL Upstream Certificate Signature Algorithm(MSG-ID: 27)</h3>

* `<134>1 %Z - enlighten - 27 - BOM%P and %P SSL upstream SNI '%S' certificate '%d/%d' signature algorithm: '%s'`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 27 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL SNI 'www.example.com' certificate '1/3' signature algorithm: 'sha256WithRSAEncryption'`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 27 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL SNI 'www.example.com' certificate '1/3' signature algorithm: 'ecdsa-with-SHA256'`

<h3>SSL Upstream Certificate Date Validation(MSG-ID: 28)</h3>

* `<134>1 %Z - enlighten - 28 - BOM%P and %P SSL upstream SNI '%S' certificate '%d/%d' not before: '%s'(%s), not after: '%s'(%s)`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 28 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL SNI 'www.example.com' certificate '1/3' not before: 'Jan 28 00:00:00 2019 GMT'(Valid), not after: 'Feb  1 12:00:00 2021 GMT'(Not expired)`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 28 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL SNI 'www.example.com' certificate '1/3' not before: 'Jan 28 00:00:00 2019 GMT'(Not valid), not after: 'Feb  1 12:00:00 2021 GMT'(Expired)`

<h3>SSL Upstream Certificate Self Signed(MSG-ID: 29)</h3>

* `<132>1 %Z - enlighten - 29 - BOM%P and %P SSL upstream SNI '%S' certificate '%d/%d' is a self signed certificate`
* `<local0.warning>1 2020-03-03T02:02:02.000012Z - enlighten - 29 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL SNI 'www.example.com' certificate '1/3' is a self signed certificate`

<h3>SSL Upstream Certificate Issuer(MSG-ID: 30)</h3>

* `<134>1 %Z - enlighten - 30 - BOM%P and %P SSL upstream SNI '%S' certificate '%d/%d' issuer: '%s'`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 30 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL SNI 'www.example.com' certificate '1/3' issuer: '/C=US/O=DigiCert Inc/OU=www.digicert.com/CN=DigiCert Global Root CA'`

<h3>SSL Upstream Certificate Subject(MSG-ID: 31)</h3>

* `<134>1 %Z - enlighten - 31 - BOM%P and %P SSL upstream SNI '%S' certificate '%d/%d' subject: '%s'`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 31 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL SNI 'www.example.com' certificate '1/3' subject: '/C=US/ST=California/L=San Francisco/O=Cloudflare, Inc./CN=cloudflare-dns.com'`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 31 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL SNI 'www.example.com' certificate '1/3' subject: '/C=TW/L=臺北市/O=中華電信股份有限公司/CN=www.cht.com.tw'`

<h3>SSL Upstream Certificate Public Key(MSG-ID: 32)</h3>

* `<134>1 %Z - enlighten - 32 - BOM%P and %P SSL upstream SNI '%S' certificate '%d/%d' public key: '%s', '%u' bits`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 32 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL SNI 'www.example.com' certificate '1/3' public key: 'EC', '256' bits`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 32 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL SNI 'www.example.com' certificate '1/3' public key: 'RSA', '2048' bits`

<h3>SSL Upstream Certificate Extension Key Usage(MSG-ID: 33)</h3>

* `<134>1 %Z - enlighten - 33 - BOM%P and %P SSL upstream SNI '%S' certificate '%d/%d' extension key usage: '%s'`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 33 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL SNI 'www.example.com' certificate '1/3' extension key usage: 'Digital Signature, Key Encipherment'`

<h3>SSL Upstream Certificate Extension SAN(MSG-ID: 34)</h3>

* `<134>1 %Z - enlighten - 34 - BOM%P and %P SSL upstream SNI '%S' certificate '%d/%d' extension SAN, DNS: '%s', IPv4: '%s', IPv6: '%s'`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 34 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL SNI 'www.example.com' certificate '1/3' extension SAN, DNS: 'cloudflare-dns.com, *.cloudflare-dns.com, one.one.one.one', IPv4: '1.1.1.1, 1.0.0.1, 162.159.132.53, 162.159.36.1, 162.159.46.1', IPv6: '2606:4700:4700::1111, 2606:4700:4700::1001, 2606:4700:4700::64, 2606:4700:4700::6400'`
* `<134>1 %Z - enlighten - 34 - BOM%P and %P SSL upstream SNI '%S' certificate '%d/%d' extension SAN, DNS: 'www.cht.com.tw, eshop.cht.com.tw, eshop2.cht.com.tw, eshop3.cht.com.tw, handicapfree.cht.com.tw', IPv4: '', IPv6: ''`

<h3>SSL Upstream Certificate Fingerprint SHA1(MSG-ID: 35)</h3>

* `<134>1 %Z - enlighten - 35 - BOM%P and %P SSL upstream SNI '%S' certificate '%d/%d' fingerprint(SHA1): '%s'`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 35 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL SNI 'www.example.com' certificate '1/3' fingerprint(SHA1): 'fd:54:e4:64:3b:49:70:5a:2a:ab:e5:06:53:c4:f5:6c2d:f8:07:3d'`

<h3>SSL Upstream Certificate Fingerprint SHA256(MSG-ID: 36)</h3>

* `<134>1 %Z - enlighten - 36 - BOM%P and %P SSL upstream SNI '%S' certificate '%d/%d' fingerprint(SHA256): '%s'`
* `<local0.info>1 2020-03-03T02:02:02.000012Z - enlighten - 36 - BOM[192.168.2.10]:46204 and [192.168.2.100]:443 SSL SNI 'www.example.com' certificate '1/3' fingerprint(SHA256): '8e:7c:d0:27:7d:0f:2d:1c:2e:93:45:5c:6f:19:08:69df:64:8b:20:ee:5f:77:4c:7d:d8:cb:cc:65:83:17:73'`
