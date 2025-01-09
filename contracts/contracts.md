# Contracts

+ PBR L3out LAB

```
MXS2-LF102# show system internal epm endpoint ip 192.168.1.4

MAC : 00a2.ee74.463c ::: Num IPs : 1
IP# 0 : 192.168.1.4 ::: IP# 0 flags :  ::: l3-sw-hit: No
Vlan id : 171 ::: Vlan vnid : 21192 ::: VRF name : vmenchac_Tenant_PBR:VRF01
BD vnid : 16482272 ::: VRF vnid : 2555914
Phy If : 0x1a009000 ::: Tunnel If : 0
Interface : Ethernet1/10
Flags : 0x80005c04 ::: sclass : 16387 ::: Ref count : 5
EP Create Timestamp : 01/07/2025 11:39:26.909418
EP Update Timestamp : 01/09/2025 17:48:51.122142
EP Flags : local|IP|MAC|host-tracked|sclass|timer|

::::


MXS2-LF102# 
```
```
MXS2-LF102# show system internal epm endpoint ip 192.168.2.4

MAC : 00a2.ee74.463c ::: Num IPs : 1
IP# 0 : 192.168.2.4 ::: IP# 0 flags :  ::: l3-sw-hit: No
Vlan id : 173 ::: Vlan vnid : 21193 ::: VRF name : vmenchac_Tenant_PBR:VRF01
BD vnid : 16482273 ::: VRF vnid : 2555914
Phy If : 0x1a00a000 ::: Tunnel If : 0
Interface : Ethernet1/11
Flags : 0x80005c04 ::: sclass : 49154 ::: Ref count : 5
EP Create Timestamp : 01/01/2025 15:37:57.272198
EP Update Timestamp : 01/09/2025 17:48:51.124242
EP Flags : local|IP|MAC|host-tracked|sclass|timer|

::::


MXS2-LF102#
```


