# Commands

### Miscellaneous
```
SWITCH# show ip route
SWITCH# show lldp neighbors
SWITCH# show isis internal mcast routes gipo | egrep 239.255.255.240 -A 4
SWITCH# show isis internal mcast routes ftag | egrep -A 9 "FTAG ID:  1"
SWITCH# iping -V <tenant/vrf> 10.0.1.2
SWITCH# setup-clean-config.sh
```
```
LEAF# show enpoint
LEAF# show endpoint ip 10.0.0.1
LEAF# show system internal epm endpoint ip 10.0.0.1
LEAF# show zoning-rule scope <vrf segment>
LEAF# show zoning-rule | egrep <EPG pcTAG>
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
```
### VPC
```
LEAF# show system internal epm vpc
```
### VLANs
```
LEAF# show vlan extended
```
```
APIC# moquery -c fabric.ExplicitGEp
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
### Fabric Discovery
```
SWITCH# show discoveryissues
```
```
APIC# acidiag cluster
```
### Faults, Logging
```
APIC# show faults last-days 5 history
APIC# show faults leaf 101
APIC# show faults history leaf 101
```
### APIC Cluster
```
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
### OSPF
```
BLF# show ip ospf interface vrf vmenchac_T01:vmenchac_vrf_01
BLF# show ip ospf neighbors vrf vmenchac_T01:vmenchac_vrf_01
BLF# show ip route ospf vrf vmenchac_T01:vmenchac_vrf_01
BLF# show bgp ipv4 unicast vrf vmenchac_T01:vmenchac_vrf_01
```
### BGP (overlay)
```
SWITCH# show bgp sessions vrf overlay-1
```
