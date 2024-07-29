# FN72145: Nexus ACI 9000 Will Fail with SSD Read-Only Filesystem

https://www.cisco.com/c/en/us/support/docs/cloud-systems-management/application-policy-infrastructure-controller-apic/217677-addressing-aci-fn72145-nexus-aci-9000-w.html

https://bst.cloudapps.cisco.com/bugsearch/bug/CSCvx19640

```
SWITCH# tail -n 103  /mnt/pss/smartctl_full_dump.log | egrep "Device Model|Firmware Version|ATTRIBUTE_NAME|Power_On_Hours"
SWITCH# vsh -c "show logging onboard internal reset-reason"    <<< check this command didnt run on the lab!!!!!!
```
```
APIC# moquery -c eqptFlash -f 'eqpt.Flash.model*"Micron_M500IT"'   <<< check this command didnt run on the lab!!!!!!
```
