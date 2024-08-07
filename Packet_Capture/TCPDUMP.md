# TCPDUMP on SWITCHES

Similar to Ethanalyzer in NXOS, only control plane traffic on the switch (seen by the CPU).

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

