## Intro

Wireshark Notes.

### Interface Overview
#### Packet List Column:
- `No.` : The index number of the packet in this packet capture file
- `Time`: The timestamp of the packet
- `Source`: The source IP address
- `Destination`: The destination IP address
- `Protocol`: The protocol contained in the packet
- `Length`: The total length of the packet
- `Info`: Some infomation about the data in the packet (the payload) as interpreted by Wireshark
#### Others:
- `Apply a display filter ...<Ctrl-/>` : Enter Wireshark display filters here(Filter Commands)

### Basic Filter Commands

`ip.addr == 'IP Address'`
- filter for traffic associated with a specific IP address
- example: `ip.addr == 127.0.0.1`

`ip.src == 'IP Address'`
- filter to select traffic for a specific source IP address only
- example: `ip.src == 127.0.0.1`

`ip.dst == 'IP Address'`
- filter to select traffic for a specific destination IP address only
- example: `ip.dst == 127.0.0.1`

`eth.addr == 'MAC Address'`
- filter to select traffic to or from a specific Ethernet MAC address
- example: `eth.addr == FF:FF:FF:FF:FF:FF` 

`udp.port == 'Port Number'`
- filter to select UDP specific port traffic
- example: `udp.port == 53` (Port 53 = Domain Name System)

`tcp.port == 'Port Number'`
- filter to select TCP specific port traffic
-  example: `tcp.port == 80` (Port 80 = unencrypted HTTP)

`'protocol' contains "text"`
- filter to select protocol packet data that contains specific text data.
- example: `tcp contains "curl"` (filter to select TCP packet data that contains 'curl')


## Double-click a subtree

### Network Packet Details Explained:
#### Three Common Subtree
##### Frame 1 : 
>This provides you with details about the overall network packet, or frame, including the **frame length and the arrival time of the packet**. At this level,you’re viewing information about the entire packet of data.
- Encapsulation type
- Arrival Time
- Frame Length
##### Ethernet II : 
>This item contains details about the packet at the Ethernet level, including the **source and destination MAC addresses** and the **type of internal protocol** that the Ethernet packet contains.
##### Internet Protocol Version 4 : 
>This provides packet data about the Internet Protocol (IP) data contained in the Ethernet packet. It contains information such as the **source and destination IP addresses** and the Internal Protocol (for example, TCP or UDP), which is carried inside the IP packet.
- Version
- Header length
- Time to Live
- Protocol
- Header Checksum
- Source Address
- Destination Address
#### Various Subtree(Depends On The Protocol):
##### Protocol : 
>This provides **detailed information about the specific protocol** packet.


