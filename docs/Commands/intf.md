intf
=========

網路卡介面管理，以`Enlighten`可用介面為主。

Help
-----------

```
$ intf help
Usage: intf [GROUP] [OPTION...]
Network interface information for Enlighten

List available network interface infromation
    list
        --json,       -j    output in json format
        --interface,  -i    interface name, alias name is also works

List TUN/TAP interface information
    tap
        --json,       -j    output in json format
        --interface,  -i    interface name, alias name is also works

Retrieve network interface statistics
    statistics
        --json,       -j    output in json format
        --interface,  -i    interface name, alias name is also works

Print the help
    help

Report bugs to <tubear.chen@packetx.biz>.
```

Example 1 列出`Enlighten`可用的網路卡資訊
----------

```
$ intf list
Index: 0
Name: eth1
Alias name: P0
MAC address: 00:50:56:26:a3:ae
Driver name: e1000
Driver version: 7.3.21-k8-NAPI
Firmware version: 
Bus info: 0000:02:05.0
Up: yes
Promiscuous: no
ARP: yes
TCP segmentation offload: yes
UDP fragmentation offload: no
Generic segmentation offload: yes
Generic receive offload: no
Large receive offload: no
MTU: 1500

Index: 1
Name: eth2
Alias name: P1
MAC address: 00:50:56:2c:c4:3a
Driver name: e1000
Driver version: 7.3.21-k8-NAPI
Firmware version: 
Bus info: 0000:02:06.0
Up: yes
Promiscuous: no
ARP: yes
TCP segmentation offload: yes
UDP fragmentation offload: no
Generic segmentation offload: yes
Generic receive offload: yes
Large receive offload: no
MTU: 1500

...
```

Example 2 列出特定網路卡資訊
-----------

```
$ intf list --interface eth4
Index: 3
Name: eth4
Alias name: P3
MAC address: 00:0c:29:8c:5a:3e
Driver name: e1000
Driver version: 7.3.21-k8-NAPI
Firmware version: 
Bus info: 0000:02:08.0
Up: yes
Promiscuous: no
ARP: yes
TCP segmentation offload: yes
UDP fragmentation offload: no
Generic segmentation offload: yes
Generic receive offload: no
Large receive offload: no
MTU: 1500

[enlighten@enlighten Enlighten]$ intf list --interface P2
Index: 2
Name: eth3
Alias name: P2
MAC address: 00:0c:29:8c:5a:34
Driver name: e1000
Driver version: 7.3.21-k8-NAPI
Firmware version: 
Bus info: 0000:02:07.0
Up: yes
Promiscuous: no
ARP: yes
TCP segmentation offload: yes
UDP fragmentation offload: no
Generic segmentation offload: yes
Generic receive offload: no
Large receive offload: no
MTU: 1500

$ intf list --interface P6 --json
{
   "InterfaceInfo": [
     {
       "Index": 6,
       "Name": "eth7",
       "AliasName": "P6",
       "MACAddress": "00:0c:29:8c:5a:5c",
       "Up": true,
       "TCPSegmentationOffload": true,
       "UDPFragmentationOffload": false,
       "GenericSegmentationOffload": true,
       "GenericReceiveOffload": true,
       "LargeReceiveOffload": false,
       "MTU": 1500
     }
   ]
 }
```

可接受別名。

Example 3 列出tun/tap虛擬網路卡資訊
-----------

```
$ intf tap --interface pktx1
Index: 0
Name: pktx1
MAC address: f6:37:6a:c8:fe:01
Driver name: tun
Driver version: 1.6
Firmware version: 
Bus info: tap
Up: yes
Promiscuous: no
ARP: yes
TCP Segmentation Offload: no
UDP Fragmentation Offload: no
Generic Segmentation Offload: yes
Generic Receive Offload: yes
Large Receive Offload: no
MTU: 1450

$ intf tap --interface pktx1 --json
{
   "InterfaceInfo": [
     {
       "Index": 0,
       "Name": "pktx1",
       "MACAddress": "f6:37:6a:c8:fe:01",
       "Up": true,
       "TCPSegmentationOffload": false,
       "UDPFragmentationOffload": false,
       "GenericSegmentationOffload": true,
       "GenericReceiveOffload": true,
       "LargeReceiveOffload": false,
       "MTU": 1450
     }
   ]
 }
```

Example 4 取回網路卡系統統計資訊
-----------

```
$ intf statistics --interface P0
Name: eth1
Alias name: P0
Receive count: 0
Send count: 66881
Receive bytes: 0
Send bytes: 13732742
Receive error: 0
Send error: 0
Receive drop: 0
Send drop: 0
Receive collision: 0
Receive length error: 0
Receive overflow error: 0
Receive CRC error: 0
Receive frame error: 0
Receive FIFO error: 0
Receive miss error: 0
Send aborted error: 0
Send carrier error: 0
Send FIFO error: 0
Send heartbeat error: 0
Send window error: 0
Receive compressed: 0
Send compressed: 0

$ intf statistics --interface pktx1 --json
{
   "Name": "pktx1",
   "AliasName": "pktx1",
   "ReceiveCount": 0,
   "SendCount": 16,
   "ReceiveBytes": 0,
   "SendBytes": 1280,
   "ReceiveError": 0,
   "SendError": 0,
   "ReceiveDrop": 0,
   "SendDrop": 0,
   "ReceiveCollision": 0,
   "ReceiveLengthError": 0,
   "ReceiveOverflowError": 0,
   "ReceiveCRCError": 0,
   "ReceiveFrameError": 0,
   "ReceiveFIFOError": 0,
   "ReceiveMissError": 0,
   "SendAbortedError": 0,
   "SendCarrierError": 0,
   "SendFIFOError": 0,
   "SendHeartbeatError": 0,
   "SendWindowError": 0,
   "ReceiveCompressed": 0,
   "SendCompressed": 0
 }
```
