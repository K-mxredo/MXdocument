[PRODUCT] 

 Vendor website:
http://www.brilliance.com.cn/
 
 黄金通二级系统三代管理端

fofa ：title="黄金通二级系统三代管理端"

官网： https://113.105.126.146:8900/ 

测试账号：admin/123456
![图片](https://github.com/user-attachments/assets/c938a171-699c-458e-8102-a6acfbf815f4)


[TYPE] 

SQL INJECTION

[DESCRIPTION] 

A SQL INJECTION  vulnerability exists in the " 黄金通二级系统三代管理端 ".The system's API ’sysframework/logSelect.htm ‘ exits a SQL injection. The manipulation of  the argument 'nodename' leads to sql injection.

[DETAILS] 

Request package is as follows

```
POST /sysframework/logSelect.htm HTTP/1.1
Host: 113.105.126.146:8900
Cookie: JSESSIONID_null_8900=108wmhre5vzd01q8gdx95qedhb
Content-Length: 94
Sec-Ch-Ua-Platform: "Windows"
X-Requested-With: XMLHttpRequest
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/135.0.0.0 Safari/537.36
Accept: */*
Sec-Ch-Ua: "Google Chrome";v="135", "Not-A.Brand";v="8", "Chromium";v="135"
Content-Type: application/x-www-form-urlencoded;utf-8
Sec-Ch-Ua-Mobile: ?0
Origin: https://113.105.126.146:8900
Sec-Fetch-Site: same-origin
Sec-Fetch-Mode: cors
Sec-Fetch-Dest: empty
Referer: https://113.105.126.146:8900/sysframework/operLog.htm
Accept-Encoding: gzip, deflate, br
Accept-Language: zh-CN,zh;q=0.9
Priority: u=1, i
Connection: keep-alive

page=1&branchtype=01&dateStart=2025-05-01&dateEnd=2025-06-03&nodename=&operuserCode=&cont=
```

The parameter nodename in the request body is vulnerable to SQL injection.

![image-20250601183733652](https://github.com/user-attachments/assets/dd819277-9332-4b76-a7e8-2e30eae92094)


[Mitigation & Fix Recommendations] 
Implement parameterized queries (precompiled), use stored procedures if securely coded, and apply input validation/filtering.

