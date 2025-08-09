# NDO API
## Get Auth Token using username/password

```
vmenchac@VMENCHAC-M-H2GJ NDO_curl_lab % cat user_auth.json 
{"userName":"admin","userPasswd":"ins4956!","domain":"DefaultAuth"}%   
```
```
curl -k https://10.31.125.162/login -d @user_auth.json   
```
```
vmenchac@VMENCHAC-M-H2GJ NDO_curl_lab % cat token.txt 
Authorization: Bearer <token>   
```

## Using the token GET the schema config

```
curl -k https://10.31.125.162/mso/api/v1/schemas/68967003f3e488ff838abed8 -H @token.txt   
```

## Edit the schema

+ Modify what you need, also change the deploy version +1 at the end.

```
curl -X PUT -k https://10.31.125.162/mso/api/v1/schemas/68967003f3e488ff838abed8 -H @token.txt -d @schema_mod.json 
```

## Files

```
vmenchac@VMENCHAC-M-H2GJ NDO_curl_lab % ls -l
total 64
-rw-r--r--@ 1 vmenchac  staff  23171 Aug  8 17:57 schema_mod.json
-rw-r--r--@ 1 vmenchac  staff   1053 Aug  8 17:51 token.txt
-rw-r--r--@ 1 vmenchac  staff     67 Aug  8 17:35 user_auth.json

```
