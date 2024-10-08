LAB


single link down on other side:
```
354) FSM:<Ethernet1/45> Transition at 2024-10-05T08:05:59.365242000+00:00
    Previous state: [ETH_PORT_FSM_ST_WAIT_LOGICAL_CHANGE_TRUNK]
    Triggered event: [ETH_PORT_FSM_EV_LOGICAL_CHG_DONE]
    Next state: [ETH_PORT_FSM_ST_TRUNK_UP]
--
355) FSM:<Ethernet1/45> Transition at 2024-10-07T23:09:02.357192000+00:00
    Previous state: [ETH_PORT_FSM_ST_TRUNK_UP]
    Triggered event: [ETH_PORT_FSM_EV_LINK_DOWN]
    Next state: [FSM_ST_NO_CHANGE]
--
360) FSM:<Ethernet1/45> Transition at 2024-10-07T23:09:02.359215000+00:00
    Previous state: [ETH_PORT_FSM_ST_TRUNK_UP]
    Triggered event: [ETH_PORT_FSM_EV_LOGICAL_DOWN]
    Next state: [ETH_PORT_FSM_ST_WAIT_LOGICAL_DOWN]
--
375) FSM:<Ethernet1/45> Transition at 2024-10-07T23:09:02.382379000+00:00
    Previous state: [ETH_PORT_FSM_ST_WAIT_LOGICAL_DOWN]
    Triggered event: [ETH_PORT_FSM_EV_LOGICAL_DOWN_DONE]
    Next state: [ETH_PORT_FSM_ST_WAIT_PROTOCOL_DOWN]
--
381) FSM:<Ethernet1/45> Transition at 2024-10-07T23:09:02.383058000+00:00
    Previous state: [ETH_PORT_FSM_ST_WAIT_PROTOCOL_DOWN]
    Triggered event: [ETH_PORT_FSM_EV_PROTO_DOWN_DONE]
    Next state: [ETH_PORT_FSM_ST_PROTOCOL_DOWN]
--
382) FSM:<Ethernet1/45> Transition at 2024-10-07T23:09:02.383066000+00:00
    Previous state: [ETH_PORT_FSM_ST_PROTOCOL_DOWN]
    Triggered event: [ETH_PORT_FSM_EV_PHY_DOWN]
    Next state: [ETH_PORT_FSM_ST_WAIT_PHYSICAL_DOWN]
--
400) FSM:<Ethernet1/45> Transition at 2024-10-07T23:09:02.502160000+00:00
    Previous state: [ETH_PORT_FSM_ST_WAIT_PHYSICAL_DOWN]
    Triggered event: [ETH_PORT_FSM_EV_PHY_DOWN_DONE]
    Next state: [ETH_PORT_FSM_ST_WAIT_APPLY_CONFIG]
--
413) FSM:<Ethernet1/45> Transition at 2024-10-07T23:09:02.505923000+00:00
    Previous state: [ETH_PORT_FSM_ST_WAIT_APPLY_CONFIG]
    Triggered event: [ETH_PORT_FSM_EV_CFG_DONE]
    Next state: [ETH_PORT_FSM_ST_INIT_EVAL]
--
414) FSM:<Ethernet1/45> Transition at 2024-10-07T23:09:02.506771000+00:00
    Previous state: [ETH_PORT_FSM_ST_INIT_EVAL]
    Triggered event: [ETH_PORT_FSM_EV_IE_PORT_INIT]
    Next state: [ETH_PORT_FSM_ST_SPAN_EVAL]
--
415) FSM:<Ethernet1/45> Transition at 2024-10-07T23:09:02.506776000+00:00
    Previous state: [ETH_PORT_FSM_ST_SPAN_EVAL]
    Triggered event: [ETH_PORT_FSM_EV_NON_SPAN_DEST]
    Next state: [ETH_PORT_FSM_ST_WAIT_PRE_CFG]
--
434) FSM:<Ethernet1/45> Transition at 2024-10-07T23:09:02.538073000+00:00
    Previous state: [ETH_PORT_FSM_ST_WAIT_PRE_CFG]
    Triggered event: [ETH_PORT_FSM_EV_PRE_CFG_DONE]
    Next state: [ETH_PORT_FSM_ST_LINK_INIT]
--
435) FSM:<Ethernet1/45> Transition at 2024-10-07T23:09:03.533360000+00:00
    Previous state: [ETH_PORT_FSM_ST_LINK_INIT]
    Triggered event: [ETH_PORT_FSM_EV_PACER_TIMER_EXPIRED]
    Next state: [FSM_ST_NO_CHANGE]
--
436) FSM:<Ethernet1/45> Transition at 2024-10-07T23:11:20.444332000+00:00
    Previous state: [ETH_PORT_FSM_ST_LINK_INIT]
    Triggered event: [ETH_PORT_FSM_EV_LINK_UP]
    Next state: [ETH_PORT_FSM_ST_WAIT_BRINGUP]
--
```


