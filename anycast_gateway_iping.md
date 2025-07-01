# Anycast Gateway iping

https://community.cisco.com/t5/application-centric-infrastructure/how-does-aci-iping-work-when-i-use-pervasive-gateway-as-source/td-p/4741758

```
MXS2-L103# acidiag fnvread | egrep "101|103"
     101        1            MXS2-L101      FDO204520TY     10.2.160.66/32    leaf         active   0
     103        1            MXS2-L103      FDO25210JA1     10.2.160.67/32    leaf         active   0
MXS2-L103# 
```

LEAF 103 TEP 10.2.160.67 to hex 0A.02.A0.43

LEAF 101 TEP 10.2.160.66 to hex 0A.02.A0.42

```
MXS2-L103# show system internal epm endpoint ip 10.12.62.5

MAC : 40ce.2491.5741 ::: Num IPs : 1
IP# 0 : 10.12.62.5 ::: IP# 0 flags :  ::: l3-sw-hit: No
Vlan id : 60 ::: Vlan vnid : 14104 ::: VRF name : vmenchac_PROD:VRF1
BD vnid : 16383923 ::: VRF vnid : 2392065
Phy If : 0x1a00b000 ::: Tunnel If : 0
Interface : Ethernet1/12
Flags : 0x80004c04 ::: sclass : 49154 ::: Ref count : 5
EP Create Timestamp : 07/01/2025 16:48:40.191362
EP Update Timestamp : 07/01/2025 16:59:36.924174
EP Flags : local|IP|MAC|sclass|timer|

::::


MXS2-L103# 
```

