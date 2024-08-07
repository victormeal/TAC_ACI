# Port Counters Fabrci-Wide

## CRC/FCS ERRORS

```
MXS2-AP001# moquery -c rmonDot3Stats -f 'rmon.Dot3Stats.fCSErrors>="1"' | egrep "dn|fCSErrors"
dn                         : topology/pod-1/node-1002/sys/phys-[eth1/2]/dbgDot3Stats
fCSErrors                  : 1
MXS2-AP001#
```

## CRC Stomp + FCS Errors

```
MXS2-AP001# moquery -c rmonEtherStats -f 'rmon.EtherStats.cRCAlignErrors>="1"' | egrep "dn|cRCAlignErrors" 
cRCAlignErrors       : 1
dn                   : topology/pod-1/node-1002/sys/phys-[eth1/2]/dbgEtherStats
MXS2-AP001# 
```

## SWITCH Interface Outputs

```
MXS2-AP001# fabric 1002 show int e1/2
----------------------------------------------------------------
 Node 1002 (MXS2-SP1002)
----------------------------------------------------------------
Ethernet1/2 is up
admin state is up, Dedicated Interface
  Hardware: 1000/10000/100000/40000 Ethernet, address: 0000.0000.0000 (bia 5ca6.2d58.3e76)
  MTU 9366 bytes, BW 40000000 Kbit, DLY 1 usec
  reliability 255/255, txload 1/255, rxload 1/255
  Encapsulation ARPA, medium is broadcast
  Port mode is routed
  full-duplex, 40 Gb/s, media type is 40G
  FEC (forward-error-correction) : disable-fec
  Beacon is turned off
  Auto-Negotiation is turned on
  Input flow-control is off, output flow-control is off
  Auto-mdix is turned off
  Rate mode is dedicated
  Switchport monitor is off
  EtherType is 0x8100
  EEE (efficient-ethernet) : n/a
  Last link flapped 13:14:32
  Last clearing of "show interface" counters never
  1 interface resets
  30 seconds input rate 25112 bits/sec, 17 packets/sec
  30 seconds output rate 805064 bits/sec, 112 packets/sec
  Load-Interval #2: 5 minute (300 seconds)
    input rate 17632 bps, 12 pps; output rate 877064 bps, 125 pps
  L3 in Switched:
    ucast: 0 pkts, 0 bytes - mcast: 0 pkts, 0 bytes
  L3 out Switched:
    ucast: 0 pkts, 0 bytes - mcast: 0 pkts, 0 bytes
  RX
    4972198 unicast packets  58003 multicast packets  22 broadcast packets
    5030224 input packets  862187991 bytes
    112058 jumbo packets  0 storm suppression bytes
    0 runts  0 giants  1 CRC  0 Stomped CRC  0 no buffer
    1 input error  0 short frame  0 overrun   0 underrun  0 ignored
    0 watchdog  0 bad etype drop  0 bad proto drop  0 if down drop
    0 input with dribble  0 input discard
    0 input buffer drop  0 input total drop
    0 Rx pause
  TX
    7447900 unicast packets  153042 multicast packets  22 broadcast packets
    7600964 output packets  5392776815 bytes
    3072470 jumbo packets
    0 output error  0 collision  0 deferred  0 late collision
    0 lost carrier  0 no carrier  0 babble  0 output discard
    0 output buffer drops  0 output total drops
    0 Tx pause


MXS2-AP001#  
```
```
MXS2-SP1002# show int e1/2 counters errors 

-------------------------------------------------------------------------------------------------
Port          Align-Err    CRC-Err   Stomp-CRC-Err   Xmit-Err    Rcv-Err  UnderSize   OutDiscards
-------------------------------------------------------------------------------------------------
Eth1/2               --          1              --         --         --         --          --

--------------------------------------------------------------------------------
Port         Single-Col  Multi-Col   Late-Col  Exces-Col  Carri-Sen       Runts
--------------------------------------------------------------------------------
Eth1/2               --         --         --         --         --          --

--------------------------------------------------------------------------------
Port          Giants SQETest-Err Deferred-Tx IntMacTx-Er IntMacRx-Er Symbol-Err
--------------------------------------------------------------------------------
Eth1/2            --          --          --          --          --         --
MXS2-SP1002#
```

