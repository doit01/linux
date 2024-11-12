systemd对应的进程管理命令就是systemctl
Linux 服务管理有两种方式service和systemctl。而systemd是Linux系统最新的初始化系统(init)，作用是提高系统的启动速度
 查看系统服务
1）命令

systemctl -t service #查看活动的系统服务

systemctl -t service --all #列出所有系统服务(包括不活跃的)
    Loaded行：配置文件的位置，是否设为开机启动

    Active行：表示正在运行

    Main PID行：主进程ID

    Status行：由应用本身提供的软件当前状态

    CGroup块：应用的所有子进程

    日志块：应用的日志

[root@wangwu ~]# systemctl stop httpd

    1

[root@wangwu ~]# systemctl status httpd




 让ssh客户端不断
 root@10.28.140.46:~# sed -i "s/#ClientAliveInterval 0/ClientAliveInterval 60/g" /etc/ssh/sshd_config
root@10.28.140.46:~# sed -i "s/#ClientAliveCountMax 3/ClientAliveCountMax 5/g" sshd_config
sed: can't read sshd_config: No such file or directory
root@10.28.140.46:~# sed -i "s/#ClientAliveCountMax 3/ClientAliveCountMax 5/g" /etc/ssh/sshd_config
root@10.28.140.46:~# service sshd restart
Restarting sshd (via systemctl):  Warning: sshd.service changed on disk. Run 'systemctl daemon-reload' to reload units.
                                                           [  OK  ]
root@10.28.140.46:~# systemctl daemon-reload


 清理系统垃圾文件
 ls -lh 查看当前目录文件大小
 du -sh 看当前总的大小
/var/log
df -h
du -h –max-depth=1 * 看每个文件大小
对于10机器
/var/lib/docker/overlay2存的是镜像
 
unmount mount
https://blog.csdn.net/weixin_34234823/article/details/89941421
df /usr/local -kh
df /var/lib/ -kh  查看挂载
df /var/lib/docker -kh
for harbor
 mount /dev/mapper/centos-home /data
 
mount /dev/mapper/centos-home /var/lib/docker

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


