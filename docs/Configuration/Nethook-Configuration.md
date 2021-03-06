Nethook Configuration
===============

Configuration
-----------

<h3>Core</h3>

|             Key            |            Prompt            |    Json Type    |      Style      |   Validation   |            Note            |
|:--------------------------:|:----------------------------:|:---------------:|:---------------:|:--------------:|:--------------------------:|
|         MessageLog         |          Message Log         |     Boolean     |     Checkbox    |        -       |              -             |
|          ErrorLog          |           Error Log          |     Boolean     |     Checkbox    |        -       |              -             |
|           MaxCore          |               -              |     Integer     |        -        |        -       | Don't Change Default Value |
|             LAN            |              LAN             |      String     |  Select Option  |        -       |              -             |
|             WAN            |              WAN             |      String     |  Select Option  |        -       |              -             |
|             TAP            |               -              |      String     |        -        |        -       | Don't Change Default Value |
|        PacketModule        |               -              |      String     |        -        |        -       | Don't Change Default Value |
|             MTU            |              MTU             |     Integer     | Textbox(Number) |  1000 to 1500  |              -             |
|      TrackingTableName     |               -              |      String     |        -        |        -       | Don't Change Default Value |
|     ExternalIpv4Address    |               -              | Array of String |        -        |        -       | Don't Change Default Value |
|     ExternalIpv6Address    |               -              | Array of String |        -        |        -       | Don't Change Default Value |
|          ARPCache          |               -              |     Boolean     |        -        |        -       | Don't Change Default Value |
|          NDPCache          |               -              |     Boolean     |        -        |        -       | Don't Change Default Value |
|       GracefulTimeout      |       Graceful Timeout       |     Integer     | Textbox(Number) | Greater Than 0 |              -             |
|      EnableUDPRedirect     |      Enable UDP Redirect     |     Boolean     |     Checkbox    |        -       |              -             |
|   TCPSegmentationOffload   |   TCP Segmentation Offload   |     Boolean     |     Checkbox    |        -       |              -             |
|   UDPFragmentationOffload  |   UDP Fragmentation Offload  |     Boolean     |     Checkbox    |        -       |              -             |
| GenericSegmentationOffload | Generic Segmentation Offload |     Boolean     |     Checkbox    |        -       |              -             |
|    GenericReceiveOffload   |    Generic Receive Offload   |     Boolean     |     Checkbox    |        -       |              -             |
|     LargeReceiveOffload    |     Large Receive Offload    |     Boolean     |     Checkbox    |        -       |              -             |
|      TCPRedirectPolicy     |      TCP Reidrect Policy     |      Object     |        -        |   Must Exist   |    See [Policy](#policy)   |
|      SSLRedirectPolicy     |      SSL Redirect Policy     |      Object     |        -        |   Must Exist   |    See [Policy](#policy)   |
|       UDPRejectPolicy      |       UDP Reject Policy      |      Object     |        -        |   Must Exist   |    See [Policy](#policy)   |
|      UDPRedirectPolicy     |      UDP Redirect Policy     |      Object     |        -        |   Must Exist   |    See [Policy](#policy)   |

<h3 id="policy">Policy</h3>

|      Key     |     Prompt    |    Json Type    |      Style      | Validation |              Note             |
|:------------:|:-------------:|:---------------:|:---------------:|:----------:|:-----------------------------:|
|      LAN     |      LAN      | Array of Object |        -        | Must Exist |    See [4-Tuple](#4_tuple)    |
|      WAN     |      WAN      | Array of Object |        -        | Must Exist |    See [4-Tuple](#4_tuple)    |
| RedirectPort | Redirect Port |     Integer     | Textbox(Number) |   0-65535  | Don't Show on UDPRejectPolicy |

<h3 id="4_tuple">4-Tuple</h3>

|          Key         |         Prompt         |              Json Type              |            Style            |  Validation  |              Note             |
|:--------------------:|:----------------------:|:-----------------------------------:|:---------------------------:|:------------:|:-----------------------------:|
|    SourceIpAddress   |    Source IP Address   |           Array of String           |  Textarea(IP per One Line)  | IPv4 or IPv6 |               -               |
|      SourcePort      |       Source Port      | Array of String or Array of Integer | Textarea(Port per One Line) |  0 to 65535  | Prefer Submit Array of String |
| DestinationIpAddress | Destination IP Address |           Array of String           |  Textarea(IP per One Line)  | IPv4 or IPv6 |               -               |
|    DestinationPort   |    Destination Port    |  Arrayof String or Array of Integer | Textarea(Port per One Line) |  0 to 65535  | Prefer Submit Array of String |
