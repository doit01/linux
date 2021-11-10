df /var/lib/ -kh  查看挂载
netstat -aon|findstr "80"
docker-compose -f src/main/docker/redis.yml up -d

docker run -d --name myRedis -p 6379:6379 redis 
docker run -d --name redis6 -p 6379:6379 10.31.94.21:5000/redis  -v $PWD/data:/data --appendonly yes

https://www.kancloud.cn/wenshunbiao/wenshunbiao/1609076
在 home 目录查找名字叫 php.ini 的文件

find /home -type f -name php.ini

在 home 目录查找名字叫 data 的文件夹（-iname 不区分大小写）

find /home -type d -iname data

在 home 目录查找所有PHP文件

find /home -type f -name "*.php"

grep root /etc/passwd
或
cat /etc/passwd | grep root

在当前目录及其子目录下搜索

grep -r 'find str' ./*

使用正则搜索并显示匹配的行号

grep -n 't[ae]st' regular_express.txt


