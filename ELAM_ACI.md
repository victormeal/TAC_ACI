# ELAM - ACI


```
vsh_lc
debug platform internal roc elam asic 0
trigger reset
trigger init in-select 6 out-select 0
reset
set outer ipv4 dst_ip 10.0.0.1 src_ip 10.0.1.2
start
status
ereport
```
```
ereport | egrep "Incoming Interface"
ereport | egrep ovector
show plat int hal l2 port gpd
```

```
MXS2-LF104# show mod

Mod  Ports  Module-Type                         Model              Status
---  -----  ----------------------------------- ------------------ ----------
1    60     48x10/25G+12x100G Switch            N9K-C93240YC-FX2   ok        


Mod  Sw              Hw
---  --------------  ------
1    15.2(7g)        2.0   


Mod  MAC-Address(es)                         Serial-Num
---  --------------------------------------  ----------
1    4c-5d-3c-cd-70-19 to 4c-5d-3c-cd-70-59  FDO252106H2


Mod  Online Diag Status
---  ------------------
1    pass      

MXS2-LF104# 
MXS2-LF104# vsh_lc
module-1# debug platform internal tah elam asic 0
Invalid CLI for platform type - TAH
module-1# debug platform internal roc elam asic 0
module-1(DBG-elam)# trigger reset 
module-1(DBG-elam)# trigger init in-select ?
  10  Outerl4-innerl4-ieth
  13  Outer(l2|l3|l4)-inner(l2|l3|l4)-noieth
  14  Outer(l2(vntag)|l3|l4)-inner(l2|l3|l4)-ieth
  15  Outer(l2|l3|l4)-inner(l2|l3|l4)-ieth
  6   Outerl2-outerl3-outerl4
  7   Innerl2-innerl3-innerl4
  8   Outerl2-innerl2-ieth
  9   Outerl3-innerl3

module-1(DBG-elam)# trigger init in-select 6 out-select 0
module-1(DBG-elam-insel6)# set outer ipv4 dst_ip 10.0.0.1 src_ip 10.0.1.2
module-1(DBG-elam-insel6)# start
module-1(DBG-elam-insel6)# status
 ELAM STATUS
===========
Asic 0 Slice 0 Status Armed
Asic 0 Slice 1 Status Armed

module-1(DBG-elam-insel6)#
module-1(DBG-elam-insel6)# status
 ELAM STATUS
===========
Asic 0 Slice 0 Status Triggered
Asic 0 Slice 1 Status Armed

module-1(DBG-elam-insel6)# 
module-1(DBG-elam-insel6)# ereport
Python available. Continue ELAM decode with LC Pkg
 ELAM REPORT 

======================================================================================================================================================
                                                        Trigger/Basic Information                                                                     
======================================================================================================================================================
ELAM Report File                        : /tmp/logs/elam_2024-08-07-28m-20h-22s.txt
In-Select Trigger                       : Outerl2-outerl3-outerl4( 6 )            
Out-Select Trigger                      : Pktrw-sideband-sb_info( 0 )             
ELAM Captured Device                    : LEAF                                    
Packet Direction                        : ingress                                 
Triggered ASIC type                     : Heavenly                                
Triggered ASIC instance                 : 0                                       
Triggered Slice                         : 0                                       
Incoming Interface                      : 0x62( 0x62 )                            
( Slice Source ID(Ss) in "show plat int hal l2 port gpd" )

======================================================================================================================================================
                                                            Captured Packet                                                                           

======================================================================================================================================================

------------------------------------------------------------------------------------------------------------------------------------------------------
Outer Packet Attributes
------------------------------------------------------------------------------------------------------------------------------------------------------
Outer Packet Attributes       : l2uc ipv4 ip ipuc ipv4uc                
Opcode                        : OPCODE_UC                               

------------------------------------------------------------------------------------------------------------------------------------------------------
Outer L2 Header
------------------------------------------------------------------------------------------------------------------------------------------------------
Destination MAC               : 0022.BDF8.19FF                          
Source MAC                    : 2001.2001.0148                          
802.1Q tag is valid           : yes( 0x1 )                              
CoS                           : 7( 0x7 )                                
Access Encap VLAN             : 2001( 0x7D1 )                           

------------------------------------------------------------------------------------------------------------------------------------------------------
Outer L3 Header
------------------------------------------------------------------------------------------------------------------------------------------------------
L3 Type                       : IPv4                                    
IP Version                    : 4                                       
DSCP                          : 0                                       
IP Packet Length              : 84 ( = IP header(28 bytes) + IP payload )
Don't Fragment Bit            : not set                                 
TTL                           : 255                                     
IP Protocol Number            : ICMP                                    
IP CheckSum                   : 53989( 0xD2E5 )                         
Destination IP                : 10.0.0.1                                
Source IP                     : 10.0.1.2                                

======================================================================================================================================================
                                                                Forwarding Lookup ( FPB )
======================================================================================================================================================

------------------------------------------------------------------------------------------------------------------------------------------------------
Destination IP (Lookup Key)
------------------------------------------------------------------------------------------------------------------------------------------------------
Dst IP Lookup was performed             : yes                           
Dst IP Lookup VRF                       : 4645( 0x1225 )                
( Hw VrfId in "show plat int hal l3 vrf pi" )
Dst IP Address                          : 10.0.0.1                      

------------------------------------------------------------------------------------------------------------------------------------------------------
Destination IP (Lookup Result)
------------------------------------------------------------------------------------------------------------------------------------------------------
Dst IP is Hit                           : yes                           
Dst IP Hit Index                        : 24975( 0x618F )               
( HIT IDX in "show plat int hal l3 routes")
ECMP Pointer is valid                   : no                            
( Ecmp ID in "show plat int hal l3 ecmp")
TRIE Pointer is valid                   : yes                           
( Trie PID in "show plat int hal l3 routes")
NextHop L2 Pointer is valid             : yes                           
NextHop L2 Pointer                      : 32825( 0x8039 )               
( NB Hw Idx in "show plat int hal l3 routes" and HIT IDX in "show plat int hal l3 nexthops")

------------------------------------------------------------------------------------------------------------------------------------------------------
Source IP (Lookup Key)
------------------------------------------------------------------------------------------------------------------------------------------------------
Src IP Lookup was performed             : yes                           
Force Src MAC Lookup                    : no                            
if yes, no learning, src EPG classification with src IP. check src MAC.
Src IP Lookup VRF                       : 4645( 0x1225 )                
( Hw VrfId in "show plat int hal l3 vrf pi" )
Src IP Address                          : 10.0.1.2                      

------------------------------------------------------------------------------------------------------------------------------------------------------
Source IP (Lookup Result)
------------------------------------------------------------------------------------------------------------------------------------------------------
Src IP is Hit                           : yes                           
Src IP Hit Index                        : 24968( 0x6188 )               
( HIT IDX in "show plat int hal l3 routes")
ECMP Pointer is valid                   : no                            
( Ecmp ID in "show plat int hal l3 ecmp")
TRIE Pointer is valid                   : yes                           
( Trie PID in "show plat int hal l3 routes")
NextHop L2 Pointer is valid             : yes                           
NextHop L2 Pointer                      : 2491( 0x9BB )                 
( NB Hw Idx in "show plat int hal l3 routes" and HIT IDX in "show plat int hal l3 nexthops")

------------------------------------------------------------------------------------------------------------------------------------------------------
Destination MAC (Lookup Key)
------------------------------------------------------------------------------------------------------------------------------------------------------
Dst MAC Lookup was performed            : no                            
Dst MAC Lookup BD                       : 578( 0x242 )                  
( Hw BDID in "show plat int hal l2 bd pi" )
Dst MAC Address                         : 0022.BDF8.19FF                

------------------------------------------------------------------------------------------------------------------------------------------------------
Destination MAC (Lookup Result)
------------------------------------------------------------------------------------------------------------------------------------------------------
Dst MAC Lookup was not performed        : N/A                           

------------------------------------------------------------------------------------------------------------------------------------------------------
Source MAC (Lookup Key)
------------------------------------------------------------------------------------------------------------------------------------------------------
Src MAC Lookup was performed            : yes                           
Src MAC Lookup BD                       : 578( 0x242 )                  
( Hw BDID in "show plat int hal l2 bd pi" )
Src MAC Address                         : 2001.2001.0148                

------------------------------------------------------------------------------------------------------------------------------------------------------
Source MAC (Lookup Result)
------------------------------------------------------------------------------------------------------------------------------------------------------
Src MAC is Hit                          : yes( 0x1 )                    
Src MAC is Hit Index                    : 2491( 0x9BB )                 
( phy_id in "show plat int hal objects ep l2 mac (MAC) extensions" or HIT IDX in "show plat int hal l3 nexthops" for L3OUT/L3 EP)

======================================================================================================================================================
                                                                Contract Lookup ( FPC )
======================================================================================================================================================

------------------------------------------------------------------------------------------------------------------------------------------------------
Contract Lookup Key
------------------------------------------------------------------------------------------------------------------------------------------------------
IP Protocol                             : ICMP( 0x1 )                   
L4 Src Port                             : 2048( 0x800 )                 
L4 Dst Port                             : 20088( 0x4E78 )               
sclass (src pcTag)                      : 16389( 0x4005 )               
dclass (dst pcTag)                      : 16388( 0x4004 )               
src pcTag is from local table           : yes                           
derived from a local table on this node by the lookup of src IP or MAC
Unknown Unicast / Flood Packet          : no                            
If yes, Contract is not applied here because it is flooded

------------------------------------------------------------------------------------------------------------------------------------------------------
Contract Result
------------------------------------------------------------------------------------------------------------------------------------------------------
Contract Drop                           : no                            
Contract Logging                        : no                            
Contract Applied                        : yes                           
Contract Hit                            : yes                           
Contract Aclqos Stats Index             : 81588                         
( show sys int aclqos zoning-rules | grep -B 9 "Idx: 81588" )

======================================================================================================================================================
                                                          Look Up Blocks Information
======================================================================================================================================================
MY TEP HIT                              : no( 0x0 )                     
MY TEP Index                            : 0                             
( "show ip int lo0" or "show plat int sug tab tah_sug_lua_mytepkeytable 0" )
Tenant RMAC Address                     : 2( 0x2 )                      
BD in LUB lookup                        : 578( 0x242 )                  
BD Profile Index                        : 2( 0x2 )                      
EPG in LUB lookup                       : 11287( 0x2C17 )               
VIF Profile Index                       : 15( 0xF )                     
Infra RMAC Address                      : 0( 0x0 )                      
PIF Index                               : 49( 0x31 )                    

======================================================================================================================================================
                                             Flood/Multicast or Forwarding to Remote Leaf ( LUC,LUD )
======================================================================================================================================================
Dst Pointer is Flood Pointer            : no                            
Dst is Tunnel                 
Dst Pointer                             : 12333( 0x302D )               
DstInfoIdx in "show plat int hal tunnel rtep apd"

======================================================================================================================================================
                                                             SUP-TCAM ( ACX )
======================================================================================================================================================
SUP-TCAM Hit Index                      : None. No Rule was applied     

======================================================================================================================================================
                                                         Table Lookup Results
======================================================================================================================================================
Vif Table Lookup                        : hit DLEFT table with index: 0xA9
Outer Vlan XLate  Table Lookup          : hit DLEFT table with index: 0x1FF
Vlan Xlate Table Lookup                 : hit DLEFT table with index: 0x1B9E
RW Vlan Xlate Table Lookup              : hit DLEFT table with index: 0x757
Rw Encap Table capture access           : 11( 0xB )                     
Rw Outer BD State Table capture access  : 2( 0x2 )                      
Rw BD State Table capture access        : 4645( 0x1225 )                
Rw EPG State Table capture access       : 4645( 0x1225 )                
Rw Tenant RMAC Table capture access     : 1( 0x1 )                      
Rw Source IP Address Table capture access: 2( 0x2 )                      
Rw Source MAC Address Table capture access: 2( 0x2 )                      

======================================================================================================================================================
                                                         FPX Latch Results 
======================================================================================================================================================

------------------------------------------------------------------------------------------------------------------------------------------------------
SA notify Information
------------------------------------------------------------------------------------------------------------------------------------------------------
SA notify -Bind notify Enable           : yes( 0x1 )                    
SA notify -SA notify Enable             : yes( 0x1 )                    
SA notify -Sclass notify Enable         : yes( 0x1 )                    
SA notify -IP route                     : yes( 0x1 )                    
SA notify -Interface                    : 11( 0xB )                     

------------------------------------------------------------------------------------------------------------------------------------------------------
FPX Result Vector 
------------------------------------------------------------------------------------------------------------------------------------------------------
FIB SA - Match prefix Length            : 32( 0x20 )                    
FIB SA - L2 Pointer Valid               : yes( 0x1 )                    
FIB SA - TCAM hit                       : no( 0x0 )                     
FIB SA - TCAM hit Index                 : 24968( 0x6188 )               
FIB DA - Match prefix Length            : 32( 0x20 )                    
FIB DA - L2 Pointer Valid               : yes( 0x1 )                    
FIB DA - L2 Pointer                     : 32825( 0x8039 )               
FIB DA - TCAM hit                       : no( 0x0 )                     
FIB DA - TCAM hit Index                 : 24975( 0x618F )               
MAC SA - TCAM hit                       : no( 0x0 )                     
MAC SA - TCAM hit Index                 : 2491( 0x9BB )                 
MAC DA - TCAM hit                       : no( 0x0 )                     
MAC DA - TCAM hit Index                 : 2491( 0x9BB )                 

------------------------------------------------------------------------------------------------------------------------------------------------------
FPX MAC DA/SA Information 
------------------------------------------------------------------------------------------------------------------------------------------------------
MAC SA - Interface                      : 11( 0xB )                     
MAC SA - L2 Info Valid                  : yes( 0x1 )                    
MAC SA - L2 Bind Pass                   : yes( 0x1 )                    
MAC SA - L2 Pointer                     : 2491( 0x9BB )                 
MAC DA - Interface                      : 2125869( 0x20702D )           
MAC DA - L2 Info Valid                  : yes( 0x1 )                    

------------------------------------------------------------------------------------------------------------------------------------------------------
FPX IFABRIC  FIB SA  Information 
------------------------------------------------------------------------------------------------------------------------------------------------------
FIB SA L3 info - Sclass                 : 1( 0x1 )                      
FIB SA L3 info - Source policy incomplete : no( 0x0 )                     
FIB SA L3 info - Bind Notify Enable     : yes( 0x1 )                    
FIB SA L3 info - SA Notify Enable       : yes( 0x1 )                    
FIB SA L3 info - Sclass Notify Enable   : yes( 0x1 )                    

------------------------------------------------------------------------------------------------------------------------------------------------------
FPX IFABRIC  FIB DA  Information 
------------------------------------------------------------------------------------------------------------------------------------------------------
FIB DA L3 info - Sclass                 : 1( 0x1 )                      
FIB DA L3 info - Dest policy incomplete : no( 0x0 )                     

------------------------------------------------------------------------------------------------------------------------------------------------------
FPX IFABRIC  MAC SA  Information 
------------------------------------------------------------------------------------------------------------------------------------------------------
MAC SA L2 info - Sclass                 : 1( 0x1 )                      
MAC SA L2 info - EPG                    : 11287( 0x2C17 )               
MAC SA L2 info - Source policy incomplete : no( 0x0 )                     
MAC SA L2 info - Bind Notify Enable     : no( 0x0 )                     
MAC SA L2 info - SA Notify Enable       : yes( 0x1 )                    
MAC SA L2 info - Sclass Notify Enable   : yes( 0x1 )                    

------------------------------------------------------------------------------------------------------------------------------------------------------
FPX IFABRIC  MAC DA  Information 
------------------------------------------------------------------------------------------------------------------------------------------------------
MAC DA L2 info - Dest policy incomplete : no( 0x0 )                     

======================================================================================================================================================
                                                         Rewrite Information ( RW )
======================================================================================================================================================

------------------------------------------------------------------------------------------------------------------------------------------------------
iEth Information
------------------------------------------------------------------------------------------------------------------------------------------------------
Packet from CPU                         : no                            
Packet from vPC peer LEAF               : no                            
Packet from tunnel (remote leaf/avs)    : no                            
Packet to tunnel (remote leaf/avs)      : yes                           
iEth SUP code                           : NONE( 0x0 )                   
Destination Interface (Dst ASIC Port)   : 93( 0x5D )                    
ASIC Port(AP) in "show plat int hal l2 port gpd"  or Flood MET index
Destination Interface (Dst Logical Index) : 2( 0x2 )                      
LID in "show plat int hal l2 port pi"
Source Interface (Src ASIC Port)        : 50( 0x32 )                    
ASIC Port(AP) in "show plat int hal l2 port gpd"
Source Interface (Src Logical Index)    : 11( 0xB )                     
LID in "show plat int hal l2 port pi"
Source Interface (Src Slice ID)         : 98( 0x62 )                    
Slice Source ID(Ss) in "show plat int hal l2 port gpd"
VNID Use BD                             : yes( 0x1 )                    

------------------------------------------------------------------------------------------------------------------------------------------------------
iFabric Information
------------------------------------------------------------------------------------------------------------------------------------------------------
Destination EPG HW-ID                   : 4645( 0x1225 )                
Hw EPGID in "show plat int hal l2 fd pi"
Source      EPG HW-ID                   : 11287( 0x2C17 )               
Hw EPGID in "show plat int hal l2 fd pi"
Destination EPG pcTag (dclass)          : 16388( 0x4004 )               
Source      EPG pcTag (sclass)          : 16389( 0x4005 )               

------------------------------------------------------------------------------------------------------------------------------------------------------
Other Forwarding Information
------------------------------------------------------------------------------------------------------------------------------------------------------
Overall SUP code                        : NONE( 0x0 )                   
Encap Index is valid                    : yes                           
Destination is remote TEP (tunnel)
Encap Index                             : 46( 0x2E )                    
RwEncapIdx in "show plat int hal tunnel rtep apd"
Forwarding Operation                    : mytep_fwd_uc_route            

------------------------------------------------------------------------------------------------------------------------------------------------------
Sideband Information
------------------------------------------------------------------------------------------------------------------------------------------------------
ovector                                 : 296( 0x128 )                  
Ovec in "show plat int hal l2 port gpd"
Opcode                                  : OPCODE_UC                     

------------------------------------------------------------------------------------------------------------------------------------------------------
Sideband SB Information
------------------------------------------------------------------------------------------------------------------------------------------------------
output slice vector (egress ASIC slices) : Packet egresses from slices: 1
Packet is BPDU                          : no                            
Packet Direction                        : ingress ( front panel (or cpu) -> leaf )
Flood to EPG                            : no                            
Packet is towards CPU                   : no                            

------------------------------------------------------------------------------------------------------------------------------------------------------
Sideband SB Multicast Information
------------------------------------------------------------------------------------------------------------------------------------------------------
BD                                      : 4645( 0x1225 )                
Source is l3 interface                  : no                            
FTAG                                    : 10( 0xA )                     
RPF Fail                                : no                            
Packet Hash                             : 44( 0x2C )                    
Is my TEP                               : no                            
Souce is VPC Peer                       : no                            
Source Sh Group                         : 0( 0x0 )                      
IS IPV6                                 : no                            
Outer MC use MET                        : no                            
BD fabric Copy Enable                   : no                            
Source interface number                 : 66( 0x42 )                    
Is EPG                                  : yes                           
RX SPAN Enable                          : no                            
TX SPAN Enable                          : no                            

------------------------------------------------------------------------------------------------------------------------------------------------------
FINAL FORWARDING LOOKUP 
------------------------------------------------------------------------------------------------------------------------------------------------------
Bits set in Final Forwarding Block:     : IFABRIC_IG UC TENANT MYTEP ROUTE HIT 

------------------------------------------------------------------------------------------------------------------------------------------------------

------------------------------------------------------------------------------------------------------------------------------------------------------
Lookup Drop
------------------------------------------------------------------------------------------------------------------------------------------------------
LU drop reason                          : no drop   
<snip>



```
### Incoming Interface
```
module-1(DBG-elam-insel6)# ereport | egrep "Incoming Interface"
Incoming Interface                      : 0x62( 0x62 )                            
module-1(DBG-elam-insel6)# 
```
#### Outgoing Interface
```
module-1(DBG-elam-insel6)# ereport | egrep ovector
ovector                                 : 296( 0x128 )                  
  hea_elam_out_sidebnd_no_spare_vec.ovector_idx: 0x128
  hea_luc_latch_results_vec.luc7_0.uc_ovector_idx: 0x128
  hea_lud_latch_results_vec.lud2_0.acl_redir_ovector_idx: 0x0
  hea_lud_latch_results_vec.lud4_1.ovector_idx: 0x128
    hea_flop_elam_out_vec.sidebnd.ovector_idx: 0x128
module-1(DBG-elam-insel6)# 
```
```
module-1(DBG-elam-insel6)# show plat int hal l2 port gpd
No sandboxes exist
Legend:
-------
IfId:       Interface Id                                    IfName:      Interface Name
I P:        Is PC Mbr                                       IfId:           Interface Id
Uc PC Cfg:      UcPcCfg Idx                                 Uc PC MbrId:    Uc Pc Mbr Id
As:             Asic                                        AP:             Asic Port
Sl:             Slice                                       Sp:             Slice Port
Ss:             Slice SrcId                                 Ovec:           Ovector (slice | srcid)
L S:            Local Slot                                  Reprogram:                                                  
L3:             Is L3
    P:    PifTable                                          Xla Idx:        Xlate Idx
    RP:   Rw PifTable                                       Ovx Idx:        OXlate Idx
    IP:   If Profile Table                                  N L3:           Num. of L3 Ifs
    RS:   Rw SrcId Table                                    NI L3:          Num. of Infra L3 Ifs
    DP:   DPort Table                                       Vif Tid:        Vif Tid
    SP:   SrcPortState Table                                RwV Tid:        RwVif Tid
    RSP:  RwSrcPortstate Table                              Ing Lbl:        Ingress Acl Label
    UC:   UCPcCfg                                           Egr Lbl:        Egress Acl Label
    UM:   UCPcMbr                                           Reprogram:                                                  
PROF ID:        Lport Profile Id
    VS:   VifStateTable                                     HI:             LportProfile Hw Install
    RV:   Rw VifTable                                       
Num. of Sandboxes: 1

Sandbox_ID: 0, BMP: 0x0
 Port Count: 19

==============================================================================================================================================
                       Uc   Uc                          |       Reprogram       |                                         | Rep |            
                     I PC   Pc                        L |   R I R D    R  U U X | L Xla Ovx N  NI Vif    RwV    Ing  Egr  | V R | PROF H     
IfId     Ifname      P Cfg  MbrID As AP  Sl Sp Ss Ovec S | P P P S P Sp Sp C M L | 3 Idx Idx L3 L3 Tid    Tid    Lbl  Lbl  | S V | ID   I  smac   
===============================================================================================================================================
1a000000 Eth1/1      0 3a   1b    0  6d  1  24 48 148  1   0 0 0 0 0 0  0  0 0 0   1 7   0   1  0  D-154  -      0    0      1 0   7    0 0   
1a001000 Eth1/2      1 0    3d    0  71  1  28 50 150  1   0 0 0 0 0 0  0  0 0 0   0 0   0   0  0  -      -      0    0      1 0   0    0 0   
1a002000 Eth1/3      0 5a   3b    0  75  1  2c 58 158  1   0 1 0 0 0 0  0  0 0 0   0 0   0   0  0  D-2c2  -      0    0      1 1   27   0 0   
1a004000 Eth1/5      0 40   21    0  72  1  29 52 152  1   0 0 0 0 0 0  0  0 0 0   0 0   0   0  0  D-293  -      400  0      1 0   29   0 0   
1a005000 Eth1/6      0 4e   2f    0  76  1  2d 5a 15a  1   0 0 0 0 0 0  0  0 0 0   0 0   0   0  0  D-312  -      400  0      1 0   2b   0 0   
1a006000 Eth1/7      0 4c   2d    0  6f  1  26 4c 14c  1   0 0 0 0 0 0  0  0 0 0   0 0   0   0  0  D-128  -      400  0      1 0   2e   0 0   
1a007000 Eth1/8      0 4a   2b    0  73  1  2a 54 154  1   0 0 0 0 0 0  0  0 0 0   0 0   0   0  0  D-27b  -      400  0      1 0   2a   0 0   
1a008000 Eth1/9      0 3c   1d    0  77  1  2e 5c 15c  1   0 0 0 0 0 0  0  0 0 0   0 0   0   0  0  D-207  -      0    0      0 0   9    0 0   
1a009000 Eth1/10     0 48   29    0  70  1  27 4e 14e  1   0 0 0 0 0 0  0  0 0 0   0 0   0   0  0  D-41   -      0    0      0 0   15   0 0   
1a00a000 Eth1/11     0 52   33    0  74  1  2b 56 156  1   0 0 0 0 0 0  0  0 0 0   0 0   0   0  0  D-10   -      0    0      0 0   1f   0 0   
1a00b000 Eth1/12     0 50   31    0  78  1  2f 5e 15e  1   0 0 0 0 0 0  0  0 0 0   0 0   0   0  0  D-22a  -      0    0      1 0   1d   0 0   
1a00c000 Eth1/13     0 3e   1f    0  79  1  30 60 160  1   0 0 0 0 0 0  0  0 0 0   0 0   0   0  0  D-3d   -      400  0      1 0   28   0 0   
1a00d000 Eth1/14     0 54   35    0  7a  1  31 62 162  1   0 0 0 0 0 0  0  0 0 0   0 0   0   0  0  D-343  -      400  0      1 0   2d   0 0   
1a017000 Eth1/24     0 46   27    0  84  1  3b 76 176  1   0 0 0 0 0 0  0  0 0 0   0 0   0   0  0  D-1c0  -      400  0      1 0   30   0 0   
1a023000 Eth1/36     0 44   25    0  3d  0  3c 78 78   1   0 0 0 0 0 0  0  0 0 0   0 0   0   0  0  D-3fa  -      400  0      1 0   31   0 0   
1a02c000 Eth1/45     0 42   23    0  32  0  31 62 62   1   0 0 0 0 0 0  0  0 0 0   0 0   0   0  0  D-a9   -      0    0      0 0   f    0 0   
1a032000 Eth1/51     0 1    15    0  51  1  8  10 110  1   0 0 0 0 0 0  0  0 0 0   1 4   2   2  2  D-16a  -      200  0      0 0   5    0 0   
1a033000 Eth1/52     0 3    19    0  59  1  10 20 120  1   0 0 0 0 0 0  0  0 0 0   1 6   4   2  2  D-350  -      200  0      0 0   5    0 0   
1a034000 Eth1/53     0 2    17    0  5d  1  14 28 128  1   0 0 0 0 0 0  0  0 0 0   1 5   3   2  2  D-24d  -      200  0      0 0   5    0 0   
module-1(DBG-elam-insel6)# 
```
