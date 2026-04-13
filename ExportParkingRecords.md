#### **Company：**Shenzhen DAS INTELLITECH Co., Ltd.

#### official website:https://www.csdas.cn/

#### product:https://pms.demo.dasiot.cn/#/login

#### Affected version: 6.2.0

#### **Vulnerability Type**: **Sql injection (CWE-74 / CWE-89)**

#### **Attack Vector**: Network (Remote)

####  **漏洞描述 (Description)：**

> A SQL injection vulnerability exists in the "Parking Management System". The system's API endpoint "ParkingRecord/ExportParkingRecords" is vulnerable to **unauthorized access**, allowing **unauthenticated users** to exploit certain interfaces and retrieve sensitive user data. In severe cases, attackers can execute commands to gain server privileges, posing a critical security risk. The manipulation of the parameter "value" leads to SQL injection.

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
<img width="3001" height="1567" alt="image-20260413163830886" src="https://github.com/user-attachments/assets/62942680-71b4-40d2-b4ef-b9e1d9a637b3" />



The specific request packet is as follows, **no authentication required**:

```

POST /ParkingRecord/ExportParkingRecords HTTP/1.1
Host: 117.157.67.208:8015
Content-Length: 87
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/141.0.0.0 Safari/537.36
Accept: application/json, text/plain, */*
Content-Type: application/json
Origin: http://117.157.67.208:8015
Referer: http://117.157.67.208:8015/
Accept-Encoding: gzip, deflate, br
Accept-Language: zh-CN,zh;q=0.9
Connection: keep-alive

{"pageIndex":1,"pageSize":50,"Filters":[{"Field":"OwnerName","Op":"=","Value":""}]}
```

The parameter 'Value' in the request body is vulnerable to SQL injection,Get the current database name:
<img width="2407" height="889" alt="image-20260413164311034" src="https://github.com/user-attachments/assets/6063795f-a484-4312-8f05-0e752ea6ce06" />

**Execute command**
<img width="2401" height="613" alt="image-20260413164446950" src="https://github.com/user-attachments/assets/6055f9bb-8539-42c9-8e4e-172a6823d9a2" />


#### **[Mitigation & Fix Recommendations]** 

Implement parameterized queries (precompiled), use stored procedures if securely coded, and apply input validation/filtering.

