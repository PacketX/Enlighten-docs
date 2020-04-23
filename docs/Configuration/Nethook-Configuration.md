Nethook Configuration
===============

Example
---------

```
{
    "MessageLog": true,
    "ErrorLog": true,
    "MaxCore": 1,
    "LAN": "P0",
    "WAN": "P3",
    "TAP": "pktx0",
    "PacketModule": "pfpacket_ring",
    "MTU": 1450,
    "TrackingTableName": "ST1",
    "ExternalIpv4Address": [Don't Change Default Value
    ],
    "ExternalIpv6Address": [
    ],
    "ARPCache": false,
    "NDPCache": false,

    /* TCP */
    "TCPRedirectPolicy": {
        "LAN": [
            {
                "SourceIpAddress": [],
                "SourcePort": [],
                "DestinationIpAddress": [],
                "DestinationPort": [ 80 ]
            }
        ],
        "WAN": [
            {
                "SourceIpAddress": [],
                "SourcePort": [ 80 ],
                "DestinationIpAddress": [],
                "DestinationPort": []
            }
        ],
        "RedirectPort": 3128
    },
    /* TCP-SSL */
    "SSLRedirectPolicy": {
        "LAN": [
            {
                "SourceIpAddress": [],
                "SourcePort": [],
                "DestinationIpAddress": [],
                "DestinationPort": [ 443 ]
            }
        ],
        "WAN": [
            {
                "SourceIpAddress": [],
                "SourcePort": [ 443 ],
                "DestinationIpAddress": [],
                "DestinationPort": []
            }
        ],
        "RedirectPort": 3129
    },
    /* UDP-gQUIC */
    "UDPDropPolicy": {
        "LAN": [
            {
                "SourceIpAddress": [],
                "SourcePort": [],
                "DestinationIpAddress": [],
                "DestinationPort": [ 443 ]
            }
        ],
        "WAN": [
            {
                "SourceIpAddress": [],
                "SourcePort": [ 443 ],
                "DestinationIpAddress": [],
                "DestinationPort": []
            }
        ]
    }
}
```

Configuration
-----------

<h3>Core</h3>

|         Key         |        Prompt       |    Json Type    |      Style      |                   Validation                   |            Note            |
|:-------------------:|:-------------------:|:---------------:|:---------------:|:----------------------------------------------:|:--------------------------:|
|      MessageLog     |     Message Log     |     Boolean     |     Checkbox    |                        -                       |              -             |
|       ErrorLog      |      Error Log      |     Boolean     |     Checkbox    |                        -                       |              -             |
|       MaxCore       |          -          |     Integer     |        -        |                 Must equal to 1                |              -             |
|         LAN         |      LAN     |      String     |  Select Option  | All AliasName Value of [GET /template/interface](05.Template.md#wizard_step2) |              -             |
|         WAN         |       WAN      |      String     |  Select Option  | All AliasName Value of [GET /template/interface](05.Template.md#wizard_step2) |              -             |
|         TAP         |          -          |      String     |        -        |                        -                       | Don't Change Default Value |
|     PacketModule    |          -          |      String     |        -        |                        -                       | Don't Change Default Value |
|         MTU         |         MTU         |     Integer     | Textbox(Number) |                  1000 to 1500                  |              -             |
|  TrackingTableName  |          -          |      String     |        -        |                        -                       | Don't Change Default Value |
| ExternalIpv4Address |          -          | Array of String |        -        |                        -                       | Don't Change Default Value |
| ExternalIpv6Address |          -          | Array of String |        -        |                        -                       | Don't Change Default Value |
|       ARPCache      |          -          |     Boolean     |        -        |                        -                       | Don't Change Default Value |
|       NDPCache      |          -          |     Boolean     |        -        |                        -                       | Don't Change Default Value |
|  TCPRedirectPolicy  | TCP Reidrect Policy |      Object     |        -        |                        Must Exist                       |    See [Policy](#policy)   |
|  SSLRedirectPolicy  | SSL Redirect Policy |      Object     |        -        |                        Must Exist                       |    See [Policy](#policy)   |
|  UDPDropPolicy  | UDP Drop Policy |      Object     |        -        |                        Must Exist                       |    See [Policy](#policy)   |

<h3 id="policy">Policy</h3>

|      Key     |     Prompt    |    Json Type    |      Style      | Validation |             Note            |
|:------------:|:-------------:|:---------------:|:---------------:|:----------:|:---------------------------:|
|      LAN     |   LAN  | Array of Object |        -        |      Must Exist     |   See [4-Tuple](#4_tuple)   |
|      WAN     |   WAN  | Array of Object |        -        |      Must Exist     |   See [4-Tuple](#4_tuple)   |
| RedirectPort | Redirect Port |     Integer     | Textbox(Number) |   0-65535  | Don't Show on UDPDropPolicy |

<h3 id="4_tuple">4-Tuple</h3>

|          Key         |         Prompt         |              Json Type              |            Style            |  Validation  |              Note             |
|:--------------------:|:----------------------:|:-----------------------------------:|:---------------------------:|:------------:|:-----------------------------:|
|    SourceIpAddress   |    Source IP Address   |           Array of String           |  Textarea(IP per One Line)  | IPv4 or IPv6 |               -               |
|      SourcePort      |       Source Port      | Array of String or Array of Integer | Textarea(Port per One Line) |  0 to 65535  | Prefer Submit Array of String |
| DestinationIpAddress | Destination IP Address |           Array of String           |  Textarea(IP per One Line)  | IPv4 or IPv6 |               -               |
|    DestinationPort   |    Destination Port    |  Arrayof String or Array of Integer | Textarea(Port per One Line) |  0 to 65535  | Prefer Submit Array of String |
