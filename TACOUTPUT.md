# TACOUTPUT

```
apic1# trigger tacoutput
.
.
.
Enter selections: 1,2,3,4,5,6
.
.
.
Logs available for SCP or SFTP download from /data/techsupport/TacOutput-2021-11-17T08:18:06-to-2021-12-17T08:18:06.tgz
To download through your web browser go to https://<apic address>/files/1/techsupport/TacOutput-2021-11-17T08:18:06-to-2021-12-17T08:18:06.tgz
Note: in the URL previous 1 denotes the APIC ID 1, if script was run on APIC-n, then n must be specified in the URL (n = APIC-ID).

To remove files when done run
rm -rf /tmp/TacOutput2021-12-17T08-16-19
rm -f /data/techsupport/TacOutput-2021-11-17T08:18:06-to-2021-12-17T08:18:06.tgz
```
```
Decode tacoutputs
tar -xvzf <tacoutputs_name>

Search filters
xmls_parser -f aaaModLR-* -t Jun 24 | more  <<<<<<<<< Triple AAA
xmls_parser -f faultRecord-* -t Jun 24 | more <<<<<<<<< Fault events
xmls_parser -f eventRecord-* -t Jun 24 | more <<<<<<<< Events recoded
nxos-bl-decode -f binlog_uuid_472_epmc_vdc_1_sub_1_level_3 | grep " moved from" | sed "s/^.*IP\s*//p" | sort | uniq -c | sort -rn | more
  10.129.91.176
xmls_parser -f *.xml -g 1/31 | less -r
```
