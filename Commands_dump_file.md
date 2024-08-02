# Commands

### Miscellaneous
```
SWITCH# show ip route
SWITCH# show lldp neighbors
SWITCH# show isis internal mcast routes gipo | egrep 239.255.255.240 -A 4
SWITCH# show isis internal mcast routes ftag | egrep -A 9 "FTAG ID:  1"
SWITHC# iping -V <tenant/vrf> 10.0.1.2
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
```
```
APIC# ifconfig
APIC# show firmware upgrade status
APIC# acidiag avread
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
```
APIC# moquery -c fabric.ExplicitGEp
```
### Fabric Discovery
```
SWITCH# show discoveryissues
```
### Faults, Logging
```
APIC# show faults last-days 5 history
APIC# show faults leaf 101
APIC# show faults history leaf 101
```
### NTP
```
SWITCH# show ntp peer-status
APIC# htpstat
```