## Output Buffer Drops

```
MXS2-AP001# moquery -c rmonEgrCounters -f 'rmon.EgrCounters.bufferdroppkts>="1"' | egrep "dn|bufferdroppkts"
bufferdroppkts : 2
dn             : topology/pod-1/node-101/sys/phys-[eth1/49]/dbgEgrCounters
bufferdroppkts : 2
dn             : topology/pod-1/node-101/sys/phys-[eth1/50]/dbgEgrCounters
bufferdroppkts : 4
dn             : topology/pod-1/node-101/sys/phys-[eth1/52]/dbgEgrCounters
bufferdroppkts : 10
dn             : topology/pod-1/node-101/sys/phys-[eth1/53]/dbgEgrCounters
bufferdroppkts : 1
dn             : topology/pod-1/node-101/sys/phys-[eth1/54]/dbgEgrCounters
bufferdroppkts : 5
dn             : topology/pod-1/node-102/sys/phys-[eth1/49]/dbgEgrCounters
bufferdroppkts : 2
dn             : topology/pod-1/node-102/sys/phys-[eth1/52]/dbgEgrCounters
bufferdroppkts : 2
dn             : topology/pod-1/node-102/sys/phys-[eth1/53]/dbgEgrCounters
MXS2-AP001#
```
```
MXS2-AP001# fabric 101 show int e1/53
----------------------------------------------------------------
 Node 101 (MXS2-LF101)
----------------------------------------------------------------
Ethernet1/53 is up
admin state is up, Dedicated Interface
  Hardware: 1000/10000/100000/40000 Ethernet, address: 0000.0000.0000 (bia 286f.7feb.0345)
  MTU 9366 bytes, BW 40000000 Kbit, DLY 1 usec
  reliability 255/255, txload 1/255, rxload 1/255
  Encapsulation ARPA, medium is broadcast
  Port mode is routed
  full-duplex, 40 Gb/s, media type is 40G
  FEC (forward-error-correction) : disable-fec
  Beacon is turned off
  Auto-Negotiation is turned on
  Input flow-control is off, output flow-control is off
  Auto-mdix is turned off
  Rate mode is dedicated
  Switchport monitor is off
  EtherType is 0x8100
  EEE (efficient-ethernet) : n/a
  Last link flapped 13:17:26
  Last clearing of "show interface" counters never
  1 interface resets
  30 seconds input rate 818992 bits/sec, 124 packets/sec
  30 seconds output rate 24880 bits/sec, 20 packets/sec
  Load-Interval #2: 5 minute (300 seconds)
    input rate 809968 bps, 118 pps; output rate 509192 bps, 66 pps
  L3 in Switched:
    ucast: 0 pkts, 0 bytes - mcast: 0 pkts, 0 bytes
  L3 out Switched:
    ucast: 0 pkts, 0 bytes - mcast: 0 pkts, 0 bytes
  RX
    8730834 unicast packets  11249 multicast packets  9 broadcast packets
    8742092 input packets  6796509900 bytes
    3964973 jumbo packets  0 storm suppression bytes
    0 runts  0 giants  0 CRC  0 Stomped CRC  0 no buffer
    0 input error  0 short frame  0 overrun   0 underrun  0 ignored
    0 watchdog  0 bad etype drop  0 bad proto drop  0 if down drop
    0 input with dribble  0 input discard
    0 input buffer drop  0 input total drop
    0 Rx pause
  TX
    3533718 unicast packets  451314 multicast packets  17 broadcast packets
    3985049 output packets  2785632239 bytes
    1579706 jumbo packets
    0 output error  0 collision  0 deferred  0 late collision
    0 lost carrier  0 no carrier  0 babble  0 output discard
    10 output buffer drops  10 output total drops
    0 Tx pause


MXS2-AP001# 
```

## Output Errors

```
MXS2-AP001# moquery -c rmonIfOut -f 'rmon.IfOut.errors>="1"' | egrep "dn|errors"
MXS2-AP001# moquery -c rmonIfOut -f 'rmon.IfOut.errors>="1"'                    
No Mos found
MXS2-AP001# 
```
