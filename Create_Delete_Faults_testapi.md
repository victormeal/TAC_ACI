# Manually Generate Fault using testapi

https://techzone.cisco.com/t5/Application-Centric/Manually-Generate-Fault-using-testapi/ta-p/930640


```
MXS2-AP001# acidiag dbgtoken
0JVCRHZZIERP

MXS2-AP001# 
```
http://git.insieme.local/cgi-bin/generateRootPassword.py

```
MEUCIFMmxNfWZegAhxOYEm35LJbm/UMvTPtQjAEcIhg7CPjTAiEAtniCVsSK7yB9LFADjahxo2kOi4L5FOPmJv8Bd5b/BXQ=
```
```
MXS2-AP001# ssh root@localhost
Warning: Permanently added 'localhost' (RSA) to the list of known hosts.
Application Policy Infrastructure Controller
root@localhost's password: 
root@MXS2-AP001:~# 
```
```
root@MXS2-AP001:~# enable_testapi.bin 3600
Decoded seconds argument 3600 to be 3600
PAM_SERVER UDS SOCKET PATH = /var/run/mgmt/socket/pam
Connection successful - attempting to send testapi enable directive
Sent testapi enable directive (total pkt len 8)
Received response from testapi server
testapi enable directive acknowledged by REST endpoint
Success : testapi functionality is now enabled for 3600 seconds
root@MXS2-AP001:~# exit
logout
Connection to localhost closed.
MXS2-AP001# 
```

Will create a similar Fault to this one...

```
apl-apic-1# moquery -c faultInst -f 'fault.Inst.code=="F1651"'
Total Objects shown: 3

# fault.Inst
code             : F1651
ack              : no
alert            : no
annotation       : 
cause            : export-data-failed
changeSet        : 
childAction      : 
created          : 2024-02-04T16:05:14.906-04:00
delegated        : no
descr            : Upload triggered at 2019-03-14T14:25:49.103-05:00 for policy tsod-Log_Insight_Issue_Node-1110-1111 failed . Check operational status for details.
dn               : expcont/expstatus-tsod-MY_TEST/fault-F1651
domain           : infra
extMngdBy        : undefined
highestSeverity  : minor
lastTransition   : 2024-02-04T16:07:19.188-04:00
lc               : raised
modTs            : never
occur            : 1
origSeverity     : minor
prevSeverity     : minor
rn               : fault-F1651
rule             : dbgexp-policy-status-export-data
severity         : minor
status           : 
subject          : management
title            : 
type             : operational
uid              : 
userdom          : all
```
```
MXS2-AP001# icurl -g -X POST 'http://localhost:7777/testapi/mo/expcont/expstatus-tsod-MY_TEST/fault-F1651.xml' -d '<faultInst code="F1651" severity="minor" status="created"/>'
<?xml version="1.0" encoding="UTF-8"?><imdata totalCount="1"><faultInst ack="no" alert="no" annotation="" cause="unknown" changeSet="" childAction="" code="F1651" created="1970-01-01T00:00:00.000+00:00" delegated="no" descr="" dn="expcont/expstatus-tsod-MY_TEST/fault-F1651" domain="infra" extMngdBy="" highestSeverity="info" lastTransition="1970-01-01T00:00:00.000+00:00" lc="" modTs="never" occur="0" origSeverity="info" prevSeverity="info" rn="" rule="generic" severity="minor" status="" subject="" title="" type="config" uid="0" userdom=""/></imdata>
MXS2-AP001# 
```
The Fault should be created, check with moquery.

```
MXS2-AP001# moquery -c faultInst -f 'fault.Inst.code=="F1651"'                                                                                                                 
Total Objects shown: 3

# fault.Inst
code             : F1651
ack              : no
alert            : no
annotation       : 
cause            : unknown
changeSet        : 
childAction      : 
created          : 2024-08-21T22:52:46.063+00:00
delegated        : no
descr            : 
dn               : expcont/expstatus-tsod-MY_TEST/fault-F1651
domain           : infra
extMngdBy        : undefined
highestSeverity  : minor
lastTransition   : 2024-08-21T22:52:46.063+00:00
lc               : raised
modTs            : never
occur            : 1
origSeverity     : minor
prevSeverity     : minor
rn               : fault-F1651
rule             : dbgexp-policy-status-export-data
severity         : minor
status           : 
subject          : 
title            : 
type             : config
uid              : 
userdom          : all
```


# Manually delete a Fault using testapi

https://techzone.cisco.com/t5/Application-Centric/Using-icurl-to-TestAPI-Delete-an-Object-in-ACI/ta-p/1250057

Same steps as create one, but change the status tu deleted...
```
1. APIC# acidiag dbgtoken
2. Password on http://git.insieme.local/cgi-bin/generateRootPassword.py
3. APIC# ssh root@localhost
4. APIC# enable_testapi.bin 3600
5. exit
7. APIC# moquery -c faultInst -f 'fault.Inst.code=="F1651"'
6. APIC# icurl -g -X POST 'http://localhost:7777/testapi/mo/expcont/expstatus-tsod-MY_TEST/fault-F1651.xml' -d '<faultInst code="F1651" severity="minor" status="deleted"/>'

from above change "expcont/expstatus-tsod-MY_TEST/fault-F1651" with the correct dn obtained on step 7.
```

```
MXS2-AP001# icurl -g -X POST 'http://localhost:7777/testapi/mo/expcont/expstatus-tsod-MY_TEST/fault-F1651.xml' -d '<faultInst code="F1651" severity="minor" status="deleted"/>'
<?xml version="1.0" encoding="UTF-8"?><imdata totalCount="1"><faultInst ack="no" alert="no" annotation="" cause="unknown" changeSet="" childAction="" code="F1651" created="1970-01-01T00:00:00.000+00:00" delegated="no" descr="" dn="expcont/expstatus-tsod-MY_TEST/fault-F1651" domain="infra" extMngdBy="" highestSeverity="info" lastTransition="1970-01-01T00:00:00.000+00:00" lc="" modTs="never" occur="0" origSeverity="info" prevSeverity="info" rn="" rule="generic" severity="minor" status="deleted" subject="" title="" type="config" uid="0" userdom=""/></imdata>
MXS2-AP001# 
```


