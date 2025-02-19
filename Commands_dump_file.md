# Commands

### Miscellaneous
```
SWITCH# show ip route
SWITCH# show lldp neighbors
SWITCH# show isis internal mcast routes gipo | egrep 239.255.255.240 -A 4
SWITCH# show isis internal mcast routes ftag | egrep -A 9 "FTAG ID:  1"
SWITCH# iping -V <tenant/vrf> 10.0.1.2 -S 10.0.1.254
SWITCH# setup-clean-config.sh
```
```
LEAF# show enpoint
LEAF# show endpoint ip 10.0.0.1
LEAF# show system internal epm endpoint ip 10.0.0.1
LEAF# cat /mit/sys/phys-[eth1--51]/summary
LEAF# show isis dteps vrf overlay-1
```
```
SPINE# show coop internal info repo ep | egrep -A 8 -B 42 10.0.0.1
SPINE# show coop internal info repo ep key <BD VNID> <MAC> | egrep 'vnid|mac|id|Real'
```
```
APIC# ifconfig
APIC# show firmware upgrade status
APIC# acidiag avread
APIC# avread
APIC# acidiag fnvread
APIC# acidiag run lldp tool in eth2-1
APIC# ifconfig
APIC# show switch
APIC# moquery -d uni/infra/accportprof-Leaf_101_102/hports-e1-20-typ-range
APIC# moquery -c fvAEPg -f 'fv.AEPg.name=="App_EPG"'
APIC# fabric 101 show hostname
APIC# moquery -c ipv4.Addr -f 'ipv4.Addr.addr == "10.2.184.66"'
APIC# show stats granularity 15min history leaf 316 interface eth 1/20
```
### Basic Commands
```
APIC# show version
APIC# show controller
APIC# show switch
APIC# acidiag fnvread
APIC# moquery -c faultInst -f 'fault.Inst.code=="Fxxxx"'
APIC# show fault code Fxxxx detail
```
### Endpoint learning
```
APIC# show epg <>
APIC# show epg <> detail
APIC# show endpoints ip 10.0.0.1
```
### Contracts / Zoning-rules
```
APIC# moquery -c fvCtx -f 'fv.Ctx.name=="Presales_VRF"'
APIC# moquery -c fvAEPg -f 'fv.AEPg.name=="App_EPG"'
```
```
LEAF# show zoning-rule
LEAF# show zoning-rule scope <vrf segment>
LEAF# show zoning-rule | egrep <EPG pcTAG>
LEAF# show zoning-filter
LEAF# show zoning-filter filter 8
```
### Interfaces
```
APIC# show run leaf 101 interface eth 1/20
APIC# show run vpc context leaf 101 102 interface vpc vmenchc_vpc_intpolgroup_01
```
### Port Counters
```
APIC# moquery -c rmonDot3Stats -f 'rmon.Dot3Stats.fCSErrors>="1"' | egrep "dn|fCSErrors"
APIC# moquery -c rmonEtherStats -f 'rmon.EtherStats.cRCAlignErrors>="1"' | egrep "dn|cRCAlignErrors"
APIC# moquery -c rmonEgrCounters -f 'rmon.EgrCounters.bufferdroppkts>="1"' | egrep "dn|bufferdroppkts"
APIC# moquery -c rmonIfOut -f 'rmon.IfOut.errors>="1"' | egrep "dn|errors"
```
```
SWITCH# show int e1/2
SWITCH# show int e1/2 counter errors
```
### VLANs
```
LEAF# show vlan extended
```
```
APIC# moquery -c fabric.ExplicitGEp
```
### VPC
```
LEAF# show system internal epm vpc
moquery -c vpcDom
```
### Fabric Discovery
```
SWITCH# show discoveryissues
```
```
APIC# acidiag cluster
```
### Faults, Logging
```
APIC# moquery -c faultInst -f 'fault.Inst.code=="Fxxxx"'
APIC# show faults last-days 5 history
APIC# show faults leaf 101
APIC# show faults history leaf 101
```
### APIC Cluster
```
APIC# show controller
APIC# acidiag avread
APIC# avread
```
### CPU and Porcesses
```
APIC# top
```
### NTP
```
SWITCH# show ntp peer-status
APIC# htpstat
```
### BGP (overlay)
```
SWITCH# show bgp sessions vrf overlay-1
```
### OSPF L3Out
```
BLF# show ip ospf interface vrf vmenchac_T01:vmenchac_vrf_01
BLF# show ip ospf neighbors vrf vmenchac_T01:vmenchac_vrf_01
BLF# show ip route ospf vrf vmenchac_T01:vmenchac_vrf_01
BLF# show bgp ipv4 unicast vrf vmenchac_T01:vmenchac_vrf_01
```
### BGP L3Out
```
SWITCH# tcpdump -i kpm_inb port 179
```
```
BLF# show ip bgp summary vrf vmenchac_T01:vmenchac_vrf_01
BLF# show bgp ipv4 unicast neighbors 3.3.3.3 advertised-routes vrf vmenchac_T01:vmenchac_vrf_01
BLF# show bgp ipv4 unicast neighbors 3.3.3.3 routes vrf vmenchac_T01:vmenchac_vrf_01
BLF# show bgp ipv4 unicast neighbors 3.3.3.3 received-routes vrf vmenchac_T01:vmenchac_vrf_01
```
### Multicast L3
```
SPINE# show isis internal mcast routes gipo | egrep 255.1.192.9 -A10
SPINE# show isis internal mcast routes ftag
LEAF# show ip mroute <mgroup> vrf <vrf_name>
```
### DHCP Relay
```
LEAF# show ip dhcp relay
LEAF# show vlan id 32 extended
LEAF# show dhcp internal info relay address interface vlan 32
LEAF# show dhcp internal info relay discover
LEAF# show dhcp internal event-history traces | egrep -i "udp|DHCP|smac|Dmac|ctx|pkt|interface|svi|drop|type"
```

### QOS
```
LEAF# show system internal qos vlan encap 2000
```
