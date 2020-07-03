nwctl Configuration
==============

Configuration
-----------

<h3>Core</h3>

|         Key         |        Prompt        | Json Type |              Style              |    Validation   |            Note            |
|:-------------------:|:--------------------:|:---------:|:-------------------------------:|:---------------:|:--------------------------:|
|      MessageLog     |      Message Log     |  Boolean  |             Checkbox            |        -        |              -             |
|       ErrorLog      |       Error Log      |  Boolean  |             Checkbox            |        -        |              -             |
| ManagementInterface | Management Interface |   String  |                -                |        -        | Don't Change Default Value |
|     IPv4Address     |     IPv4 Address     |   Array   | Textarea(IP/slash per One Line) | IPv4 with Slash |              -             |
|  DefaultIPv4Gateway | Default IPv4 Gateway |   Array   |    Textarea(IP per One Line)    |       IPv4      |              -             |
|      DNSServer      |      DNS Server      |   Array   |    Textarea(IP per One Line)    |       IPv4      |              -             |
|      NTPServer      |      NTP Server      |   Array   | Textarea(Hostname per One Line) |        -        |              -             |
