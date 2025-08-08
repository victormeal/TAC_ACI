# API Access logs

```
MXS2-AP001# pwd
/var/log/dme/log
MXS2-AP001# cat access.log | egrep 10.188.105.126
127.0.0.1 (::ffff:10.188.105.126) - - [08/Aug/2025:17:17:03 +0000]"GET /api/aaaRefresh.json?_dc=1754673421278 HTTP/1.1" 403 119 "https://10.31.125.151/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:141.0) Gecko/20100101 Firefox/141.0"
127.0.0.1 (::ffff:10.188.105.126) - - [08/Aug/2025:17:17:13 +0000]"GET /api/node/mo/info.json?_dc=1754673431326 HTTP/1.1" 403 119 "https://10.31.125.151/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:141.0) Gecko/20100101 Firefox/141.0"
127.0.0.1 (::ffff:10.188.105.126) - - [08/Aug/2025:17:17:15 +0000]"POST /uitelemetry/clicks HTTP/1.1" 200 0 "https://10.31.125.151/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:141.0) Gecko/20100101 Firefox/141.0"
127.0.0.1 (::ffff:10.188.105.126) - - [08/Aug/2025:17:18:14 +0000]"GET /api/node/mo/info.json?_dc=1754673491963 HTTP/1.1" 403 119 "https://10.31.125.151/" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:141.0) Gecko/20100101 Firefox/141.0"
```