port-channel member link down other side:

```
217) FSM:<Ethernet1/20> Transition at 2024-10-04T02:54:59.338609000+00:00
    Previous state: [ETH_PORT_FSM_ST_WAIT_BUNDLE_MEMBER_BRINGUP]
    Triggered event: [ETH_PORT_FSM_EV_FIRST_BRINGUP_BUNDLE_MEMBER_DONE]
    Next state: [ETH_PORT_FSM_ST_BUNDLE_MEMBER_UP]
--
218) FSM:<Ethernet1/20> Transition at 2024-10-07T23:15:32.137516000+00:00
    Previous state: [ETH_PORT_FSM_ST_BUNDLE_MEMBER_UP]
    Triggered event: [ETH_PORT_FSM_EV_EXTERNAL_REINIT_NO_FLAP_REQ]
    Next state: [FSM_ST_NO_CHANGE]
--
225) FSM:<Ethernet1/20> Transition at 2024-10-07T23:15:32.138027000+00:00
    Previous state: [ETH_PORT_FSM_ST_BUNDLE_MEMBER_UP]
    Triggered event: [ETH_PORT_FSM_EV_FEED_CHECK_LAST_TO_BUNDLE]
    Next state: [FSM_ST_NO_CHANGE]
--
226) FSM:<Ethernet1/20> Transition at 2024-10-07T23:15:32.220684000+00:00
    Previous state: [ETH_PORT_FSM_ST_BUNDLE_MEMBER_UP]
    Triggered event: [ETH_PORT_FSM_EV_PROTO_DOWN_RNF]
    Next state: [ETH_PORT_FSM_ST_WAIT_PROTOCOL_DOWN_RNF]
--
232) FSM:<Ethernet1/20> Transition at 2024-10-07T23:15:32.227598000+00:00
    Previous state: [ETH_PORT_FSM_ST_WAIT_PROTOCOL_DOWN_RNF]
    Triggered event: [ETH_PORT_FSM_EV_PROTO_DOWN_DONE]
    Next state: [ETH_PORT_FSM_ST_PROTOCOL_DOWN]
--
233) FSM:<Ethernet1/20> Transition at 2024-10-07T23:15:32.228069000+00:00
    Previous state: [ETH_PORT_FSM_ST_PROTOCOL_DOWN]
    Triggered event: [ETH_PORT_FSM_EV_EXTERNAL_REINIT_NO_FLAP_REQ]
    Next state: [ETH_PORT_FSM_ST_WAIT_BRINGUP]
--
243) FSM:<Ethernet1/20> Transition at 2024-10-07T23:15:32.239355000+00:00
    Previous state: [ETH_PORT_FSM_ST_WAIT_BRINGUP]
    Triggered event: [ETH_PORT_FSM_EV_MAP_PARAM_TO_CHANNEL]
    Next state: [No transition found]
--
245) FSM:<Ethernet1/20> Transition at 2024-10-07T23:15:42.240674000+00:00
    Previous state: [ETH_PORT_FSM_ST_WAIT_BRINGUP]
    Triggered event: [ETH_PORT_FSM_EV_SUSPEND_PORT_DUE_TO_NO_LACP_PDUS]
    Next state: [ETH_PORT_FSM_ST_PORT_SUSPENDED]
--
246) FSM:<Ethernet1/20> Transition at 2024-10-07T23:15:42.241796000+00:00
    Previous state: [ETH_PORT_FSM_ST_PORT_SUSPENDED]
    Triggered event: [ETH_PORT_FSM_EV_LINK_DOWN]
    Next state: [FSM_ST_NO_CHANGE]
--
251) FSM:<Ethernet1/20> Transition at 2024-10-07T23:15:42.243678000+00:00
    Previous state: [ETH_PORT_FSM_ST_PORT_SUSPENDED]
    Triggered event: [ETH_PORT_FSM_EV_PROTO_DOWN]
    Next state: [ETH_PORT_FSM_ST_WAIT_PROTOCOL_DOWN]
--
257) FSM:<Ethernet1/20> Transition at 2024-10-07T23:15:42.244872000+00:00
    Previous state: [ETH_PORT_FSM_ST_WAIT_PROTOCOL_DOWN]
    Triggered event: [ETH_PORT_FSM_EV_PROTO_DOWN_DONE]
    Next state: [ETH_PORT_FSM_ST_PROTOCOL_DOWN]
--
258) FSM:<Ethernet1/20> Transition at 2024-10-07T23:15:42.244879000+00:00
    Previous state: [ETH_PORT_FSM_ST_PROTOCOL_DOWN]
    Triggered event: [ETH_PORT_FSM_EV_PHY_DOWN]
    Next state: [ETH_PORT_FSM_ST_WAIT_PHYSICAL_DOWN]
--
275) FSM:<Ethernet1/20> Transition at 2024-10-07T23:15:42.367301000+00:00
    Previous state: [ETH_PORT_FSM_ST_WAIT_PHYSICAL_DOWN]
    Triggered event: [ETH_PORT_FSM_EV_PHY_DOWN_DONE]
    Next state: [ETH_PORT_FSM_ST_WAIT_APPLY_CONFIG]
--
288) FSM:<Ethernet1/20> Transition at 2024-10-07T23:15:42.371089000+00:00
    Previous state: [ETH_PORT_FSM_ST_WAIT_APPLY_CONFIG]
    Triggered event: [ETH_PORT_FSM_EV_CFG_DONE]
    Next state: [ETH_PORT_FSM_ST_INIT_EVAL]
--
289) FSM:<Ethernet1/20> Transition at 2024-10-07T23:15:42.371409000+00:00
    Previous state: [ETH_PORT_FSM_ST_INIT_EVAL]
    Triggered event: [ETH_PORT_FSM_EV_IE_PORT_INIT]
    Next state: [ETH_PORT_FSM_ST_SPAN_EVAL]
--
290) FSM:<Ethernet1/20> Transition at 2024-10-07T23:15:42.371415000+00:00
    Previous state: [ETH_PORT_FSM_ST_SPAN_EVAL]
    Triggered event: [ETH_PORT_FSM_EV_NON_SPAN_DEST]
    Next state: [ETH_PORT_FSM_ST_WAIT_PRE_CFG]
--
308) FSM:<Ethernet1/20> Transition at 2024-10-07T23:15:42.432852000+00:00
    Previous state: [ETH_PORT_FSM_ST_WAIT_PRE_CFG]
    Triggered event: [ETH_PORT_FSM_EV_PRE_CFG_DONE]
    Next state: [ETH_PORT_FSM_ST_LINK_INIT]
--
309) FSM:<Ethernet1/20> Transition at 2024-10-07T23:15:43.427626000+00:00
    Previous state: [ETH_PORT_FSM_ST_LINK_INIT]
    Triggered event: [ETH_PORT_FSM_EV_PACER_TIMER_EXPIRED]
    Next state: [FSM_ST_NO_CHANGE]
--
310) FSM:<Ethernet1/20> Transition at 2024-10-07T23:18:06.854209000+00:00
    Previous state: [ETH_PORT_FSM_ST_LINK_INIT]
    Triggered event: [ETH_PORT_FSM_EV_LINK_UP]
    Next state: [ETH_PORT_FSM_ST_WAIT_BRINGUP]
```