## PING sourced from leaf 103 (endpoint is local)
```
MXS2-L103# iping 10.12.62.5 -V vmenchac_PROD:VRF1  -S 10.12.62.254 -c 1
PING 10.12.62.5 (10.12.62.5) from 10.12.62.254: 56 data bytes
64 bytes from 10.12.62.5: icmp_seq=0 ttl=255 time=1.355 ms
```
```
MXS2-L103# show ip int brief vrf vmenchac_PROD:VRF1
IP Interface Status for VRF "vmenchac_PROD:VRF1"(27)
Interface            Address              Interface Status
vlan59               10.12.62.254/24      protocol-up/link-up/admin-up

MXS2-L103# 
```
```
ACI-N3K-5# ethanalyzer local interface inband display-filter ip.addr==10.12.62.254 limit-captured-frames 0 detail 
Capturing on inband
wireshark-cisco-mtc-dissector: ethertype=0xde09, devicetype=0x0
Frame 2303 (102 bytes on wire, 102 bytes captured)
    Arrival Time: Jul  1, 2025 12:46:49.321747000
    [Time delta from previous captured frame: 0.165238000 seconds]
    [Time delta from previous displayed frame: 9.677173000 seconds]
    [Time since reference or first frame: 9.677173000 seconds]
    Frame Number: 2303
    Frame Length: 102 bytes
    Capture Length: 102 bytes
    [Frame is marked: False]
    [Protocols in frame: eth:vlan:ip:icmp:data]
Ethernet II, Src: 00:22:bd:f8:19:ff (00:22:bd:f8:19:ff), Dst: 40:ce:24:91:57:41 (40:ce:24:91:57:41)
    Destination: 40:ce:24:91:57:41 (40:ce:24:91:57:41)
        Address: 40:ce:24:91:57:41 (40:ce:24:91:57:41)
        .... ...0 .... .... .... .... = IG bit: Individual address (unicast)
        .... ..0. .... .... .... .... = LG bit: Globally unique address (factory default)
    Source: 00:22:bd:f8:19:ff (00:22:bd:f8:19:ff)
        Address: 00:22:bd:f8:19:ff (00:22:bd:f8:19:ff)
        .... ...0 .... .... .... .... = IG bit: Individual address (unicast)
        .... ..0. .... .... .... .... = LG bit: Globally unique address (factory default)
    Type: 802.1Q Virtual LAN (0x8100)
802.1Q Virtual LAN, PRI: 5, CFI: 0, ID: 1262
    101. .... .... .... = Priority: 5
    ...0 .... .... .... = CFI: 0
    .... 0100 1110 1110 = ID: 1262
    Type: IP (0x0800)
Internet Protocol, Src: 10.12.62.254 (10.12.62.254), Dst: 10.12.62.5 (10.12.62.5)
    Version: 4
    Header length: 20 bytes
    Differentiated Services Field: 0x14 (DSCP 0x05: Unknown DSCP; ECN: 0x00)
        0001 01.. = Differentiated Services Codepoint: Unknown (0x05)
        .... ..0. = ECN-Capable Transport (ECT): 0
        .... ...0 = ECN-CE: 0
    Total Length: 84
    Identification: 0x7cb0 (31920)
    Flags: 0x00
        0.. = Reserved bit: Not Set
        .0. = Don't fragment: Not Set
        ..0 = More fragments: Not Set
    Fragment offset: 0
    Time to live: 64
    Protocol: ICMP (0x01)
    Header checksum: 0x6cca [correct]
        [Good: True]
        [Bad : False]
    Source: 10.12.62.254 (10.12.62.254)
    Destination: 10.12.62.5 (10.12.62.5)
Internet Control Message Protocol
    Type: 8 (Echo (ping) request)
    Code: 0 ()
    Checksum: 0xcce4 [correct]
    Identifier: 0xc201
    Sequence number: 0 (0x0000)
    Data (56 bytes)

0000  0d 14 64 68 a5 89 08 00 da ab ac ab 0a 02 a0 43   ..dh...........C
0010  fe 65 ca ac ac ab 02 01 01 02 00 00 00 02 cd ab   .e..............
0020  00 00 cd ab 00 00 cd ab 00 00 cd ab 00 00 cd ab   ................
0030  00 00 cd ab 00 00 cd ab                           ........
        Data: 0D146468A5890800DAABACAB0A02A043FE65CAACACAB0201...
        [Length: 56]

Frame 2304 (102 bytes on wire, 102 bytes captured)
    Arrival Time: Jul  1, 2025 12:46:49.322136000
    [Time delta from previous captured frame: 0.000389000 seconds]
    [Time delta from previous displayed frame: 0.000389000 seconds]
    [Time since reference or first frame: 9.677562000 seconds]
    Frame Number: 2304
    Frame Length: 102 bytes
    Capture Length: 102 bytes
    [Frame is marked: False]
    [Protocols in frame: eth:vlan:ip:icmp:data]
Ethernet II, Src: 40:ce:24:91:57:41 (40:ce:24:91:57:41), Dst: 00:22:bd:f8:19:ff (00:22:bd:f8:19:ff)
    Destination: 00:22:bd:f8:19:ff (00:22:bd:f8:19:ff)
        Address: 00:22:bd:f8:19:ff (00:22:bd:f8:19:ff)
        .... ...0 .... .... .... .... = IG bit: Individual address (unicast)
        .... ..0. .... .... .... .... = LG bit: Globally unique address (factory default)
    Source: 40:ce:24:91:57:41 (40:ce:24:91:57:41)
        Address: 40:ce:24:91:57:41 (40:ce:24:91:57:41)
        .... ...0 .... .... .... .... = IG bit: Individual address (unicast)
        .... ..0. .... .... .... .... = LG bit: Globally unique address (factory default)
    Type: 802.1Q Virtual LAN (0x8100)
802.1Q Virtual LAN, PRI: 7, CFI: 0, ID: 1262
    111. .... .... .... = Priority: 7
    ...0 .... .... .... = CFI: 0
    .... 0100 1110 1110 = ID: 1262
    Type: IP (0x0800)
Internet Protocol, Src: 10.12.62.5 (10.12.62.5), Dst: 10.12.62.254 (10.12.62.254)
    Version: 4
    Header length: 20 bytes
    Differentiated Services Field: 0x14 (DSCP 0x05: Unknown DSCP; ECN: 0x00)
        0001 01.. = Differentiated Services Codepoint: Unknown (0x05)
        .... ..0. = ECN-Capable Transport (ECT): 0
        .... ...0 = ECN-CE: 0
    Total Length: 84
    Identification: 0xfcb0 (64688)
    Flags: 0x00
        0.. = Reserved bit: Not Set
        .0. = Don't fragment: Not Set
        ..0 = More fragments: Not Set
    Fragment offset: 0
    Time to live: 255
    Protocol: ICMP (0x01)
    Header checksum: 0x2dc9 [correct]
        [Good: True]
        [Bad : False]
    Source: 10.12.62.5 (10.12.62.5)
    Destination: 10.12.62.254 (10.12.62.254)
Internet Control Message Protocol
    Type: 0 (Echo (ping) reply)
    Code: 0 ()
    Checksum: 0xd4e4 [correct]
    Identifier: 0xc201
    Sequence number: 0 (0x0000)
    Data (56 bytes)

0000  0d 14 64 68 a5 89 08 00 da ab ac ab 0a 02 a0 43   ..dh...........C
0010  fe 65 ca ac ac ab 02 01 01 02 00 00 00 02 cd ab   .e..............
0020  00 00 cd ab 00 00 cd ab 00 00 cd ab 00 00 cd ab   ................
0030  00 00 cd ab 00 00 cd ab                           ........
        Data: 0D146468A5890800DAABACAB0A02A043FE65CAACACAB0201...
        [Length: 56]


2 packets captured
ACI-N3K-5# 
```
## PING sourced from leaf 101 (endpoint is remote)

