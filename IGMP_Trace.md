# IGMP Traces

```
MXS2-L101# tcpdump -i kpm_inb host 10.12.62.4
tcpdump: verbose output suppressed, use -v or -vv for full protocol decode
listening on kpm_inb, link-type EN10MB (Ethernet), capture size 262144 bytes
17:42:57.562949 IP 10.12.62.4 > 239.1.1.2: igmp v2 report 239.1.1.2
17:42:57.563162 IP 10.12.62.4 > 239.1.1.1: igmp v2 report 239.1.1.1
17:42:57.563371 IP 10.12.62.4 > 239.1.2.2: igmp v2 report 239.1.2.2
^C
3 packets captured
3 packets received by filter
0 packets dropped by kernel
MXS2-L101#
```
``` 
MXS2-L101# show ip igmp groups vrf vmenchac_PROD:VRF1 
Type: S - Static, D - Dynamic, L - Local, T - SSM Translated
IGMP Connected Group Membership for VRF "vmenchac_PROD:VRF1"
Group Address        Type   Interface    Uptime               Expires              Last Reporter       
239.1.1.1            D      vlan53       2d16h                00:03:48             10.12.62.4          
239.1.1.2            D      vlan53       2d16h                00:03:48             10.12.62.4          
```
```
MXS2-L101# show ip igmp internal event-history events | egrep 239.     
2025-07-20T00:46:30.487432000+00:00 igmp [21468]: TID 23224:igmp_entry_process_mrib_update:619:(vmenchac_PROD:VRF1-base) igmp_entry_process_mrib_update: Update received for (*, 239.1.1.2) on Vlan53
2025-07-20T00:46:30.487367000+00:00 igmp [21468]: TID 23224:igmp_entry_process_mrib_update:619:(vmenchac_PROD:VRF1-base) igmp_entry_process_mrib_update: Update received for (*, 239.1.1.1) on Vlan53
2025-07-20T00:46:30.025334000+00:00 igmp [21468]: TID 22688:igmp_entry_process_mrib_update:619:(vmenchac_PROD:VRF1-base) igmp_entry_process_mrib_update: Update received for (*, 239.1.1.2) on Vlan53
2025-07-20T00:46:30.025248000+00:00 igmp [21468]: TID 22688:igmp_entry_process_mrib_update:619:(vmenchac_PROD:VRF1-base) igmp_entry_process_mrib_update: Update received for (*, 239.1.1.1) on Vlan53
2025-07-20T00:45:16.339869000+00:00 igmp [21468]: TID 23225:igmp_receive_report:2754:(vmenchac_PROD:VRF1-base) igmp receive report: Entry created: Triggering MRIB schedule update for (*, 239.1.1.2) oif: Vlan53
2025-07-20T00:45:16.339452000+00:00 igmp [21468]: TID 23225:igmp_receive_report:2754:(vmenchac_PROD:VRF1-base) igmp receive report: Entry created: Triggering MRIB schedule update for (*, 239.1.1.1) oif: Vlan53
MXS2-L101#
```
```
MXS2-L101# pwd
/var/sysmgr/tmp_logs
MXS2-L101# log_trace_bl_print_tool igmp_trace.bl | egrep 239.1.2.2  
[2025-07-22T17:46:59.262689000+00:00:T:igmp_receive_v1v2_report:4180] (vmenchac_PROD:VRF1) Received v2 Report for 239.1.2.2 from 10.12.62.4 (Vlan53)
[2025-07-22T17:46:59.263169000+00:00:T:igmp_allow_group_source:2586] (vmenchac_PROD:VRF1) Filtered group 239.1.2.2
[2025-07-22T17:48:56.207213000+00:00:T:igmp_receive_v1v2_report:4180] (vmenchac_PROD:VRF1) Received v2 Report for 239.1.2.2 from 10.12.62.4 (Vlan53)
[2025-07-22T17:48:56.207947000+00:00:T:igmp_allow_group_source:2586] (vmenchac_PROD:VRF1) Filtered group 239.1.2.2
[2025-07-22T17:50:50.763671000+00:00:T:igmp_receive_v1v2_report:4180] (vmenchac_PROD:VRF1) Received v2 Report for 239.1.2.2 from 10.12.62.4 (Vlan53)
[2025-07-22T17:50:50.764130000+00:00:T:igmp_allow_group_source:2586] (vmenchac_PROD:VRF1) Filtered group 239.1.2.2
[2025-07-22T17:52:45.543683000+00:00:T:igmp_receive_v1v2_report:4180] (vmenchac_PROD:VRF1) Received v2 Report for 239.1.2.2 from 10.12.62.4 (Vlan53)
[2025-07-22T17:52:45.544186000+00:00:T:igmp_allow_group_source:2586] (vmenchac_PROD:VRF1) Filtered group 239.1.2.2
[2025-07-22T17:54:47.843518000+00:00:T:igmp_receive_v1v2_report:4180] (vmenchac_PROD:VRF1) Received v2 Report for 239.1.2.2 from 10.12.62.4 (Vlan53)
[2025-07-22T17:54:47.844007000+00:00:T:igmp_allow_group_source:2586] (vmenchac_PROD:VRF1) Filtered group 239.1.2.2
[2025-07-22T17:56:49.580567000+00:00:T:igmp_receive_v1v2_report:4180] (vmenchac_PROD:VRF1) Received v2 Report for 239.1.2.2 from 10.12.62.4 (Vlan53)
[2025-07-22T17:56:49.581060000+00:00:T:igmp_allow_group_source:2586] (vmenchac_PROD:VRF1) Filtered group 239.1.2.2
[2025-07-22T17:58:50.722618000+00:00:T:igmp_receive_v1v2_report:4180] (vmenchac_PROD:VRF1) Received v2 Report for 239.1.2.2 from 10.12.62.4 (Vlan53)
[2025-07-22T17:58:50.723253000+00:00:T:igmp_allow_group_source:2586] (vmenchac_PROD:VRF1) Filtered group 239.1.2.2

```
On logviewer:
```
path:
...3of3/var/sysmgr/tmp_logs

logviewer# nxos-bl-decode -f igmp_trace.bl 
```
