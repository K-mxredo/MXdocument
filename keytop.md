[PRODUCT] 

Keytop 路内停车收费系统 V2.7.1 

[TYPE] 

Sensitive Data Exposure

[DESCRIPTION] 

A Sensitive Data Exposure  vulnerability exists in the "路内停车收费系统  V2.7.1",.The system's API is vulnerable to unauthorized access, allowing unauthenticated users to exploit certain interfaces and retrieve  sensitive user data  posing a critical security risk.

[DETAILS] 

A Sensitive Data Exposure vulnerability has been identified in the  application. The vulnerability allows attackers to exploit certain  interfaces and retrieve sensitive user data such as names, usernames,  and passwords, posing a critical security risk.

1.The system's API is vulnerable to unauthorized access,use  "saas/commonApi/park/getParks" allows retrieval of all parking lot  information.

1.The system's API is vulnerable to unauthorized access,use  "saas/commonApi/park/getParks" allows retrieval of all parking lot  information. 

![图片](https://private-user-images.githubusercontent.com/202232050/420246450-63fe90a2-dd0c-462c-816b-91a9a30c3b29.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NDE2NTcxNTAsIm5iZiI6MTc0MTY1Njg1MCwicGF0aCI6Ii8yMDIyMzIwNTAvNDIwMjQ2NDUwLTYzZmU5MGEyLWRkMGMtNDYyYy04MTZiLTkxYTlhMzBjM2IyOS5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjUwMzExJTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI1MDMxMVQwMTM0MTBaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT0zZjMzMzU3NjhhNmNkZGNlNjNjYWRlMTliMGY1ZmNmYzJjODkxMzJmMWQ3YTY5ZmIwMTIwMDJkNjY0NmZjYjBkJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.d0P9QbDQXJJWA8ppEHKS28VjcXPRPeJv5pT4QFb5FGg)

2.By utilizing parameter "parkCode" obtained from API  "saas/commonApi/park/getParks" , using API "saas/user/searchUser" one  can query detailed personnel data within the targeted parking lot,  including user names, account credentials, and passwords. 

![图片](https://private-user-images.githubusercontent.com/202232050/420247927-3e86bbb7-e806-4cd5-9327-30e9ffb1e574.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NDE2NTcxNTAsIm5iZiI6MTc0MTY1Njg1MCwicGF0aCI6Ii8yMDIyMzIwNTAvNDIwMjQ3OTI3LTNlODZiYmI3LWU4MDYtNGNkNS05MzI3LTMwZTlmZmIxZTU3NC5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjUwMzExJTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI1MDMxMVQwMTM0MTBaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT0wMzAxMTRiMjFmOGFhNGY4ZTVhYmUyZDU2OGRlYjkwOWMyMzBjYzJiZjkxOGI0YTMzOTFkYjMwYjdmODE3MjIxJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.RFW1gt_6nu0Yz0cMv43PgZJ0xqWd0EuujrYQZfEuN38)

[Mitigation & Fix Recommendations] 

Unauthorized access is prohibited. Implement server-side authorization checks to enforce access control.