```
MXS2-LF102# show zoning-rule scope 2555914
+---------+--------+--------+----------+----------------+---------+---------+------------------------------------+------------------+----------------------+
| Rule ID | SrcEPG | DstEPG | FilterID |      Dir       |  operSt |  Scope  |                Name                |      Action      |       Priority       |
+---------+--------+--------+----------+----------------+---------+---------+------------------------------------+------------------+----------------------+
|   4127  |   0    |   0    | implicit |    uni-dir     | enabled | 2555914 |                                    |     deny,log     |   any_any_any(21)    |
|   4279  |   0    |   15   | implicit |    uni-dir     | enabled | 2555914 |                                    |     deny,log     | any_vrf_any_deny(22) |
|   4228  |   0    | 16386  | implicit |    uni-dir     | enabled | 2555914 |                                    |      permit      |    src_dst_any(9)    |
|   4125  |   0    | 49153  | implicit |    uni-dir     | enabled | 2555914 |                                    |      permit      |    src_dst_any(9)    |
|   4126  |   0    |   0    | implarp  |    uni-dir     | enabled | 2555914 |                                    |      permit      |  any_any_filter(17)  |
|   4268  | 16388  | 49154  | default  | uni-dir-ignore | enabled | 2555914 | vmenchac_Tenant_PBR:Contract_L3OUT |      permit      |    src_dst_any(9)    |
|   4267  | 49154  | 16388  | default  |     bi-dir     | enabled | 2555914 | vmenchac_Tenant_PBR:Contract_L3OUT |      permit      |    src_dst_any(9)    |
|   4246  | 16387  | 16388  | default  |     bi-dir     | enabled | 2555914 | vmenchac_Tenant_PBR:Contract_L3OUT |      permit      |    src_dst_any(9)    |
|   4143  | 16388  | 16387  | default  | uni-dir-ignore | enabled | 2555914 | vmenchac_Tenant_PBR:Contract_L3OUT |      permit      |    src_dst_any(9)    |
|   4304  | 16387  | 49154  | default  |     bi-dir     | enabled | 2555914 |                                    | redir(destgrp-2) |    src_dst_any(9)    |
|   4229  |  5556  | 49154  | default  |    uni-dir     | enabled | 2555914 |                                    |      permit      |    src_dst_any(9)    |
|   4118  |  5556  | 16387  | default  |    uni-dir     | enabled | 2555914 |                                    |      permit      |    src_dst_any(9)    |
|   4227  | 49154  | 16387  | default  | uni-dir-ignore | enabled | 2555914 |                                    | redir(destgrp-2) |    src_dst_any(9)    |
+---------+--------+--------+----------+----------------+---------+---------+------------------------------------+------------------+----------------------+
MXS2-LF102# 
```
```
MXS2-LF102# contract_parser.py --vrf vmenchac_Tenant_PBR:VRF01              
Key:
[prio:RuleId] [vrf:{str}] action protocol src-epg [src-l4] dst-epg [dst-l4] [flags][contract:{str}] [hit=count]

[9:4246] [vrf:vmenchac_Tenant_PBR:VRF01] permit any tn-vmenchac_Tenant_PBR/ap-AP01/epg-EPG01(16387) tn-vmenchac_Tenant_PBR/l3out-L3OUT01/instP-External_EPG01(16388) [contract:uni/tn-vmenchac_Tenant_PBR/brc-Contract_L3OUT] [hit=0]
[9:4304] [vrf:vmenchac_Tenant_PBR:VRF01] redir any tn-vmenchac_Tenant_PBR/ap-AP01/epg-EPG01(16387) tn-vmenchac_Tenant_PBR/ap-AP01/epg-EPG02(49154) [contract:uni/tn-vmenchac_Tenant_PBR/brc-PBR_L3OUT_contract] [hit=74]
                                               destgrp-2 (disabled no-oper-dest) vrf:vmenchac_Tenant_PBR:VRF01 ip:192.168.100.4 mac:00:00:00:00:00:00 bd:unknown
[9:4143] [vrf:vmenchac_Tenant_PBR:VRF01] permit any tn-vmenchac_Tenant_PBR/l3out-L3OUT01/instP-External_EPG01(16388) tn-vmenchac_Tenant_PBR/ap-AP01/epg-EPG01(16387) [contract:uni/tn-vmenchac_Tenant_PBR/brc-Contract_L3OUT] [hit=12]
[9:4268] [vrf:vmenchac_Tenant_PBR:VRF01] permit any tn-vmenchac_Tenant_PBR/l3out-L3OUT01/instP-External_EPG01(16388) tn-vmenchac_Tenant_PBR/ap-AP01/epg-EPG02(49154) [contract:uni/tn-vmenchac_Tenant_PBR/brc-Contract_L3OUT] [hit=0]
[9:4227] [vrf:vmenchac_Tenant_PBR:VRF01] redir any tn-vmenchac_Tenant_PBR/ap-AP01/epg-EPG02(49154) tn-vmenchac_Tenant_PBR/ap-AP01/epg-EPG01(16387) [contract:uni/tn-vmenchac_Tenant_PBR/brc-PBR_L3OUT_contract] [hit=290]
                                               destgrp-2 (disabled no-oper-dest) vrf:vmenchac_Tenant_PBR:VRF01 ip:192.168.100.4 mac:00:00:00:00:00:00 bd:unknown
[9:4267] [vrf:vmenchac_Tenant_PBR:VRF01] permit any tn-vmenchac_Tenant_PBR/ap-AP01/epg-EPG02(49154) tn-vmenchac_Tenant_PBR/l3out-L3OUT01/instP-External_EPG01(16388) [contract:uni/tn-vmenchac_Tenant_PBR/brc-Contract_L3OUT] [hit=0]
[9:4118] [vrf:vmenchac_Tenant_PBR:VRF01] permit any tn-vmenchac_Tenant_PBR/l3out-L3OUT01/instP-External_EPG01(5556) tn-vmenchac_Tenant_PBR/ap-AP01/epg-EPG01(16387) [contract:uni/tn-vmenchac_Tenant_PBR/brc-PBR_L3OUT_contract] [hit=28]
[9:4229] [vrf:vmenchac_Tenant_PBR:VRF01] permit any tn-vmenchac_Tenant_PBR/l3out-L3OUT01/instP-External_EPG01(5556) tn-vmenchac_Tenant_PBR/ap-AP01/epg-EPG02(49154) [contract:uni/tn-vmenchac_Tenant_PBR/brc-PBR_L3OUT_contract] [hit=37]
[9:4228] [vrf:vmenchac_Tenant_PBR:VRF01] permit any epg:any tn-vmenchac_Tenant_PBR/bd-BD02(16386) [contract:implicit] [hit=34869]
[9:4125] [vrf:vmenchac_Tenant_PBR:VRF01] permit any epg:any tn-vmenchac_Tenant_PBR/bd-BD01(49153) [contract:implicit] [hit=34878,+1]
[16:4126] [vrf:vmenchac_Tenant_PBR:VRF01] permit arp epg:any epg:any [contract:implicit] [hit=0]
[21:4127] [vrf:vmenchac_Tenant_PBR:VRF01] deny,log any epg:any epg:any [contract:implicit] [hit=0]
[22:4279] [vrf:vmenchac_Tenant_PBR:VRF01] deny,log any epg:any pfx-0.0.0.0/0(15) [contract:implicit] [hit=0]
MXS2-LF102# 
```
```
MXS2-LF102# show system internal policy-mgr stats | egrep 2555914
Rule (4118) DN (sys/actrl/scope-2555914/rule-2555914-s-5556-d-16387-f-default) Ingress: 0, Egress: 0, Pkts: 28  RevPkts: 0
Rule (4125) DN (sys/actrl/scope-2555914/rule-2555914-s-any-d-49153-f-implicit) Ingress: 0, Egress: 0, Pkts: 34867  RevPkts: 0
Rule (4126) DN (sys/actrl/scope-2555914/rule-2555914-s-any-d-any-f-implarp) Ingress: 0, Egress: 0, Pkts: 0  RevPkts: 0
Rule (4127) DN (sys/actrl/scope-2555914/rule-2555914-s-any-d-any-f-implicit) Ingress: 0, Egress: 0, Pkts: 0  RevPkts: 0
Rule (4143) DN (sys/actrl/scope-2555914/rule-2555914-s-16388-d-16387-f-default) Ingress: 0, Egress: 0, Pkts: 12  RevPkts: 0
Rule (4227) DN (sys/actrl/scope-2555914/rule-2555914-s-49154-d-16387-f-default) Ingress: 0, Egress: 0, Pkts: 290  RevPkts: 0
Rule (4228) DN (sys/actrl/scope-2555914/rule-2555914-s-any-d-16386-f-implicit) Ingress: 0, Egress: 0, Pkts: 34858  RevPkts: 0
Rule (4229) DN (sys/actrl/scope-2555914/rule-2555914-s-5556-d-49154-f-default) Ingress: 0, Egress: 0, Pkts: 37  RevPkts: 0
Rule (4246) DN (sys/actrl/scope-2555914/rule-2555914-s-16387-d-16388-f-default) Ingress: 0, Egress: 0, Pkts: 0  RevPkts: 0
Rule (4267) DN (sys/actrl/scope-2555914/rule-2555914-s-49154-d-16388-f-default) Ingress: 0, Egress: 0, Pkts: 0  RevPkts: 0
Rule (4268) DN (sys/actrl/scope-2555914/rule-2555914-s-16388-d-49154-f-default) Ingress: 0, Egress: 0, Pkts: 0  RevPkts: 0
Rule (4279) DN (sys/actrl/scope-2555914/rule-2555914-s-any-d-15-f-implicit) Ingress: 0, Egress: 0, Pkts: 0  RevPkts: 0
Rule (4304) DN (sys/actrl/scope-2555914/rule-2555914-s-16387-d-49154-f-default) Ingress: 0, Egress: 0, Pkts: 74  RevPkts: 0
MXS2-LF102# 
```
