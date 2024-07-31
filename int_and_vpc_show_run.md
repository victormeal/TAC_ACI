# Interface and VPC interface running config from APIC


## Access port vlan 2000
```
MXS2-AP001# show running-config leaf 104 interface ethernet 1/45
# Command: show running-config leaf 104 interface ethernet 1/45
# Time: Tue Jul 30 17:14:47 2024
  leaf 104 
    interface ethernet 1/45
      # policy-group vmenchac_accessport_01
      switchport access vlan 2000 tenant vmenchac_T01 application vmenchac_appprofile_01 epg vmenchac_epg_01 
      exit
    exit
MXS2-AP001#  
```

## VPC inteface

```
MXS2-AP001# show run leaf 101 interface eth 1/20
# Command: show running-config leaf 101 interface eth 1/20
# Time: Tue Jul 30 17:20:09 2024
  leaf 101 
    interface ethernet 1/20
      # channel-group vmenchc_vpc_intpolgroup_01 vpc
      exit
    exit
MXS2-AP001# 
```
```
MXS2-AP001# show run vpc context leaf 101 102 interface vpc vmenchc_vpc_intpolgroup_01
# Command: show running-config vpc context leaf 101 102 interface vpc vmenchc_vpc_intpolgroup_01
# Time: Tue Jul 30 17:21:09 2024
  vpc context leaf 101 102
    interface vpc vmenchc_vpc_intpolgroup_01
      switchport trunk allowed vlan 2000 tenant vmenchac_T01 application vmenchac_appprofile_01 epg vmenchac_epg_01 
      exit
    exit
MXS2-AP001#
```
