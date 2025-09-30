# Syslog

The same syslog messages are also saved in a local file /var/log/external/messages.

```
MXS2-AP001# cat /var/log/external/messages | head
Sep 30 17:33:45 MXS2-AP001 %LOG_LOCAL0-6-SYSTEM_MSG [E4204953][assigned-ip-address][info][client-[FDO204520TY]] Fabric node MXS2-L101 (Node ID: 101) was successfully assigned IP address 10.2.160.66/32 by DHCP.
Sep 30 17:34:06 MXS2-AP001 %LOG_LOCAL0-6-SYSTEM_MSG [E4204953][assigned-ip-address][info][client-[FDO241114GS]] Fabric node MXS2-S1001 (Node ID: 1001) was successfully assigned IP address 10.2.160.65/32 by DHCP.
Sep 30 17:34:06 MXS2-AP001 %LOG_LOCAL0-6-SYSTEM_MSG [E4204953][assigned-ip-address][info][client-[FDO241114GS]] Fabric node MXS2-S1001 (Node ID: 1001) was successfully assigned IP address 10.2.160.65/32 by DHCP.
Sep 30 17:34:06 MXS2-AP001 %LOG_LOCAL0-6-SYSTEM_MSG [E4204953][assigned-ip-address][info][client-[FDO241114GS]] Fabric node MXS2-S1001 (Node ID: 1001) was successfully assigned IP address 10.2.160.65/32 by DHCP.
Sep 30 17:34:19 MXS2-AP001 %LOG_LOCAL0-6-SYSTEM_MSG [refresh,session][info][subj-[uni/userext/user-admin]/sess-4295783931] [user admin] From-10.188.15.195-client-type-REST-Success
Sep 30 17:34:19 MXS2-AP001 %LOG_LOCAL0-6-SYSTEM_MSG [refresh,session][info][subj-[uni/userext/user-admin]/sess-4295783931] [user admin] From-10.188.15.195-client-type-REST-Success
Sep 30 17:34:40 MXS2-AP001 %LOG_LOCAL7-6-SYSTEM_MSG [refresh,session][info][subj-[uni/userext/user-admin]/sess-4295783932] [user admin] From-10.26.167.79-client-type-REST-Success
Sep 30 17:34:40 MXS2-AP001 %LOG_LOCAL7-6-SYSTEM_MSG [refresh,session][info][subj-[uni/userext/user-admin]/sess-4295783932] [user admin] From-10.26.167.79-client-type-REST-Success
Sep 30 17:34:43 MXS2-AP001 %LOG_LOCAL0-3-SYSTEM_MSG [F2831][raised][resolution-failed][minor][uni/tn-av/svcCont/svcRedirectPol-15.15.15.2/rsIPSLAMonitoringPol/fault-F2831] Failed to form relation to MO uni/tn-av/ipslaMonitoringPol-avIpsla of class fvIPSLAMonitoringPol
Sep 30 17:34:43 MXS2-AP001 %LOG_LOCAL7-4-SYSTEM_MSG [F1617][raised][resolution-failed][warning][uni/tn-av/ldevCtx-c-FvCtrav-g-av-l4l7-sgt-n-N1/lIfCtx-c-provider/rsLIfCtxToInstP/fault-F1617] Failed to form relation to MO uni/tn-av/out-av_static/instP-exEpg of class l3extInstP
MXS2-AP001#                                      
MXS2-AP001# 
MXS2-AP001# 
MXS2-AP001# 
MXS2-AP001# cat /var/log/external/messages | tail
Sep 30 19:02:52 MXS2-AP001 %LOG_LOCAL0-6-SYSTEM_MSG [refresh,session][info][subj-[uni/userext/user-Cisco_MSO_qrujwiDy]/sess-4295784171] [user Cisco_MSO_qrujwiDy] From-10.31.125.221-client-type-REST-Success
Sep 30 19:03:52 MXS2-AP001 %LOG_LOCAL0-6-SYSTEM_MSG [refresh,session][info][subj-[uni/userext/user-Cisco_MSO_qrujwiDy]/sess-4295784172] [user Cisco_MSO_qrujwiDy] From-10.31.125.221-client-type-REST-Success
Sep 30 19:03:52 MXS2-AP001 %LOG_LOCAL0-6-SYSTEM_MSG [refresh,session][info][subj-[uni/userext/user-Cisco_MSO_qrujwiDy]/sess-4295784172] [user Cisco_MSO_qrujwiDy] From-10.31.125.221-client-type-REST-Success
Sep 30 19:04:04 MXS2-AP001 %LOG_LOCAL0-6-SYSTEM_MSG [refresh,session][info][subj-[uni/userext/user-admin]/sess-4295784173] [user admin] From-10.152.203.117-client-type-REST-Success
Sep 30 19:04:04 MXS2-AP001 %LOG_LOCAL0-6-SYSTEM_MSG [refresh,session][info][subj-[uni/userext/user-admin]/sess-4295784173] [user admin] From-10.152.203.117-client-type-REST-Success
Sep 30 19:04:38 MXS2-AP001 %LOG_LOCAL7-6-SYSTEM_MSG [E4209236][transition][info][uni/tn-CiscoLive2025/ctx-CLUS_Server/cep-00:00:00:00:00:00/ip-[192.168.200.2]] IP detached. EPG: uni/tn-CiscoLive2025/ctx-CLUS_Server. IP: 192.168.200.2
Sep 30 19:04:52 MXS2-AP001 %LOG_LOCAL0-6-SYSTEM_MSG [refresh,session][info][subj-[uni/userext/user-Cisco_MSO_qrujwiDy]/sess-4295784174] [user Cisco_MSO_qrujwiDy] From-10.31.125.221-client-type-REST-Success
Sep 30 19:04:52 MXS2-AP001 %LOG_LOCAL0-6-SYSTEM_MSG [refresh,session][info][subj-[uni/userext/user-Cisco_MSO_qrujwiDy]/sess-4295784174] [user Cisco_MSO_qrujwiDy] From-10.31.125.221-client-type-REST-Success
Sep 30 19:05:12 MXS2-AP001 %LOG_LOCAL0-6-SYSTEM_MSG [refresh,session][info][subj-[uni/userext/user-admin]/sess-4295784175] [user admin] From-10.25.129.227-client-type-REST-Success
Sep 30 19:05:12 MXS2-AP001 %LOG_LOCAL0-6-SYSTEM_MSG [refresh,session][info][subj-[uni/userext/user-admin]/sess-4295784175] [user admin] From-10.25.129.227-client-type-REST-Success
MXS2-AP001#
```
