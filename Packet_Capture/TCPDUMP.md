# TCPDUMP on SWITCHES

Similar to Ethanalyzer in NXOS, only control plane traffic on the switch (seen by the CPU).
```
tcpdump -i kpm_inb host 3.3.3.3
tcpdump -i kpm_inb host 3.3.3.3 -nn
tcpdump -ni kpm_inb icmp
tcpdump -i kpm_inb host 3.3.3.3 and host 1.1.1.1
```
To save in a PCAP file
```
MXS2-LF101# tcpdump -i kpm_inb -w /data/techsupport/test.pcap
tcpdump: listening on kpm_inb, link-type EN10MB (Ethernet), capture size 262144 bytes 
```
```
MXS2-LF104#  tcpdump -ni kpm_inb icmp
tcpdump: verbose output suppressed, use -v or -vv for full protocol decode
listening on kpm_inb, link-type EN10MB (Ethernet), capture size 262144 bytes
06:28:20.601101 IP 10.0.1.2 > 10.0.1.254: ICMP echo request, id 64575, seq 0, length 64
21:46:40.639301 IP 10.0.1.254 > 10.0.1.2: ICMP echo reply, id 64575, seq 0, length 64
06:28:20.601124 IP 10.0.1.2 > 10.0.1.254: ICMP echo request, id 64575, seq 256, length 64
21:46:40.640368 IP 10.0.1.254 > 10.0.1.2: ICMP echo reply, id 64575, seq 256, length 64
06:28:20.601165 IP 10.0.1.2 > 10.0.1.254: ICMP echo request, id 64575, seq 512, length 64
21:46:40.641349 IP 10.0.1.254 > 10.0.1.2: ICMP echo reply, id 64575, seq 512, length 64
06:28:20.603909 IP 10.0.1.2 > 10.0.1.254: ICMP echo request, id 64575, seq 768, length 64
21:46:40.642422 IP 10.0.1.254 > 10.0.1.2: ICMP echo reply, id 64575, seq 768, length 64
06:28:20.625398 IP 10.0.1.2 > 10.0.1.254: ICMP echo request, id 64575, seq 1024, length 64
21:46:40.643463 IP 10.0.1.254 > 10.0.1.2: ICMP echo reply, id 64575, seq 1024, length 64
^C
10 packets captured
10 packets received by filter
0 packets dropped by kernel
MXS2-LF104# 
```
### Interface where you can take the capture
```
MXS2-LF101# tcpdump -D
1.eth0 [Up, Running]
2.psdev0 [Up, Running]
3.kpm_inb [Up, Running]
4.kpm_mgmt [Up, Running]
5.tahoe0 [Up, Running]
6.psdev2 [Up, Running]
7.any (Pseudo-device that captures on all interfaces) [Up, Running]
8.lo [Up, Running, Loopback]
9.inband_lo [Up]
10.inband_hi [Up]
11.mgmt0 [Up]
12.bluetooth-monitor (Bluetooth Linux Monitor)
13.usbmon1 (USB bus number 1)
MXS2-LF101# 
```
### Disable IP/port to names
By default, tcpdump resolves IP addresses and ports into names, as shown in the previous example. When troubleshooting network issues, it is often easier to use the IP addresses and port numbers; disable name resolution by using the option -n and port resolution with -nn:
```
MXS2-LF101# tcpdump -i kpm_inb host 3.3.3.3
tcpdump: verbose output suppressed, use -v or -vv for full protocol decode
listening on kpm_inb, link-type EN10MB (Ethernet), capture size 262144 bytes
06:25:49.822106 IP 3.3.3.3.bgp > 1.1.1.1.36239: Flags [P.], seq 3627584694:3627584715, ack 4092013969, win 7300, length 21: BGP
22:21:12.183616 IP 1.1.1.1.36239 > 3.3.3.3.bgp: Flags [.], ack 21, win 7568, length 0
06:25:57.108188 IP 3.3.3.3.bgp > 1.1.1.1.36239: Flags [F.], seq 21, ack 1, win 7300, length 0
22:21:17.191527 IP 1.1.1.1.36239 > 3.3.3.3.bgp: Flags [F.], seq 1, ack 22, win 7568, length 0
06:25:57.511142 IP 3.3.3.3.bgp > 1.1.1.1.36239: Flags [.], ack 2, win 7300, length 0
06:26:12.233530 IP 3.3.3.3.18369 > 1.1.1.1.bgp: Flags [S], seq 42090404, win 29200, options [mss 1460,sackOK,TS val 198795252 ecr 0,nop,wscale 2], length 0
22:21:22.945667 IP 1.1.1.1.bgp > 3.3.3.3.18369: Flags [S.], seq 3716451542, ack 42090405, win 29200, options [mss 1460,nop,nop,sackOK,nop,wscale 2], length 0
06:26:12.233608 IP 3.3.3.3.18369 > 1.1.1.1.bgp: Flags [.], ack 1, win 7300, length 0
22:21:22.946493 IP 1.1.1.1.bgp > 3.3.3.3.18369: Flags [P.], seq 1:67, ack 1, win 7300, length 66: BGP
06:26:12.233647 IP 3.3.3.3.18369 > 1.1.1.1.bgp: Flags [.], ack 67, win 7300, length 0
06:26:12.263553 IP 3.3.3.3.18369 > 1.1.1.1.bgp: Flags [P.], seq 1:77, ack 67, win 7300, length 76: BGP
22:21:23.403531 IP 1.1.1.1.bgp > 3.3.3.3.18369: Flags [.], ack 77, win 7300, length 0
06:26:12.267975 IP 3.3.3.3.18369 > 1.1.1.1.bgp: Flags [P.], seq 77:96, ack 67, win 7300, length 19: BGP
22:21:23.403596 IP 1.1.1.1.bgp > 3.3.3.3.18369: Flags [.], ack 96, win 7300, length 0
22:21:23.403636 IP 1.1.1.1.bgp > 3.3.3.3.18369: Flags [P.], seq 67:86, ack 96, win 7300, length 19: BGP
06:26:12.631195 IP 3.3.3.3.18369 > 1.1.1.1.bgp: Flags [.], ack 86, win 7300, length 0
22:21:24.412086 IP 1.1.1.1.bgp > 3.3.3.3.18369: Flags [P.], seq 86:194, ack 96, win 7300, length 108: BGP
06:26:15.363403 IP 3.3.3.3.18369 > 1.1.1.1.bgp: Flags [.], ack 194, win 7300, length 0
06:26:15.451855 IP 3.3.3.3.18369 > 1.1.1.1.bgp: Flags [P.], seq 96:198, ack 194, win 7300, length 102: BGP
22:21:24.451082 IP 1.1.1.1.bgp > 3.3.3.3.18369: Flags [.], ack 198, win 7300, length 0
^C
20 packets captured
20 packets received by filter
0 packets dropped by kernel
MXS2-LF101# 
MXS2-LF101# tcpdump -i kpm_inb host 3.3.3.3 -nn
tcpdump: verbose output suppressed, use -v or -vv for full protocol decode
listening on kpm_inb, link-type EN10MB (Ethernet), capture size 262144 bytes
06:26:30.349283 IP 3.3.3.3.18369 > 1.1.1.1.179: Flags [P.], seq 42090602:42090623, ack 3716451736, win 7300, length 21: BGP
22:21:34.901289 IP 1.1.1.1.179 > 3.3.3.3.18369: Flags [.], ack 21, win 7300, length 0
06:26:30.353936 IP 3.3.3.3.18369 > 1.1.1.1.179: Flags [F.], seq 21, ack 1, win 7300, length 0
22:21:39.907858 IP 1.1.1.1.179 > 3.3.3.3.18369: Flags [F.], seq 1, ack 22, win 7300, length 0
06:26:30.354036 IP 3.3.3.3.18369 > 1.1.1.1.179: Flags [.], ack 2, win 7300, length 0
06:26:49.065039 IP 3.3.3.3.53386 > 1.1.1.1.179: Flags [S], seq 891375862, win 29200, options [mss 1460,sackOK,TS val 198801843 ecr 0,nop,wscale 2], length 0
22:21:44.915603 IP 1.1.1.1.179 > 3.3.3.3.53386: Flags [S.], seq 906029737, ack 891375863, win 29200, options [mss 1460,nop,nop,sackOK,nop,wscale 2], length 0
06:26:49.065067 IP 3.3.3.3.53386 > 1.1.1.1.179: Flags [.], ack 1, win 7300, length 0
22:21:44.916247 IP 1.1.1.1.179 > 3.3.3.3.53386: Flags [P.], seq 1:67, ack 1, win 7300, length 66: BGP
06:26:49.065085 IP 3.3.3.3.53386 > 1.1.1.1.179: Flags [.], ack 67, win 7300, length 0
06:26:49.168928 IP 3.3.3.3.53386 > 1.1.1.1.179: Flags [P.], seq 1:77, ack 67, win 7300, length 76: BGP
22:21:45.357296 IP 1.1.1.1.179 > 3.3.3.3.53386: Flags [.], ack 77, win 7300, length 0
06:26:49.168978 IP 3.3.3.3.53386 > 1.1.1.1.179: Flags [P.], seq 77:96, ack 67, win 7300, length 19: BGP
22:21:45.357391 IP 1.1.1.1.179 > 3.3.3.3.53386: Flags [.], ack 96, win 7300, length 0
22:21:45.410561 IP 1.1.1.1.179 > 3.3.3.3.53386: Flags [P.], seq 67:86, ack 96, win 7300, length 19: BGP
06:26:49.169092 IP 3.3.3.3.53386 > 1.1.1.1.179: Flags [.], ack 86, win 7300, length 0
22:21:46.415858 IP 1.1.1.1.179 > 3.3.3.3.53386: Flags [P.], seq 86:194, ack 96, win 7300, length 108: BGP
06:26:49.188956 IP 3.3.3.3.53386 > 1.1.1.1.179: Flags [.], ack 194, win 7300, length 0
06:26:49.188987 IP 3.3.3.3.53386 > 1.1.1.1.179: Flags [P.], seq 96:198, ack 194, win 7300, length 102: BGP
22:21:46.418373 IP 1.1.1.1.179 > 3.3.3.3.53386: Flags [.], ack 198, win 7300, length 0
^C
20 packets captured
20 packets received by filter
0 packets dropped by kernel
MXS2-LF101# 
```
