# Encap VLAN and PI VLAN
+ Here we have to SVI for anycast-gateway (pervasive). One is for encap vlan 2000 (10.0.0.254) and another for encap vlan 2001 (10.0.1.254). The PI VLAN assigned is randomly assigned on each leaf. But mapped to the same VNI (VXLAN ID).
```
MXS2-AP001# fabric 101 show ip int brief vrf vmenchac_T01:vmenchac_vrf_01
----------------------------------------------------------------
 Node 101 (MXS2-LF101)
----------------------------------------------------------------
IP Interface Status for VRF "vmenchac_T01:vmenchac_vrf_01"(46)
Interface            Address              Interface Status
vlan261              10.0.0.254/24        protocol-up/link-up/admin-up
vlan263              10.0.1.254/24        protocol-up/link-up/admin-up
```
```
MXS2-AP001# fabric 102 show ip int brief vrf vmenchac_T01:vmenchac_vrf_01
----------------------------------------------------------------
 Node 102 (MXS2-LF102)
----------------------------------------------------------------
IP Interface Status for VRF "vmenchac_T01:vmenchac_vrf_01"(23)
Interface            Address              Interface Status
vlan148              10.0.0.254/24        protocol-up/link-up/admin-up
vlan153              10.0.1.254/24        protocol-up/link-up/admin-up


MXS2-AP001#  
```
```
MXS2-AP001# fabric 101 show vlan id 261 extended 
----------------------------------------------------------------
 Node 101 (MXS2-LF101)
----------------------------------------------------------------

 VLAN Name                             Encap            Ports                    
 ---- -------------------------------- ---------------- ------------------------ 
 261  vmenchac_T01:vmenchac_bd_01      vxlan-15728690   Eth1/20, Po6             
```
```
MXS2-AP001# fabric 102 show vlan id 148 extended 
----------------------------------------------------------------
 Node 102 (MXS2-LF102)
----------------------------------------------------------------

 VLAN Name                             Encap            Ports                    
 ---- -------------------------------- ---------------- ------------------------ 
 148  vmenchac_T01:vmenchac_bd_01      vxlan-15728690   Eth1/20, Po4             

MXS2-AP001#
```
