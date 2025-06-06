[PRODUCT] 

 停车场管理系统   6.2.0

![image-20250601191639502](C:\Users\16523\AppData\Roaming\Typora\typora-user-images\image-20250601191639502.png)



官网demo站：https://pms.demo.dasiot.cn/#/login

[TYPE] 

SQL INJECTION

[DESCRIPTION] 

A SQL INJECTION  vulnerability exists in the " 停车场管理系统 ".The system's API 'vehicle/search ' is vulnerable to unauthorized access ,allowing unauthenticated users to exploit certain interfaces and retrieve  sensitive user data  posing a critical security risk. The manipulation of  the argument 'vehicleTypeCode' leads to sql injection.

[DETAILS] 

Request package is as follows  

```
POST /vehicle/search HTTP/1.1
Host: 59.47.27.22:8011
Content-Length: 391
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/133.0.0.0 Safari/537.36
Accept: application/json, text/plain, */*
Content-Type: application/json
Origin: http://59.47.27.22:8011
Referer: http://59.47.27.22:8011/
Accept-Encoding: gzip, deflate, br
Accept-Language: zh-CN,zh;q=0.9
Connection: keep-alive

{"pagingModel":{"pageSize":15,"pageIndex":1},"sortModel":{"field":"","orderType":1},"filterModel":{"ownerName":"","companyName":"","startDate":"","endDate":"","vehicleTypeCode":"","vehicleState":"[0,1,3,4,5]","expiryStatus":"[0,1]","groupID":"","vehicleIdentificationNumber":"","ownerPhone":""}}
```

The parameter 'vehicleTypeCode ' in the request body is vulnerable to SQL injection.

![image-20250601193216346](C:\Users\16523\AppData\Roaming\Typora\typora-user-images\image-20250601193216346.png)

[Mitigation & Fix Recommendations] 
Implement parameterized queries (precompiled), use stored procedures if securely coded, and apply input validation/filtering.

