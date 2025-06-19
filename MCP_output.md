# MCP LOOP

```
Leaf-102# show mcp internal loop-detection stats interface port-channel 2
------------------------------------------
Interface: port-channel2
--------------- LOOP-DETECTION STATS  ---------------
MCP packets sent(Per-vlan): 1797131
  MCP packets received: 228
MCP invalid packets received: 0
MCP packets received with invalid digest: 0
MCP packets received when switching state is disabled: 0
Number of active VLANs: 17
Number of active TX VLANs: 0
Number of VLANS in MCP packets are sent: 17
     MCP enabled vlans:
            2,    4,    5,    7,    9,   10,   16,  107,  110,  202
          212,  250,  260,  301,  550,  560,  561
        MCP loop detected at: Wed May 28 05:11:43 2025
   MCP loop detected in VLAN: 7                                 <<<<<
