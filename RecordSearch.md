#### **Company：**Shenzhen DAS INTELLITECH Co., Ltd.

#### official website:https://www.csdas.cn/

#### product:https://pms.demo.dasiot.cn/#/login

#### Affected version: 6.2.0

#### **Vulnerability Type**: **Sql injection (CWE-74 / CWE-89)**

#### **Attack Vector**: Network (Remote)

####  **漏洞描述 (Description)：**

> A SQL injection vulnerability exists in the "Parking Management System". The system's API endpoint "ParkingRecord/Search" is vulnerable to **unauthorized access**, allowing **unauthenticated users** to exploit certain interfaces and retrieve sensitive user data. In severe cases, attackers can execute commands to gain server privileges, posing a critical security risk. The manipulation of the parameter "value" leads to SQL injection.

#### **Impact Score (CVSS v3.1):**

- **Attack Vector (AV):** Network
- **Attack Complexity (AC):** Low 
- **Privileges Required (PR):** None
- **User Interaction (UI):** None 
- **Scope (S):** **Changed** 
- **Confidentiality (C):** High
- **Integrity (I):** High 
- **Availability (A):** High 

#### **[DETAILS]** 

<img width="2663" height="1437" alt="image-20260413165540031" src="https://github.com/user-attachments/assets/89c0f318-d45b-4af2-8e36-6da89a179992" />

The specific request packet is as follows, **no authentication required**:

```
POST /ParkingRecord/Search HTTP/1.1
Host: 59.47.27.22:8011
Content-Length: 83
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/141.0.0.0 Safari/537.36
Accept: application/json, text/plain, */*
Content-Type: application/json
Origin: http://59.47.27.22:8011
Referer: http://59.47.27.22:8011/
Accept-Encoding: gzip, deflate, br
Accept-Language: zh-CN,zh;q=0.9
Connection: keep-alive

{"pageIndex":1,"pageSize":15,"Filters":[{"Field":"OwnerName","Op":"=","Value":""}]}
```

The parameter 'Value' in the request body is vulnerable to SQL injection,Get the current database name:

<img width="2085" height="1051" alt="image-20260413165637303" src="https://github.com/user-attachments/assets/757ea12b-48ca-4730-8621-01522e0597f4" />


**Execute command**

<img width="2077" height="723" alt="image-20260413165701422" src="https://github.com/user-attachments/assets/fc783727-5c2e-4507-8a50-7bf2d8361de3" />


#### **[Mitigation & Fix Recommendations]** 

Implement parameterized queries (precompiled), use stored procedures if securely coded, and apply input validation/filtering.

