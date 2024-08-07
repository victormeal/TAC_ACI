# ftriage

```
MXS2-AP001# ftriage route -ii LEAF:104 -dip 10.0.0.1 -sip 10.0.1.2
Starting ftriage
Log file name for the current run is: ftlog_2024-08-07-21-54-30-844.txt
2024-08-07 21:54:30,851 INFO     /controller/bin/ftriage route -ii LEAF:104 -dip 10.0.0.1 -sip 10.0.1.2
User: admin
Request password info for username: admin
Password: 
2024-08-07 21:55:01,364 INFO     ftriage:     main:2499 Invoking ftriage with username: admin
2024-08-07 21:55:44,142 INFO     ftriage:     fcls:2510 MXS2-LF104: Valid ELAM for asic:0 slice:0 srcid:98 pktid:374
2024-08-07 21:56:16,894 INFO     ftriage:     main:1314 L3 packet Seen on  MXS2-LF104 Ingress: Eth1/45 Egress: Eth1/53  Vnid: 2523146 
2024-08-07 21:56:16,895 INFO     ftriage:     main:1369 MXS2-LF104: Incoming Packet captured with [SIP:10.0.1.2, DIP:10.0.0.1] 
2024-08-07 21:56:30,524 INFO     ftriage:     main:1396 MXS2-LF104: Packet's egress outer [SIP:10.2.48.66, DIP:10.2.224.64] 
2024-08-07 21:56:30,525 INFO     ftriage:     main:1403 MXS2-LF104: Outgoing packet's Vnid: 2523146
2024-08-07 21:56:49,746 INFO     ftriage:     main:369  Computed ingress encap string vlan-2001
2024-08-07 21:56:54,532 INFO     ftriage:     main:480  Ingress BD(s) vmenchac_T01:vmenchac_bd_vlan2001
2024-08-07 21:56:54,533 INFO     ftriage:     main:491  Ingress Ctx: vmenchac_T01:vmenchac_vrf_01 Vnid: 2523146
2024-08-07 21:56:54,533 INFO     ftriage:     main:1616  Ig VRF Vnid: 2523146
2024-08-07 21:56:54,534 INFO     ftriage:     main:1660 SIP 10.0.1.2 DIP 10.0.0.1
2024-08-07 22:01:04,091 WARNING  ftriage:     misc:736  MXS2-LF104: Trouble getting the cores from the node
2024-08-07 22:01:04,092 WARNING  ftriage:     misc:736  MXS2-LF104: Trouble getting the cores from the node
2024-08-07 22:01:26,474 INFO     ftriage:  unicast:1615 MXS2-LF104: Enter dbg_sub_ig with cn HEA and inst: ig
2024-08-07 22:01:35,619 INFO     ftriage:  unicast:1996 MXS2-LF104: Dst EP is remote
2024-08-07 22:01:35,620 INFO     ftriage:  unicast:842  MXS2-LF104: Enter dbg_leaf_remote with cn HEA and inst: ig
2024-08-07 22:01:40,387 INFO     ftriage:     misc:907  MXS2-LF104: caller  unicast:979  DMAC(00:22:BD:F8:19:FF) same as RMAC(00:22:BD:F8:19:FF)
2024-08-07 22:01:40,388 INFO     ftriage:     misc:909  MXS2-LF104: L3 packet caller  unicast:986  getting routed/bounced in HEA
2024-08-07 22:01:52,892 INFO     ftriage:     misc:907  MXS2-LF104: caller  unicast:997  Dst IP is present in HEA L3 tbl
2024-08-07 22:02:05,624 INFO     ftriage:     misc:907  MXS2-LF104: caller  unicast:1055 RwDMAC DIPo(10.2.224.64) is one of dst TEPs ['10.2.224.64']
2024-08-07 22:03:09,839 INFO     ftriage:     main:1816 dbg_sub_ig function returned values on node MXS2-LF104 done False, nxt_nifs {MXS2-SP1002: ['Eth1/29', 'Eth1/32', 'Eth1/31']}, nxt_dbg_f_n nexthop, nxt_inst ig, eg_ifs Eth1/53, Vnid: 2523146
2024-08-07 22:03:09,842 INFO     ftriage:     main:972  Found peer-node MXS2-SP1002 and IF: Eth1/29 in candidate list
2024-08-07 22:04:29,486 INFO     ftriage:     fcls:2510 MXS2-SP1002: Valid ELAM for asic:0 slice:0 srcid:88 pktid:389
2024-08-07 22:04:30,689 INFO     ftriage:     main:1314 L3 packet Seen on  MXS2-SP1002 Ingress: Eth1/29 Egress: Eth1/7  Vnid: 2523146 
2024-08-07 22:04:30,690 INFO     ftriage:     main:1363 MXS2-SP1002: Incoming Packet captured with Outer [SIP:10.2.48.66, DIP:10.2.224.64] .... Inner [SIP:10.0.1.2, DIP:10.0.0.1]
2024-08-07 22:04:30,690 INFO     ftriage:     main:1403 MXS2-SP1002: Outgoing packet's Vnid: 2523146
2024-08-07 22:06:12,005 INFO     ftriage:      fib:749  MXS2-SP1002: Transit in spine
2024-08-07 22:06:48,744 WARNING  ftriage:     misc:736  MXS2-SP1002: Trouble getting the cores from the node
2024-08-07 22:06:48,744 WARNING  ftriage:     misc:736  MXS2-SP1002: Trouble getting the cores from the node
2024-08-07 22:06:48,745 INFO     ftriage:  unicast:2019 MXS2-SP1002: Enter dbg_sub_nexthop with cn BKY and inst: ig
2024-08-07 22:06:48,745 INFO     ftriage:  unicast:2033 MXS2-SP1002: Enter dbg_sub_nexthop with Transit inst: ig infra: False glbs.dipo: 10.2.224.64
2024-08-07 22:06:58,782 INFO     ftriage:  unicast:2258 MXS2-SP1002: EP is known in COOP (DIPo = 10.2.224.64)
2024-08-07 22:07:10,843 INFO     ftriage:  unicast:2333 MXS2-SP1002: Infra route 10.2.224.64 present in RIB
2024-08-07 22:07:53,149 INFO     ftriage:     main:1816 dbg_sub_nexthop function returned values on node MXS2-SP1002 done False, nxt_nifs {MXS2-LF102: ['Eth1/49', 'Eth1/50', 'Eth1/52'], MXS2-LF101: ['Eth1/50', 'Eth1/49', 'Eth1/52']}, nxt_dbg_f_n nexthop, nxt_inst eg, eg_ifs Eth1/7, Vnid: 2523146
2024-08-07 22:07:53,151 INFO     ftriage:     main:972  Found peer-node MXS2-LF101 and IF: Eth1/50 in candidate list
2024-08-07 22:08:57,872 INFO     ftriage:     fcls:2510 MXS2-LF101: Valid ELAM for asic:0 slice:1 srcid:0 pktid:203
2024-08-07 22:09:19,755 INFO     ftriage:     main:1314 L3 packet Seen on  MXS2-LF101 Ingress: Eth1/50 Egress: Eth1/20 (Po2)  Vnid: 2000 
2024-08-07 22:09:19,755 INFO     ftriage:     main:1363 MXS2-LF101: Incoming Packet captured with Outer [SIP:10.2.48.66, DIP:10.2.224.64] .... Inner [SIP:10.0.1.2, DIP:10.0.0.1]
2024-08-07 22:09:43,451 INFO     ftriage:     main:1403 MXS2-LF101: Outgoing packet's Vnid: 2000
2024-08-07 22:15:20,464 INFO     ftriage:     main:797  Computed egress encap string vlan-2000
2024-08-07 22:15:26,459 INFO     ftriage:     main:535  Egress Ctx vmenchac_T01:vmenchac_vrf_01
2024-08-07 22:15:26,459 INFO     ftriage:     main:536  Egress BD(s): vmenchac_T01:vmenchac_bd_01
2024-08-07 22:15:27,642 WARNING  ftriage:     misc:736  MXS2-LF101: Trouble getting the cores from the node
2024-08-07 22:15:27,642 WARNING  ftriage:     misc:736  MXS2-LF101: Trouble getting the cores from the node
2024-08-07 22:15:38,883 INFO     ftriage:  unicast:2019 MXS2-LF101: Enter dbg_sub_nexthop with cn SUG and inst: eg
2024-08-07 22:15:38,883 INFO     ftriage:  unicast:2033 MXS2-LF101: Enter dbg_sub_nexthop with Local inst: eg infra: False glbs.dipo: 10.2.224.64
2024-08-07 22:15:38,884 INFO     ftriage:  unicast:2046 MXS2-LF101: dbg_sub_nexthop invokes dbg_sub_eg for vip
2024-08-07 22:15:45,859 INFO     ftriage:  unicast:2759 MXS2-LF101: Enter dbg_sub_eg with cn SUG and inst: eg
2024-08-07 22:15:45,860 INFO     ftriage:  unicast:2816 MXS2-LF101: Dst EP is local
2024-08-07 22:15:45,860 INFO     ftriage:  unicast:372  MXS2-LF101: Enter dbg_leaf_local with cn SUG and inst: eg
2024-08-07 22:15:45,861 INFO     ftriage:     misc:907  MXS2-LF101: caller  unicast:581  EP if(Po2) same as egr if(Po2)
2024-08-07 22:16:00,129 INFO     ftriage:     misc:907  MXS2-LF101: caller  unicast:647  Dst IP is present in SUG L3 tbl
2024-08-07 22:16:14,262 INFO     ftriage:     misc:907  MXS2-LF101: caller  unicast:729  RW seg_id:2000 in SUG same as EP segid:2000
2024-08-07 22:16:14,263 INFO     ftriage:     main:1816 dbg_sub_nexthop function returned values on node MXS2-LF101 done True, nxt_nifs None, nxt_dbg_f_n , nxt_inst , eg_ifs Eth1/20, Vnid: 2000
2024-08-07 22:16:24,389 INFO     ftriage:     main:1848 Packet is Exiting fabric with peer-device: ACI-N3K-4 and peer-port: Ethernet1/44
MXS2-AP001# 
```