```
MXS2-L101# iping 10.12.62.5 -V vmenchac_PROD:VRF1  -S 10.12.62.254 -c 1
PING 10.12.62.5 (10.12.62.5) from 10.12.62.254: 56 data bytes
64 bytes from 10.12.62.5: icmp_seq=0 ttl=255 time=1.649 ms
```
```
MXS2-L101# show ip int brief vrf vmenchac_PROD:VRF1
IP Interface Status for VRF "vmenchac_PROD:VRF1"(23)
Interface            Address              Interface Status
vlan22               10.12.62.254/24      protocol-up/link-up/admin-up
```
```
ACI-N3K-5# ethanalyzer local interface inband display-filter ip.addr==10.12.62.254 limit-captured-frames 0 detail 
Capturing on inband
wireshark-cisco-mtc-dissector: ethertype=0xde09, devicetype=0x0
Frame 1980 (102 bytes on wire, 102 bytes captured)
    Arrival Time: Jul  1, 2025 12:39:13.070022000
    [Time delta from previous captured frame: 0.055464000 seconds]
    [Time delta from previous displayed frame: 9.698773000 seconds]
    [Time since reference or first frame: 9.698773000 seconds]
    Frame Number: 1980
    Frame Length: 102 bytes
    Capture Length: 102 bytes
    [Frame is marked: False]
    [Protocols in frame: eth:vlan:ip:icmp:data]
Ethernet II, Src: 00:22:bd:f8:19:ff (00:22:bd:f8:19:ff), Dst: 40:ce:24:91:57:41 (40:ce:24:91:57:41)
    Destination: 40:ce:24:91:57:41 (40:ce:24:91:57:41)
        Address: 40:ce:24:91:57:41 (40:ce:24:91:57:41)
        .... ...0 .... .... .... .... = IG bit: Individual address (unicast)
        .... ..0. .... .... .... .... = LG bit: Globally unique address (factory default)
    Source: 00:22:bd:f8:19:ff (00:22:bd:f8:19:ff)
        Address: 00:22:bd:f8:19:ff (00:22:bd:f8:19:ff)
        .... ...0 .... .... .... .... = IG bit: Individual address (unicast)
        .... ..0. .... .... .... .... = LG bit: Globally unique address (factory default)
    Type: 802.1Q Virtual LAN (0x8100)
802.1Q Virtual LAN, PRI: 5, CFI: 0, ID: 1262
    101. .... .... .... = Priority: 5
    ...0 .... .... .... = CFI: 0
    .... 0100 1110 1110 = ID: 1262
    Type: IP (0x0800)
Internet Protocol, Src: 10.12.62.254 (10.12.62.254), Dst: 10.12.62.5 (10.12.62.5)
    Version: 4
    Header length: 20 bytes
    Differentiated Services Field: 0x14 (DSCP 0x05: Unknown DSCP; ECN: 0x00)
        0001 01.. = Differentiated Services Codepoint: Unknown (0x05)
        .... ..0. = ECN-Capable Transport (ECT): 0
        .... ...0 = ECN-CE: 0
    Total Length: 84
    Identification: 0x0f77 (3959)
    Flags: 0x00
        0.. = Reserved bit: Not Set
        .0. = Don't fragment: Not Set
        ..0 = More fragments: Not Set
    Fragment offset: 0
    Time to live: 63
    Protocol: ICMP (0x01)
    Header checksum: 0xdb03 [correct]
        [Good: True]
        [Bad : False]
    Source: 10.12.62.254 (10.12.62.254)
    Destination: 10.12.62.5 (10.12.62.5)
Internet Control Message Protocol
    Type: 8 (Echo (ping) request)
    Code: 0 ()
    Checksum: 0xbfbe [correct]
    Identifier: 0x2c01
    Sequence number: 0 (0x0000)
    Data (56 bytes)

0000  45 12 64 68 14 b3 04 00 da ab ac ab 0a 02 a0 42   E.dh...........B
0010  fe 65 ca ac ac ab 02 01 01 02 00 00 00 02 cd ab   .e..............
0020  00 00 cd ab 00 00 cd ab 00 00 cd ab 00 00 cd ab   ................
0030  00 00 cd ab 00 00 cd ab                           ........
        Data: 4512646814B30400DAABACAB0A02A042FE65CAACACAB0201...
        [Length: 56]

Frame 1981 (102 bytes on wire, 102 bytes captured)
    Arrival Time: Jul  1, 2025 12:39:13.070401000
    [Time delta from previous captured frame: 0.000379000 seconds]
    [Time delta from previous displayed frame: 0.000379000 seconds]
    [Time since reference or first frame: 9.699152000 seconds]
    Frame Number: 1981
    Frame Length: 102 bytes
    Capture Length: 102 bytes
    [Frame is marked: False]
    [Protocols in frame: eth:vlan:ip:icmp:data]
Ethernet II, Src: 40:ce:24:91:57:41 (40:ce:24:91:57:41), Dst: 00:22:bd:f8:19:ff (00:22:bd:f8:19:ff)
    Destination: 00:22:bd:f8:19:ff (00:22:bd:f8:19:ff)
        Address: 00:22:bd:f8:19:ff (00:22:bd:f8:19:ff)
        .... ...0 .... .... .... .... = IG bit: Individual address (unicast)
        .... ..0. .... .... .... .... = LG bit: Globally unique address (factory default)
    Source: 40:ce:24:91:57:41 (40:ce:24:91:57:41)
        Address: 40:ce:24:91:57:41 (40:ce:24:91:57:41)
        .... ...0 .... .... .... .... = IG bit: Individual address (unicast)
        .... ..0. .... .... .... .... = LG bit: Globally unique address (factory default)
    Type: 802.1Q Virtual LAN (0x8100)
802.1Q Virtual LAN, PRI: 7, CFI: 0, ID: 1262
    111. .... .... .... = Priority: 7
    ...0 .... .... .... = CFI: 0
    .... 0100 1110 1110 = ID: 1262
    Type: IP (0x0800)
Internet Protocol, Src: 10.12.62.5 (10.12.62.5), Dst: 10.12.62.254 (10.12.62.254)
    Version: 4
    Header length: 20 bytes
    Differentiated Services Field: 0x14 (DSCP 0x05: Unknown DSCP; ECN: 0x00)
        0001 01.. = Differentiated Services Codepoint: Unknown (0x05)
        .... ..0. = ECN-Capable Transport (ECT): 0
        .... ...0 = ECN-CE: 0
    Total Length: 84
    Identification: 0x8f77 (36727)
    Flags: 0x00
        0.. = Reserved bit: Not Set
        .0. = Don't fragment: Not Set
        ..0 = More fragments: Not Set
    Fragment offset: 0
    Time to live: 255
    Protocol: ICMP (0x01)
    Header checksum: 0x9b02 [correct]
        [Good: True]
        [Bad : False]
    Source: 10.12.62.5 (10.12.62.5)
    Destination: 10.12.62.254 (10.12.62.254)
Internet Control Message Protocol
    Type: 0 (Echo (ping) reply)
    Code: 0 ()
    Checksum: 0xc7be [correct]
    Identifier: 0x2c01
    Sequence number: 0 (0x0000)
    Data (56 bytes)

0000  45 12 64 68 14 b3 04 00 da ab ac ab 0a 02 a0 42   E.dh...........B
0010  fe 65 ca ac ac ab 02 01 01 02 00 00 00 02 cd ab   .e..............
0020  00 00 cd ab 00 00 cd ab 00 00 cd ab 00 00 cd ab   ................
0030  00 00 cd ab 00 00 cd ab                           ........
        Data: 4512646814B30400DAABACAB0A02A042FE65CAACACAB0201...
        [Length: 56]


427 packets dropped
2 packets captured
```
ACI-N3K-5# 
