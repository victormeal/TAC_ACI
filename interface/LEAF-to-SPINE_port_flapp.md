# LEAF-to-SPINE_port_flapp

```
349) FSM:<Ethernet1/51> Transition at 2024-11-22T15:53:30.775640000-06:00
    Previous state: [ETH_PORT_FSM_ST_L3_UP]
    Triggered event: [ETH_PORT_FSM_EV_SI_BRINGUP_DONE]
    Next state: [FSM_ST_NO_CHANGE]
```
+ Admin down other side (SPINE port)
```

350) FSM:<Ethernet1/51> Transition at 2024-11-25T17:32:06.808294000-06:00
    Previous state: [ETH_PORT_FSM_ST_L3_UP]
    Triggered event: [ETH_PORT_FSM_EV_LINK_DOWN]
    Next state: [FSM_ST_NO_CHANGE]

351) Event:ESQ_START length:38, at 808339 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq Type:SERIAL

352) Event:ESQ_REQ length:38, at 811708 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq:Graceful shut steps to skip

353) Event:ESQ_REQ length:38, at 811718 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_TX] Dst:MTS_SAP_REGISTRY(0), Opc:MTS_OPC_IM_L3_IF_GRACEFUL_DOWN(62520)

354) Event:ESQ_REQ length:38, at 813045 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq:send state change

355) FSM:<Ethernet1/51> Transition at 2024-11-25T17:32:06.813154000-06:00
    Previous state: [ETH_PORT_FSM_ST_L3_UP]
    Triggered event: [ETH_PORT_FSM_EV_LOGICAL_DOWN]
    Next state: [ETH_PORT_FSM_ST_WAIT_LOGICAL_DOWN]

356) FSM:<Ethernet1/51> Transition at 2024-11-25T17:32:06.813201000-06:00
    Previous state: [ETH_PORT_FSM_ST_WAIT_LOGICAL_DOWN]
    Triggered event: [ETH_PORT_FSM_EV_SI_BRINGDOWN_CMD]
    Next state: [FSM_ST_NO_CHANGE]

357) FSM:<Ethernet1/51> Transition at 2024-11-25T17:32:06.813215000-06:00
    Previous state: [ETH_PORT_FSM_ST_WAIT_LOGICAL_DOWN]
    Triggered event: [ETH_PORT_FSM_EV_SI_BRINGDOWN]
    Next state: [FSM_ST_NO_CHANGE]

358) Event:ESQ_START length:38, at 813237 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq Type:SERIAL

359) Event:ESQ_REQ length:38, at 816321 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq:SI_BRINGDOWN_SEQ_EVAL

360) Event:ESQ_REQ length:38, at 816382 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq:Bringdown Linux netdevices

361) Event:ESQ_REQ length:38, at 819145 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_TX] Dst:MTS_SAP_REGISTRY(0), Opc:MTS_OPC_IM_L3_PROTOCOL_STATE_CHANGE(62472)

362) Event:ESQ_REQ length:38, at 819214 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_TX] Dst:MTS_SAP_OSPF(320), Opc:MTS_OPC_ETHPM_PORT_CLEANUP(61444)

363) Event:ESQ_REQ length:38, at 819871 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_TX] Dst:MTS_SAP_ELTM(192), Opc:MTS_OPC_ETHPM_SI_LOGICAL_BRINGDOWN(61463)

364) Event:ESQ_RSP length:38, at 827798 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_RX] Src:MTS_SAP_ELTM(192), Opc:MTS_OPC_ETHPM_SI_LOGICAL_BRINGDOWN(61463)

365) FSM:<Ethernet1/51> Transition at 2024-11-25T17:32:06.827910000-06:00
    Previous state: [ETH_PORT_FSM_ST_WAIT_LOGICAL_DOWN]
    Triggered event: [ETH_PORT_FSM_EV_SI_BRINGDOWN_DONE]
    Next state: [FSM_ST_NO_CHANGE]

366) FSM:<Ethernet1/51> Transition at 2024-11-25T17:32:06.827930000-06:00
    Previous state: [ETH_PORT_FSM_ST_WAIT_LOGICAL_DOWN]
    Triggered event: [ETH_PORT_FSM_EV_LOGICAL_DOWN_DONE]
    Next state: [ETH_PORT_FSM_ST_WAIT_PROTOCOL_DOWN]

367) Event:ESQ_START length:38, at 827948 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq Type:SERIAL

368) Event:ESQ_REQ length:38, at 830984 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq:determine steps to skip

369) Event:ESQ_REQ length:38, at 831032 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq:Send state change for shared intf if not sent in log down

370) Event:ESQ_REQ length:38, at 831127 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_TX] Dst:MTS_SAP_ETH_PORT_CHANNEL_MGR(378), Opc:MTS_OPC_ETHPM_PORT_CLEANUP(61444)
    RRtoken:0x0060AFF5

371) Event:ESQ_RSP length:38, at 831296 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_RX] Src:MTS_SAP_ETH_PORT_CHANNEL_MGR(378), Opc:MTS_OPC_ETHPM_PORT_CLEANUP(61444)
    RRtoken:0x0060AFF5

372) FSM:<Ethernet1/51> Transition at 2024-11-25T17:32:06.831399000-06:00
    Previous state: [ETH_PORT_FSM_ST_WAIT_PROTOCOL_DOWN]
    Triggered event: [ETH_PORT_FSM_EV_PROTO_DOWN_DONE]
    Next state: [ETH_PORT_FSM_ST_PROTOCOL_DOWN]

373) FSM:<Ethernet1/51> Transition at 2024-11-25T17:32:06.831405000-06:00
    Previous state: [ETH_PORT_FSM_ST_PROTOCOL_DOWN]
    Triggered event: [ETH_PORT_FSM_EV_PHY_DOWN]
    Next state: [ETH_PORT_FSM_ST_WAIT_PHYSICAL_DOWN]

374) Event:ESQ_START length:38, at 831459 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq Type:SERIAL

375) Event:ESQ_REQ length:38, at 834452 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq:determine steps to skip

376) Event:ESQ_REQ length:38, at 837160 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_TX] Dst:MTS_SAP_REGISTRY(0), Opc:MTS_OPC_IM_PHY_LINK_STATE_CHANGE(62470)

377) Event:ESQ_REQ length:38, at 839816 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_TX] Dst:MTS_SAP_PORT_CLIENT(181), Opc:MTS_OPC_LC_PORT_CLIENT_CONFIG(8186)
    RRtoken:0x0060B01C

378) Event:ESQ_RSP length:38, at 846598 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_RX] Src:MTS_SAP_PORT_CLIENT(181), Opc:MTS_OPC_LC_PORT_CLIENT_CONFIG(8186)
    RRtoken:0x0060B01C

379) Event:ESQ_REQ length:38, at 846607 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq:Wait for debounce logic

380) Event:ESQ_RSP length:38, at 846693 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq:Wait for debounce logic

381) Event:ESQ_REQ length:38, at 846767 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_TX] Dst:MTS_SAP_FCOE(473), Opc:MTS_OPC_ETHPM_PORT_PHY_CLEANUP(61446)

382) Event:ESQ_REQ length:38, at 846830 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_TX] Dst:MTS_SAP_CTS(400), Opc:MTS_OPC_ETHPM_PORT_PHY_CLEANUP(61446)
    RRtoken:0x0060B03A

383) Event:ESQ_RSP length:38, at 847107 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_RX] Src:MTS_SAP_CTS(400), Opc:MTS_OPC_ETHPM_PORT_PHY_CLEANUP(61446)
    RRtoken:0x0060B03A

384) Event:ESQ_REQ length:38, at 847175 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_TX] Dst:MTS_SAP_MFDM_L2_UPDATE(213), Opc:MTS_OPC_ETHPM_PORT_PHY_CLEANUP(61446)
    RRtoken:0x0060B03C

385) Event:ESQ_RSP length:38, at 847383 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_RX] Src:MTS_SAP_MFDM_L2_UPDATE(213), Opc:MTS_OPC_ETHPM_PORT_PHY_CLEANUP(61446)
    RRtoken:0x0060B03C

386) Event:ESQ_REQ length:38, at 847819 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_TX] Dst:MTS_SAP_L2FM(221), Opc:MTS_OPC_ETHPM_PORT_PHY_CLEANUP(61446)
    RRtoken:0x0060B03E

387) Event:ESQ_RSP length:38, at 847918 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_RX] Src:MTS_SAP_L2FM(221), Opc:MTS_OPC_ETHPM_PORT_PHY_CLEANUP(61446)
    RRtoken:0x0060B03E

388) Event:ESQ_REQ length:38, at 850318 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_TX] Dst:MTS_SAP_ELTM(192), Opc:MTS_OPC_ETHPM_PORT_PHY_CLEANUP(61446)
    RRtoken:0x0060B041

389) Event:ESQ_RSP length:38, at 863373 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_RX] Src:MTS_SAP_ELTM(192), Opc:MTS_OPC_ETHPM_PORT_PHY_CLEANUP(61446)
    RRtoken:0x0060B041

390) Event:ESQ_REQ length:38, at 863461 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_TX] Dst:MTS_SAP_ASSOC_MGR(714), Opc:MTS_OPC_ETHPM_PORT_PHY_CLEANUP(61446)

391) FSM:<Ethernet1/51> Transition at 2024-11-25T17:32:06.863811000-06:00
    Previous state: [ETH_PORT_FSM_ST_WAIT_PHYSICAL_DOWN]
    Triggered event: [ETH_PORT_FSM_EV_PHY_DOWN_DONE]
    Next state: [ETH_PORT_FSM_ST_WAIT_APPLY_CONFIG]

392) Event:ESQ_START length:38, at 863859 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq Type:SERIAL

393) Event:ESQ_REQ length:38, at 863882 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq:Layer Change Cleanup

394) Event:ESQ_REQ length:38, at 863888 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_TX] Dst:MTS_SAP_RES_MGR(387), Opc:MTS_RES_MGR_OPC_FREE_RESOURCE_WITH_VALUE_FOR_VDC(19462)

395) Event:ESQ_REQ length:38, at 863889 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_TX] Dst:MTS_SAP_DIAGCLIENT(366), Opc:MTS_OPC_GOLD_PP_TEST_STOP(59414)

396) Event:ESQ_REQ length:38, at 863892 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_TX] Dst:MTS_SAP_PORT_CLIENT(181), Opc:MTS_OPC_LC_PORT_FCOT_SPROM_READ(8194)

397) Event:ESQ_REQ length:38, at 863897 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq:Update Linux netdevices

398) Event:ESQ_REQ length:38, at 863916 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_TX] Dst:MTS_SAP_PORT_CLIENT(181), Opc:MTS_OPC_ETHPM_LCP_SET_PORT_CFG(61443)
    RRtoken:0x0000EF25

399) Event:ESQ_REQ length:38, at 863921 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_TX] Dst:MTS_SAP_VLAN_MGR(167), Opc:MTS_OPC_VLAN_MGR_GET_PORT_TRUNKING_MEMBERSHIP(23562)

400) Event:ESQ_REQ length:38, at 863922 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_TX] Dst:MTS_SAP_DIAGCLIENT(366), Opc:MTS_OPC_GOLD_PP_TEST_RESUME(59417)

401) Event:ESQ_REQ length:38, at 863928 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_TX] Dst:MTS_SAP_VLAN_MGR(167), Opc:MTS_OPC_VLAN_MGR_GET_PORT_MEMBERSHIP(23560)

402) FSM:<Ethernet1/51> Transition at 2024-11-25T17:32:06.864064000-06:00
    Previous state: [ETH_PORT_FSM_ST_WAIT_APPLY_CONFIG]
    Triggered event: [ETH_PORT_FSM_EV_CFG_DONE]
    Next state: [ETH_PORT_FSM_ST_INIT_EVAL]

403) FSM:<Ethernet1/51> Transition at 2024-11-25T17:32:06.864486000-06:00
    Previous state: [ETH_PORT_FSM_ST_INIT_EVAL]
    Triggered event: [ETH_PORT_FSM_EV_IE_PORT_INIT]
    Next state: [ETH_PORT_FSM_ST_SPAN_EVAL]

404) FSM:<Ethernet1/51> Transition at 2024-11-25T17:32:06.864490000-06:00
    Previous state: [ETH_PORT_FSM_ST_SPAN_EVAL]
    Triggered event: [ETH_PORT_FSM_EV_NON_SPAN_DEST]
    Next state: [ETH_PORT_FSM_ST_WAIT_PRE_CFG]

405) Event:ESQ_START length:38, at 864536 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq Type:SERIAL

406) Event:ESQ_REQ length:38, at 867554 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq:determine steps to skip

407) Event:ESQ_REQ length:38, at 878812 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq:check for crd cfg

408) Event:ESQ_REQ length:38, at 878820 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq:check for issu credits

409) Event:ESQ_REQ length:38, at 879208 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq:Publish IFDB

410) Event:ESQ_REQ length:38, at 879674 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_TX] Dst:MTS_SAP_CTS(400), Opc:MTS_OPC_ETHPM_PORT_PRE_CFG(61441)
    RRtoken:0x0060B05D

411) Event:ESQ_RSP length:38, at 879847 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_RX] Src:MTS_SAP_CTS(400), Opc:MTS_OPC_ETHPM_PORT_PRE_CFG(61441)
    RRtoken:0x0060B05D

412) Event:ESQ_REQ length:38, at 879922 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_TX] Dst:MTS_SAP_ELTM(192), Opc:MTS_OPC_ETHPM_PORT_PRE_CFG(61441)
    RRtoken:0x0060B060

413) Event:ESQ_RSP length:38, at 935686 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_RX] Src:MTS_SAP_ELTM(192), Opc:MTS_OPC_ETHPM_PORT_PRE_CFG(61441)
    RRtoken:0x0060B060

414) Event:ESQ_REQ length:38, at 935695 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq:check if port is eventually going to be down

415) Event:ESQ_REQ length:38, at 935783 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq:Pacer Check

416) Event:ESQ_REQ length:38, at 936261 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_TX] Dst:MTS_SAP_PORT_CLIENT(181), Opc:MTS_OPC_ETHPM_LCP_SET_PORT_CFG(61443)
    RRtoken:0x0060B188

417) Event:ESQ_RSP length:38, at 943215 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_RX] Src:MTS_SAP_PORT_CLIENT(181), Opc:MTS_OPC_ETHPM_LCP_SET_PORT_CFG(61443)
    RRtoken:0x0060B188

418) FSM:<Ethernet1/51> Transition at 2024-11-25T17:32:06.943522000-06:00
    Previous state: [ETH_PORT_FSM_ST_WAIT_PRE_CFG]
    Triggered event: [ETH_PORT_FSM_EV_PRE_CFG_DONE]
    Next state: [ETH_PORT_FSM_ST_LINK_INIT]

419) FSM:<Ethernet1/51> Transition at 2024-11-25T17:32:06.946215000-06:00
    Previous state: [ETH_PORT_FSM_ST_LINK_INIT]
    Triggered event: [ETH_PORT_FSM_EV_SI_CONFIG_CMD]
    Next state: [FSM_ST_NO_CHANGE]

420) FSM:<Ethernet1/51> Transition at 2024-11-25T17:32:06.946258000-06:00
    Previous state: [ETH_PORT_FSM_ST_LINK_INIT]
    Triggered event: [ETH_PORT_FSM_EV_SI_DELETE_CMD]
    Next state: [FSM_ST_NO_CHANGE]

421) FSM:<Ethernet1/51> Transition at 2024-11-25T17:32:06.946271000-06:00
    Previous state: [ETH_PORT_FSM_ST_LINK_INIT]
    Triggered event: [ETH_PORT_FSM_EV_SI_BRINGDOWN]
    Next state: [FSM_ST_NO_CHANGE]

422) FSM:<Ethernet1/51> Transition at 2024-11-25T17:32:06.946286000-06:00
    Previous state: [ETH_PORT_FSM_ST_LINK_INIT]
    Triggered event: [ETH_PORT_FSM_EV_SI_BRINGDOWN_DONE]
    Next state: [FSM_ST_NO_CHANGE]

423) FSM:<Ethernet1/51> Transition at 2024-11-25T17:32:06.946302000-06:00
    Previous state: [ETH_PORT_FSM_ST_LINK_INIT]
    Triggered event: [ETH_PORT_FSM_EV_SI_REMOVE]
    Next state: [FSM_ST_NO_CHANGE]

424) Event:ESQ_START length:38, at 946323 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq Type:SERIAL

425) Event:ESQ_REQ length:38, at 949367 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq:determine steps to skip

426) Event:ESQ_REQ length:38, at 953347 usecs after Mon Nov 25 17:32:06 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_TX] Dst:MTS_SAP_REGISTRY(0), Opc:MTS_OPC_IM_IF_REMOVED(62468)
    RRtoken:0x0060B1A4

427) Event:ESQ_RSP length:38, at 202965 usecs after Mon Nov 25 17:32:07 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_RX] Src:MTS_SAP_REGISTRY(0), Opc:MTS_OPC_IM_IF_REMOVED(62468)
    RRtoken:0x0060B1A4

428) Event:ESQ_REQ length:38, at 203036 usecs after Mon Nov 25 17:32:07 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq:Cleanup Linux netdevices

429) Event:ESQ_REQ length:38, at 203174 usecs after Mon Nov 25 17:32:07 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq:SI_HAPSS_IFDB_DELETE

430) Event:ESQ_REQ length:38, at 207052 usecs after Mon Nov 25 17:32:07 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_TX] Dst:MTS_SAP_RES_MGR(387), Opc:MTS_RES_MGR_OPC_FREE_RESOURCE_WITH_VALUE_FOR_VDC(19462)

431) Event:ESQ_REQ length:38, at 207259 usecs after Mon Nov 25 17:32:07 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_TX] Dst:MTS_SAP_REGISTRY(0), Opc:MTS_OPC_ETHPM_NOP_IFDB_PUBLISH(61471)

432) Event:ESQ_REQ length:38, at 207498 usecs after Mon Nov 25 17:32:07 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_TX] Dst:MTS_SAP_REGISTRY(0), Opc:MTS_OPC_PSSHELPER_PUB_WRITE(28673)

433) Event:ESQ_RSP length:38, at 207655 usecs after Mon Nov 25 17:32:07 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_RX] Src:MTS_SAP_REGISTRY(0), Opc:MTS_OPC_PSSHELPER_PUB_WRITE(28673)

434) FSM:<Ethernet1/51> Transition at 2024-11-25T17:32:07.207733000-06:00
    Previous state: [ETH_PORT_FSM_ST_LINK_INIT]
    Triggered event: [ETH_PORT_FSM_EV_SI_REMOVE_DONE]
    Next state: [FSM_ST_NO_CHANGE]

435) FSM:<Ethernet1/51> Transition at 2024-11-25T17:32:07.207746000-06:00
    Previous state: [ETH_PORT_FSM_ST_LINK_INIT]
    Triggered event: [ETH_PORT_FSM_EV_SI_DELETE]
    Next state: [FSM_ST_NO_CHANGE]

436) Event:ESQ_START length:38, at 207765 usecs after Mon Nov 25 17:32:07 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq Type:SERIAL

437) Event:ESQ_REQ length:38, at 210646 usecs after Mon Nov 25 17:32:07 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq:determine steps to skip

438) Event:ESQ_REQ length:38, at 212006 usecs after Mon Nov 25 17:32:07 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_TX] Dst:MTS_SAP_REGISTRY(0), Opc:MTS_OPC_IM_IF_CONFIG_DELETED(62469)

439) Event:ESQ_RSP length:38, at 213804 usecs after Mon Nov 25 17:32:07 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_RX] Src:MTS_SAP_REGISTRY(0), Opc:MTS_OPC_IM_IF_CONFIG_DELETED(62469)

440) Event:ESQ_REQ length:38, at 213899 usecs after Mon Nov 25 17:32:07 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_TX] Dst:MTS_SAP_IFMGR(179), Opc:MTS_OPC_IM_IF_IOD_ASSIGN_RELEASE(62466)

441) Event:ESQ_RSP length:38, at 214841 usecs after Mon Nov 25 17:32:07 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_RX] Src:MTS_SAP_IFMGR(179), Opc:MTS_OPC_IM_IF_IOD_ASSIGN_RELEASE(62466)

442) Event:ESQ_REQ length:38, at 214945 usecs after Mon Nov 25 17:32:07 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq:SI_HAPSS_DELETE

443) Event:ESQ_REQ length:38, at 215197 usecs after Mon Nov 25 17:32:07 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_TX] Dst:MTS_SAP_PORT_CLIENT(181), Opc:MTS_OPC_LC_PORT_CLIENT_CONFIG(8186)

444) Event:ESQ_RSP length:38, at 216967 usecs after Mon Nov 25 17:32:07 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_RX] Src:MTS_SAP_PORT_CLIENT(181), Opc:MTS_OPC_LC_PORT_CLIENT_CONFIG(8186)

445) FSM:<Ethernet1/51> Transition at 2024-11-25T17:32:07.217073000-06:00
    Previous state: [ETH_PORT_FSM_ST_LINK_INIT]
    Triggered event: [ETH_PORT_FSM_EV_SI_DELETE_DONE]
    Next state: [FSM_ST_NO_CHANGE]

446) FSM:<Ethernet1/51> Transition at 2024-11-25T17:32:07.217510000-06:00
    Previous state: [ETH_PORT_FSM_ST_LINK_INIT]
    Triggered event: [ETH_PORT_FSM_EV_SI_REINIT_REQ]
    Next state: [FSM_ST_NO_CHANGE]
```
+ Admin up the other side (SPINE port)
```

447) FSM:<Ethernet1/51> Transition at 2024-11-25T17:32:07.937486000-06:00
    Previous state: [ETH_PORT_FSM_ST_LINK_INIT]
    Triggered event: [ETH_PORT_FSM_EV_PACER_TIMER_EXPIRED]
    Next state: [FSM_ST_NO_CHANGE]

448) FSM:<Ethernet1/51> Transition at 2024-11-25T17:34:12.566466000-06:00
    Previous state: [ETH_PORT_FSM_ST_LINK_INIT]
    Triggered event: [ETH_PORT_FSM_EV_LINK_UP]
    Next state: [ETH_PORT_FSM_ST_WAIT_BRINGUP]

449) Event:ESQ_START length:38, at 566623 usecs after Mon Nov 25 17:34:12 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq Type:SERIAL

450) Event:ESQ_REQ length:38, at 569164 usecs after Mon Nov 25 17:34:12 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq:determine steps to skip

451) Event:ESQ_REQ length:38, at 569169 usecs after Mon Nov 25 17:34:12 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq:check for issu

452) Event:ESQ_REQ length:38, at 569881 usecs after Mon Nov 25 17:34:12 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_TX] Dst:MTS_SAP_REGISTRY(0), Opc:MTS_OPC_IM_PHY_LINK_STATE_CHANGE(62470)

453) Event:ESQ_REQ length:38, at 569922 usecs after Mon Nov 25 17:34:12 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_TX] Dst:MTS_SAP_CTS(400), Opc:MTS_OPC_ETHPM_PORT_BRINGUP(61442)
    RRtoken:0x0060C047

454) Event:ESQ_RSP length:38, at 579357 usecs after Mon Nov 25 17:34:12 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_RX] Src:MTS_SAP_CTS(400), Opc:MTS_OPC_ETHPM_PORT_BRINGUP(61442)
    RRtoken:0x0060C047

455) Event:ESQ_REQ length:38, at 579425 usecs after Mon Nov 25 17:34:12 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_TX] Dst:MTS_SAP_FCOE(473), Opc:MTS_OPC_ETHPM_PORT_BRINGUP(61442)

456) Event:ESQ_REQ length:38, at 579534 usecs after Mon Nov 25 17:34:12 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_TX] Dst:MTS_SAP_ETH_PORT_CHANNEL_MGR(378), Opc:MTS_OPC_ETHPM_PORT_BRINGUP(61442)
    RRtoken:0x0060C058

457) Event:ESQ_RSP length:38, at 579684 usecs after Mon Nov 25 17:34:12 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_RX] Src:MTS_SAP_ETH_PORT_CHANNEL_MGR(378), Opc:MTS_OPC_ETHPM_PORT_BRINGUP(61442)
    RRtoken:0x0060C058

458) Event:ESQ_REQ length:38, at 579740 usecs after Mon Nov 25 17:34:12 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_TX] Dst:MTS_SAP_ASSOC_MGR(714), Opc:MTS_OPC_ETHPM_PORT_BRINGUP(61442)

459) FSM:<Ethernet1/51> Transition at 2024-11-25T17:34:12.579839000-06:00
    Previous state: [ETH_PORT_FSM_ST_WAIT_BRINGUP]
    Triggered event: [ETH_PORT_FSM_EV_BRINGUP_DONE]
    Next state: [ETH_PORT_FSM_ST_WAIT_PRE_LOGICAL_UP]

460) Event:ESQ_START length:38, at 579890 usecs after Mon Nov 25 17:34:12 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq Type:SERIAL

461) Event:ESQ_REQ length:38, at 583216 usecs after Mon Nov 25 17:34:12 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq:determine steps to skip

462) Event:ESQ_REQ length:38, at 583256 usecs after Mon Nov 25 17:34:12 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq:Sending state up notif to shared vdc

463) FSM:<Ethernet1/51> Transition at 2024-11-25T17:34:12.583370000-06:00
    Previous state: [ETH_PORT_FSM_ST_WAIT_PRE_LOGICAL_UP]
    Triggered event: [ETH_PORT_FSM_EV_PRE_LOGICAL_DONE]
    Next state: [ETH_PORT_FSM_ST_WAIT_LOGICAL_UP]

464) FSM:<Ethernet1/51> Transition at 2024-11-25T17:34:12.583378000-06:00
    Previous state: [ETH_PORT_FSM_ST_WAIT_LOGICAL_UP]
    Triggered event: [ETH_PORT_FSM_EV_L3_UP]
    Next state: [ETH_PORT_FSM_ST_L3_UP]

465) FSM:<Ethernet1/51> Transition at 2024-11-25T17:34:12.587206000-06:00
    Previous state: [ETH_PORT_FSM_ST_L3_UP]
    Triggered event: [ETH_PORT_FSM_EV_SI_DONE]
    Next state: [FSM_ST_NO_CHANGE]

466) FSM:<Ethernet1/51> Transition at 2024-11-25T17:34:13.115435000-06:00
    Previous state: [ETH_PORT_FSM_ST_L3_UP]
    Triggered event: [ETH_PORT_FSM_EV_SI_CONFIG_CMD]
    Next state: [FSM_ST_NO_CHANGE]

467) FSM:<Ethernet1/51> Transition at 2024-11-25T17:34:13.115637000-06:00
    Previous state: [ETH_PORT_FSM_ST_L3_UP]
    Triggered event: [ETH_PORT_FSM_EV_SI_CREATE_CMD]
    Next state: [FSM_ST_NO_CHANGE]

468) FSM:<Ethernet1/51> Transition at 2024-11-25T17:34:13.115648000-06:00
    Previous state: [ETH_PORT_FSM_ST_L3_UP]
    Triggered event: [ETH_PORT_FSM_EV_SI_CREATE]
    Next state: [FSM_ST_NO_CHANGE]

469) Event:ESQ_START length:38, at 115670 usecs after Mon Nov 25 17:34:13 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq Type:SERIAL

470) Event:ESQ_REQ length:38, at 118194 usecs after Mon Nov 25 17:34:13 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq:determine steps to skip

471) Event:ESQ_REQ length:38, at 118233 usecs after Mon Nov 25 17:34:13 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq:SI Creation Internal Init

472) Event:ESQ_REQ length:38, at 121796 usecs after Mon Nov 25 17:34:13 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_TX] Dst:MTS_SAP_RES_MGR(387), Opc:MTS_RES_MGR_OPC_ALLOC_RESOURCE_WITH_VALUE_FOR_VDC(19461)

473) Event:ESQ_REQ length:38, at 121890 usecs after Mon Nov 25 17:34:13 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_TX] Dst:MTS_SAP_IFMGR(179), Opc:MTS_OPC_IM_IF_IOD_ASSIGN_RELEASE(62466)

474) Event:ESQ_RSP length:38, at 123037 usecs after Mon Nov 25 17:34:13 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_RX] Src:MTS_SAP_IFMGR(179), Opc:MTS_OPC_IM_IF_IOD_ASSIGN_RELEASE(62466)

475) Event:ESQ_REQ length:38, at 123070 usecs after Mon Nov 25 17:34:13 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_TX] Dst:MTS_SAP_ELTM(192), Opc:MTS_OPC_ELTM_MTU(72715)

476) Event:ESQ_REQ length:38, at 123113 usecs after Mon Nov 25 17:34:13 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq:Create linux netdevices

477) Event:ESQ_REQ length:38, at 123641 usecs after Mon Nov 25 17:34:13 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq:SI_HAPSS_IFDB_UPDATE

478) Event:ESQ_REQ length:38, at 123800 usecs after Mon Nov 25 17:34:13 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq:SI_gldb_update

479) Event:ESQ_RSP length:38, at 123914 usecs after Mon Nov 25 17:34:13 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq:SI_gldb_update

480) Event:ESQ_REQ length:38, at 144115 usecs after Mon Nov 25 17:34:13 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_TX] Dst:MTS_SAP_REGISTRY(0), Opc:MTS_OPC_IM_IF_CREATED(62467)

481) Event:ESQ_REQ length:38, at 144272 usecs after Mon Nov 25 17:34:13 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_TX] Dst:MTS_SAP_PORT_CLIENT(181), Opc:MTS_OPC_LC_PORT_CLIENT_CONFIG(8186)

482) Event:ESQ_RSP length:38, at 145453 usecs after Mon Nov 25 17:34:13 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_RX] Src:MTS_SAP_PORT_CLIENT(181), Opc:MTS_OPC_LC_PORT_CLIENT_CONFIG(8186)

483) FSM:<Ethernet1/51> Transition at 2024-11-25T17:34:13.145553000-06:00
    Previous state: [ETH_PORT_FSM_ST_L3_UP]
    Triggered event: [ETH_PORT_FSM_EV_SI_CREATE_DONE]
    Next state: [FSM_ST_NO_CHANGE]

484) FSM:<Ethernet1/51> Transition at 2024-11-25T17:34:13.145570000-06:00
    Previous state: [ETH_PORT_FSM_ST_L3_UP]
    Triggered event: [ETH_PORT_FSM_EV_SI_BRINGUP]
    Next state: [FSM_ST_NO_CHANGE]

485) Event:ESQ_START length:38, at 145688 usecs after Mon Nov 25 17:34:13 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq Type:SERIAL

486) Event:ESQ_REQ length:38, at 148136 usecs after Mon Nov 25 17:34:13 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq:determine steps to skip

487) Event:ESQ_REQ length:38, at 148253 usecs after Mon Nov 25 17:34:13 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_TX] Dst:MTS_SAP_ELTM(192), Opc:MTS_OPC_ETHPM_SI_LOGICAL_BRINGUP(61462)

488) Event:ESQ_RSP length:38, at 161028 usecs after Mon Nov 25 17:34:13 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_RX] Src:MTS_SAP_ELTM(192), Opc:MTS_OPC_ETHPM_SI_LOGICAL_BRINGUP(61462)

489) Event:ESQ_REQ length:38, at 161096 usecs after Mon Nov 25 17:34:13 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq:Bringup Linux netdevices

490) Event:ESQ_REQ length:38, at 161968 usecs after Mon Nov 25 17:34:13 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_TX] Dst:MTS_SAP_REGISTRY(0), Opc:MTS_OPC_IM_L3_PROTOCOL_STATE_CHANGE(62472)

491) FSM:<Ethernet1/51> Transition at 2024-11-25T17:34:13.162065000-06:00
    Previous state: [ETH_PORT_FSM_ST_L3_UP]
    Triggered event: [ETH_PORT_FSM_EV_SI_BRINGUP_DONE]
    Next state: [FSM_ST_NO_CHANGE]

492) FSM:<Ethernet1/51> Transition at 2024-11-25T17:34:13.162313000-06:00
    Previous state: [ETH_PORT_FSM_ST_L3_UP]
    Triggered event: [ETH_PORT_FSM_EV_SI_REINIT_REQ]
    Next state: [FSM_ST_NO_CHANGE]

493) FSM:<Ethernet1/51> Transition at 2024-11-25T17:34:13.162337000-06:00
    Previous state: [ETH_PORT_FSM_ST_L3_UP]
    Triggered event: [ETH_PORT_FSM_EV_SI_REINIT_CMD]
    Next state: [FSM_ST_NO_CHANGE]

494) FSM:<Ethernet1/51> Transition at 2024-11-25T17:34:13.162348000-06:00
    Previous state: [ETH_PORT_FSM_ST_L3_UP]
    Triggered event: [ETH_PORT_FSM_EV_SI_BRINGDOWN]
    Next state: [FSM_ST_NO_CHANGE]

495) Event:ESQ_START length:38, at 162379 usecs after Mon Nov 25 17:34:13 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq Type:SERIAL

496) Event:ESQ_REQ length:38, at 171695 usecs after Mon Nov 25 17:34:13 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq:SI_BRINGDOWN_SEQ_EVAL

497) Event:ESQ_REQ length:38, at 171702 usecs after Mon Nov 25 17:34:13 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_TX] Dst:MTS_SAP_TEST_ETHPM(175), Opc:MTS_OPC_IM_L3_IF_GRACEFUL_DOWN(62520)

498) Event:ESQ_RSP length:38, at 371979 usecs after Mon Nov 25 17:34:13 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_RX] Src:MTS_SAP_TEST_ETHPM(175), Opc:MTS_OPC_IM_L3_IF_GRACEFUL_DOWN(62520)

499) Event:ESQ_REQ length:38, at 372057 usecs after Mon Nov 25 17:34:13 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq:Bringdown Linux netdevices

500) Event:ESQ_REQ length:38, at 374401 usecs after Mon Nov 25 17:34:13 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_TX] Dst:MTS_SAP_REGISTRY(0), Opc:MTS_OPC_IM_L3_PROTOCOL_STATE_CHANGE(62472)

501) Event:ESQ_REQ length:38, at 374464 usecs after Mon Nov 25 17:34:13 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_TX] Dst:MTS_SAP_OSPF(320), Opc:MTS_OPC_ETHPM_PORT_CLEANUP(61444)

502) Event:ESQ_REQ length:38, at 374609 usecs after Mon Nov 25 17:34:13 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_TX] Dst:MTS_SAP_ELTM(192), Opc:MTS_OPC_ETHPM_SI_LOGICAL_BRINGDOWN(61463)

503) Event:ESQ_RSP length:38, at 382569 usecs after Mon Nov 25 17:34:13 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_RX] Src:MTS_SAP_ELTM(192), Opc:MTS_OPC_ETHPM_SI_LOGICAL_BRINGDOWN(61463)

504) FSM:<Ethernet1/51> Transition at 2024-11-25T17:34:13.382667000-06:00
    Previous state: [ETH_PORT_FSM_ST_L3_UP]
    Triggered event: [ETH_PORT_FSM_EV_SI_BRINGDOWN_DONE]
    Next state: [FSM_ST_NO_CHANGE]

505) FSM:<Ethernet1/51> Transition at 2024-11-25T17:34:13.382686000-06:00
    Previous state: [ETH_PORT_FSM_ST_L3_UP]
    Triggered event: [ETH_PORT_FSM_EV_SI_BRINGUP]
    Next state: [FSM_ST_NO_CHANGE]

506) Event:ESQ_START length:38, at 382849 usecs after Mon Nov 25 17:34:13 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq Type:SERIAL

507) Event:ESQ_REQ length:38, at 385412 usecs after Mon Nov 25 17:34:13 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq:determine steps to skip

508) Event:ESQ_REQ length:38, at 385524 usecs after Mon Nov 25 17:34:13 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_TX] Dst:MTS_SAP_ELTM(192), Opc:MTS_OPC_ETHPM_SI_LOGICAL_BRINGUP(61462)

509) Event:ESQ_RSP length:38, at 397561 usecs after Mon Nov 25 17:34:13 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_RX] Src:MTS_SAP_ELTM(192), Opc:MTS_OPC_ETHPM_SI_LOGICAL_BRINGUP(61462)

510) Event:ESQ_REQ length:38, at 397616 usecs after Mon Nov 25 17:34:13 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    Seq:Bringup Linux netdevices

511) Event:ESQ_REQ length:38, at 400229 usecs after Mon Nov 25 17:34:13 2024
    Instance:0x1A032000, Seq Id:0x1, Ret:SUCCESS
    [E_MTS_TX] Dst:MTS_SAP_REGISTRY(0), Opc:MTS_OPC_IM_L3_PROTOCOL_STATE_CHANGE(62472)

512) FSM:<Ethernet1/51> Transition at 2024-11-25T17:34:13.400350000-06:00
    Previous state: [ETH_PORT_FSM_ST_L3_UP]
    Triggered event: [ETH_PORT_FSM_EV_SI_BRINGUP_DONE]
    Next state: [FSM_ST_NO_CHANGE]


    Curr state: [ETH_PORT_FSM_ST_L3_UP]

MXS2-LF104#
```
