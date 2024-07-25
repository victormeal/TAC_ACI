# Commands

### Miscellaneous
```
SWITCH# show ip route
SWITCH# show lldp neighbors
```
```
LEAF# show enpoint
LEAF# show endpoint ip 10.0.0.1
LEAF# show system internal epm endpoint ip 10.0.0.1
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
