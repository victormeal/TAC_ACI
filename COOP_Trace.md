SPINE COOP TRACE

```
MXS2-L101# show system internal epm endpoint ip 192.168.1.2

MAC : 00a2.ee74.463c ::: Num IPs : 1
IP# 0 : 192.168.1.2 ::: IP# 0 flags : host-tracked| ::: l3-sw-hit: Yes ::: flags2 : 
Vlan id : 14 ::: Vlan vnid : 8392 ::: VRF name : lb-1:vrf-1
BD vnid : 16449444 ::: VRF vnid : 3080192
Phy If : 0x1a000000 ::: Tunnel If : 0
Interface : Ethernet1/1
Flags : 0x80005c04 ::: sclass : 32770 ::: Ref count : 5
EP Create Timestamp : 05/15/2025 20:20:05.411819
EP Update Timestamp : 05/19/2025 21:46:46.420163
EP Flags : local|IP|MAC|host-tracked|sclass|timer|

::::


MXS2-L101#
```
```
MXS2-S1001# show coop internal info ip-db key 3080192 192.168.1.2


IP address : 192.168.1.2
Vrf : 3080192
Flags : 0
EP bd vnid : 16449444 
EP mac :  00:A2:EE:74:46:3C
Publisher Id : 10.2.160.66
Record timestamp : 05 19 2025 21:18:39 122922008
Publish timestamp : 05 19 2025 21:18:39 125546501
Seq No: 0
Remote publish timestamp: 01 01 1970 00:00:00 0
URIB Tunnel Info
Num tunnels : 1
 Tunnel address : 10.2.160.66
 Tunnel ref count : 1



MXS2-S1001# 
```
```
MXS2-S1001# pwd
/var/sysmgr/tmp_logs
MXS2-S1001# 
```
```
MXS2-S1001# log_trace_bl_print_tool coop_trace.bl | grep 192.168.1.2   
[2025-05-19T02:19:51.853809000+00:00:U:coop_oracle_publish_ep_rmt_preprocess:1365] TID 26:[DBG_COOP_TRACE_DETAIL_UC]:EP record Op:Add received: return offset:0 ACTION:Local Process<vrf_vnid=2949121;ip=192.168.1.254>;
[2025-05-19T02:19:51.853810000+00:00:U:coop_oracle_process_publish_ep_add_v2:10764] TID 26:[DBG_COOP_TRACE_DETAIL_UC]:Process EPM ADD request bd_vnid 4261521600   (5772 bytes) flags 0x0 ep-add flags 0x6<vrf_vnid=2949121;ip=192.168.1.254>;
[2025-05-19T02:19:51.853814000+00:00:U:coop_ipv4_update_add_leaf:4718] TID 26:[DBG_COOP_TRACE_DETAIL_UC]:Processing add leaf 192.168.1.254 is_anycast 0 pc_tag 0x0
[2025-05-19T02:19:51.853816000+00:00:U:coop_oracle_process_ep_add_record:10205] TID 26:[DBG_COOP_TRACE_DETAIL_UC]:repo_flags 258<vrf_vnid=2949121;ip=192.168.1.254>;
[2025-05-19T02:19:51.853817000+00:00:U:coop_oracle_process_ep_add_record:10300] TID 26:[DBG_COOP_TRACE_DETAIL_UC]:log_collect_coop Re-publish router EP <vrf_vnid=2949121;ip=192.168.1.254>;
[2025-05-19T02:19:51.853817000+00:00:U:coop_oracle_v2l_process_router_ep_publish:524] TID 26:[DBG_COOP_TRACE_DETAIL_UC]:Add router ep to vrf 2949121 ep_va_type:0  ep_flags:0x86 <vrf_vnid=2949121;ip=192.168.1.254>;
[2025-05-19T02:19:51.853819000+00:00:L:coop_l2rib_export_ep_routes:2630] TID 26:[DBG_COOP_TRACE_DETAIL_L2RIB]:L2R export walk EP route type 0 mpod route type 545<vrf_vnid=2949121;ip=192.168.1.254>;
[2025-05-19T02:19:51.853820000+00:00:U:coop_oracle_process_ep_add_record:10350] TID 26:[DBG_COOP_TRACE_DETAIL_UC]:log_collect_coop L2RIB export SUCCESS trans_id 129054<vrf_vnid=2949121;ip=192.168.1.254>;
[2025-05-19T02:19:51.853822000+00:00:U:coop_oracle_process_tunnel_info_for_ep:3278] TID 26:[DBG_COOP_TRACE_DETAIL_UC]:add operation new_tunnel_nh= 10.2.160.66 cur_tunnel_nh= 10.2.160.66 old_l2nh= 10.2.160.66 old_l3v4nh= 10.2.160.66 old_l3v6nh= 10.2.160.66 l2nh= 10.2.160.66 l3v4nh= 10.2.160.66 l3v6nh= 10.2.160.66 l2nh_addr_changed=no  l3v4nh_addr_changed=no  l3v6nh_addr_changed=no  tunnel_nh_state=up <vrf_vnid=2949121;ip=192.168.1.254>;
[2025-05-19T02:19:51.853823000+00:00:U:coop_program_synthip:2806] TID 26:[DBG_COOP_TRACE_DETAIL_UC]:log_collect_coop trans_id 129054 optype=ADD;eptype=ip;                ip=192.168.1.254;                 nh=10.2.160.66;flags=0x5;<vrf_vnid=2949121;ip=192.168.1.254>;
[2025-05-19T02:19:51.853824000+00:00:U:coop_program_synthip:3035] TID 26:[DBG_COOP_TRACE_DETAIL_UC]:log_collect_coop URIB SUCCESS trans_id 129054 optype=ADD eptype=ipip=192.168.1.254 nh=10.2.160.66 flags=0x5 <vrf_vnid=2949121;ip=192.168.1.254>;
[2025-05-19T02:19:51.853833000+00:00:D:coop_objs_upd_iponly_record:8292] TID 26:[DBG_COOP_TRACE_DETAIL]: Modifying iponly: sys/coop/inst/dom-overlay-1/db-ep/vrf-2949121-ip-[192.168.1.254]
[2025-05-19T02:19:51.853841000+00:00:D:coop_objs_upd_ep:8884] TID 26:[DBG_COOP_TRACE_DETAIL]:Successfully update ep record<vrf_vnid=2949121;ip=192.168.1.254>;
[2025-05-19T02:19:51.853842000+00:00:U:coop_oracle_process_ep_add_record:10474] TID 26:[DBG_COOP_TRACE_DETAIL_UC]:notify_host_route_chg FALSE repo_ep tx_status 6 anycast_service 0<vrf_vnid=2949121;ip=192.168.1.254>;
[2025-05-19T02:19:51.853843000+00:00:U:coop_oracle_process_ep_add_record:10482] TID 26:[DBG_COOP_TRACE_DETAIL_UC]:[DAMP] Current EP damp penalty is 2 anycast_service 0<vrf_vnid=2949121;ip=192.168.1.254>;
[2025-05-19T02:19:51.854395000+00:00:U:coop_ipv4_update_add_leaf:4718] TID 26:[DBG_COOP_TRACE_DETAIL_UC]:Processing add leaf 192.168.1.2 is_anycast 0 pc_tag 0x0
[2025-05-19T02:19:51.854406000+00:00:U:coop_program_synthip:2806] TID 26:[DBG_COOP_TRACE_DETAIL_UC]:log_collect_coop trans_id 0 optype=ADD;eptype=ip;                ip=192.168.1.2;                 nh=10.2.160.66;flags=0x25;<bd_vnid=16449444;mac=00:A2:EE:74:46:3C>;
[2025-05-19T02:19:51.854407000+00:00:U:coop_program_synthip:3035] TID 26:[DBG_COOP_TRACE_DETAIL_UC]:log_collect_coop URIB SUCCESS trans_id 0 optype=ADD eptype=ipip=192.168.1.2 nh=10.2.160.66 flags=0x25 <bd_vnid=16449444;mac=00:A2:EE:74:46:3C>;
[2025-05-19T02:19:51.854470000+00:00:U:coop_oracle_publish_ep_rmt_preprocess:1365] TID 26:[DBG_COOP_TRACE_DETAIL_UC]:EP record Op:Add received: return offset:0 ACTION:Local Process<vrf_vnid=2818048;ip=192.168.102.1>;
[2025-05-19T02:19:51.854471000+00:00:U:coop_oracle_process_publish_ep_add_v2:10764] TID 26:[DBG_COOP_TRACE_DETAIL_UC]:Process EPM ADD request bd_vnid 23505088   (3324 bytes) flags 0x0 ep-add flags 0x0<vrf_vnid=2818048;ip=192.168.102.1>;
[2025-05-19T02:19:51.854474000+00:00:U:coop_ipv4_update_add_leaf:4718] TID 26:[DBG_COOP_TRACE_DETAIL_UC]:Processing add leaf 192.168.102.1 is_anycast 0 pc_tag 0x0
[2025-05-19T02:19:51.854477000+00:00:U:coop_oracle_process_ep_add_record:10205] TID 26:[DBG_COOP_TRACE_DETAIL_UC]:repo_flags 258<vrf_vnid=2818048;ip=192.168.102.1>;
[2025-05-19T02:19:51.854478000+00:00:L:coop_l2rib_export_ep_routes:2630] TID 26:[DBG_COOP_TRACE_DETAIL_L2RIB]:L2R export walk EP route type 0 mpod route type 545<vrf_vnid=2818048;ip=192.168.102.1>;
[2025-05-19T02:19:51.854479000+00:00:U:coop_oracle_process_ep_add_record:10350] TID 26:[DBG_COOP_TRACE_DETAIL_UC]:log_collect_coop L2RIB export SUCCESS trans_id 129054<vrf_vnid=2818048;ip=192.168.102.1>;
[2025-05-19T02:19:51.854481000+00:00:U:coop_oracle_process_tunnel_info_for_ep:3278] TID 26:[DBG_COOP_TRACE_DETAIL_UC]:add operation new_tunnel_nh= 10.2.160.66 cur_tunnel_nh= 10.2.160.66 old_l2nh= 10.2.160.66 old_l3v4nh= 10.2.160.66 old_l3v6nh= 10.2.160.66 l2nh= 10.2.160.66 l3v4nh= 10.2.160.66 l3v6nh= 10.2.160.66 l2nh_addr_changed=no  l3v4nh_addr_changed=no  l3v6nh_addr_changed=no  tunnel_nh_state=up <vrf_vnid=2818048;ip=192.168.102.1>;
[2025-05-19T02:19:51.854482000+00:00:U:coop_program_synthip:2806] TID 26:[DBG_COOP_TRACE_DETAIL_UC]:log_collect_coop trans_id 129054 optype=ADD;eptype=ip;                ip=192.168.102.1;                 nh=10.2.160.66;flags=0x5;<vrf_vnid=2818048;ip=192.168.102.1>;
[2025-05-19T02:19:51.854482000+00:00:U:coop_program_synthip:3035] TID 26:[DBG_COOP_TRACE_DETAIL_UC]:log_collect_coop URIB SUCCESS trans_id 129054 optype=ADD eptype=ipip=192.168.102.1 nh=10.2.160.66 flags=0x5 <vrf_vnid=2818048;ip=192.168.102.1>;
[2025-05-19T02:19:51.854492000+00:00:D:coop_objs_upd_iponly_record:8292] TID 26:[DBG_COOP_TRACE_DETAIL]: Modifying iponly: sys/coop/inst/dom-overlay-1/db-ep/vrf-2818048-ip-[192.168.102.1]
[2025-05-19T02:19:51.854499000+00:00:D:coop_objs_upd_ep:8884] TID 26:[DBG_COOP_TRACE_DETAIL]:Successfully update ep record<vrf_vnid=2818048;ip=192.168.102.1>;
[2025-05-19T02:19:51.854500000+00:00:U:coop_oracle_process_ep_add_record:10381] TID 26:[DBG_COOP_TRACE_DETAIL_UC]:Added EP record into HT 0x74019fd8 from hash table<vrf_vnid=32630;ip=2818048.192.168.102>;
[2025-05-19T02:19:51.854501000+00:00:U:coop_oracle_process_ep_add_record:10474] TID 26:[DBG_COOP_TRACE_DETAIL_UC]:notify_host_route_chg FALSE repo_ep tx_status 6 anycast_service 0<vrf_vnid=2818048;ip=192.168.102.1>;
[2025-05-19T02:19:51.854501000+00:00:U:coop_oracle_process_ep_add_record:10482] TID 26:[DBG_COOP_TRACE_DETAIL_UC]:[DAMP] Current EP damp penalty is 2 anycast_service 0<vrf_vnid=2818048;ip=192.168.102.1>;
 [2025-05-19T02:19:51.955953000+00:00:Q:coop_lazy_obj_debug_print:12093] TID 02:[DBG_COOP_TRACE_OBJ]:    modChunk with DN SUCCEEDED: chunkId=d39 priKey {classId=1673, key=1b2} dn=sys/coop/inst/dom-overlay-1/db-ep/vrf-2949121-ip-[192.168.1.254]
 [2025-05-19T02:19:51.956038000+00:00:Q:coop_lazy_obj_debug_print:12093] TID 02:[DBG_COOP_TRACE_OBJ]:    modChunk with DN SUCCEEDED: chunkId=593 priKey {classId=a18, key=16c} dn=sys/coop/inst/dom-overlay-1/db-ep/epr-16449444-epr-00:A2:EE:74:46:3C/epip4-192.168.1.2
 [2025-05-19T02:19:51.956046000+00:00:Q:coop_lazy_obj_debug_print:12093] TID 02:[DBG_COOP_TRACE_OBJ]:    modChunk with DN SUCCEEDED: chunkId=d39 priKey {classId=1673, key=158} dn=sys/coop/inst/dom-overlay-1/db-ep/vrf-2818048-ip-[192.168.102.1]
[2025-05-19T02:47:56.870569000+00:00:U:coop_oracle_publish_ep_rmt_preprocess:1365] TID 15:[DBG_COOP_TRACE_DETAIL_UC]:EP record Op:Add received: return offset:0 ACTION:Local Process<vrf_vnid=2949121;ip=192.168.1.254>;
[2025-05-19T02:47:56.870570000+00:00:U:coop_oracle_process_publish_ep_add_v2:10764] TID 15:[DBG_COOP_TRACE_DETAIL_UC]:Process EPM ADD request bd_vnid 4261521600   (5104 bytes) flags 0x0 ep-add flags 0x6<vrf_vnid=2949121;ip=192.168.1.254>;
[2025-05-19T02:47:56.870573000+00:00:U:coop_oracle_move_ep_in_tun_nh_db:977] TID 15:[DBG_COOP_TRACE_DETAIL_UC]:Psvi Case ,Skip move NH entry from 10.2.160.66 to 10.2.160.64<vrf_vnid=2949121;ip=192.168.1.254>;
[2025-05-19T02:47:56.870573000+00:00:U:coop_oracle_process_ep_add_record:9421] TID 15:[DBG_COOP_TRACE_DETAIL_UC]:log_collect_coop Psvi incr, add Ep info<vrf_vnid=2949121;ip=192.168.1.254>;
[2025-05-19T02:47:56.870574000+00:00:U:coop_oracle_v2l_process_router_ep_publish:524] TID 15:[DBG_COOP_TRACE_DETAIL_UC]:Add router ep to vrf 2949121 ep_va_type:0  ep_flags:0x86 <vrf_vnid=2949121;ip=192.168.1.254>;
[2025-05-19T02:47:56.870575000+00:00:U:coop_oracle_process_ep_add_record:9426] TID 15:[DBG_COOP_TRACE_DETAIL_UC]:Psvi incr , Skip further updates<vrf_vnid=2949121;ip=192.168.1.254>;
[2025-05-19T02:47:56.870575000+00:00:U:coop_oracle_process_ep_add_record:10503] TID 15:[DBG_COOP_TRACE_DETAIL_UC]:[DAMP] Current EP damp penalty is 0<vrf_vnid=2949121;ip=192.168.1.254>;
[2025-05-19T03:19:51.840617000+00:00:U:coop_oracle_publish_ep_rmt_preprocess:1365] TID 23:[DBG_COOP_TRACE_DETAIL_UC]:EP record Op:Add received: return offset:0 ACTION:Local Process<vrf_vnid=2949121;ip=192.168.1.254>;
[2025-05-19T03:19:51.840618000+00:00:U:coop_oracle_process_publish_ep_add_v2:10764] TID 23:[DBG_COOP_TRACE_DETAIL_UC]:Process EPM ADD request bd_vnid 4261521600   (5860 bytes) flags 0x0 ep-add flags 0x6<vrf_vnid=2949121;ip=192.168.1.254>;
```
```
MXS2-S1001# log_trace_bl_print_tool coop_trace.bl | grep eptype.*192.168.1.2
[2025-05-19T02:19:51.853823000+00:00:U:coop_program_synthip:2806] TID 26:[DBG_COOP_TRACE_DETAIL_UC]:log_collect_coop trans_id 129054 optype=ADD;eptype=ip;                ip=192.168.1.254;                 nh=10.2.160.66;flags=0x5;<vrf_vnid=2949121;ip=192.168.1.254>;
[2025-05-19T02:19:51.853824000+00:00:U:coop_program_synthip:3035] TID 26:[DBG_COOP_TRACE_DETAIL_UC]:log_collect_coop URIB SUCCESS trans_id 129054 optype=ADD eptype=ipip=192.168.1.254 nh=10.2.160.66 flags=0x5 <vrf_vnid=2949121;ip=192.168.1.254>;
[2025-05-19T02:19:51.854406000+00:00:U:coop_program_synthip:2806] TID 26:[DBG_COOP_TRACE_DETAIL_UC]:log_collect_coop trans_id 0 optype=ADD;eptype=ip;                ip=192.168.1.2;                 nh=10.2.160.66;flags=0x25;<bd_vnid=16449444;mac=00:A2:EE:74:46:3C>;
[2025-05-19T02:19:51.854407000+00:00:U:coop_program_synthip:3035] TID 26:[DBG_COOP_TRACE_DETAIL_UC]:log_collect_coop URIB SUCCESS trans_id 0 optype=ADD eptype=ipip=192.168.1.2 nh=10.2.160.66 flags=0x25 <bd_vnid=16449444;mac=00:A2:EE:74:46:3C>;
[2025-05-19T02:19:51.854482000+00:00:U:coop_program_synthip:2806] TID 26:[DBG_COOP_TRACE_DETAIL_UC]:log_collect_coop trans_id 129054 optype=ADD;eptype=ip;                ip=192.168.102.1;                 nh=10.2.160.66;flags=0x5;<vrf_vnid=2818048;ip=192.168.102.1>;
[2025-05-19T02:19:51.854482000+00:00:U:coop_program_synthip:3035] TID 26:[DBG_COOP_TRACE_DETAIL_UC]:log_collect_coop URIB SUCCESS trans_id 129054 optype=ADD eptype=ipip=192.168.102.1 nh=10.2.160.66 flags=0x5 <vrf_vnid=2818048;ip=192.168.102.1>;
[2025-05-19T03:19:51.840634000+00:00:U:coop_program_synthip:2806] TID 23:[DBG_COOP_TRACE_DETAIL_UC]:log_collect_coop trans_id 129835 optype=ADD;eptype=ip;                ip=192.168.1.254;                 nh=10.2.160.66;flags=0x5;<vrf_vnid=2949121;ip=192.168.1.254>;
[2025-05-19T03:19:51.840635000+00:00:U:coop_program_synthip:3035] TID 23:[DBG_COOP_TRACE_DETAIL_UC]:log_collect_coop URIB SUCCESS trans_id 129835 optype=ADD eptype=ipip=192.168.1.254 nh=10.2.160.66 flags=0x5 <vrf_vnid=2949121;ip=192.168.1.254>;
```
```
MXS2-S1001# acidiag fnvread | grep 10.2.160.66
     101        1            MXS2-L101      FDO204520TY     10.2.160.66/32    leaf         active   0
MXS2-S1001# 
```
