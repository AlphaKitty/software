#**redis直接用yum安装!**


###1.安装redis

`yum install redis`

###2.修改配置文件

`vi /etc/redis.conf`

###3.启动redis

`systemctl start redis`

###4.设置开机启动

`systemctl enable redis`

###5.验证是否启动成功

`redis-cli -p 9527 ping`


修改密码:

vi /etc/redis.conf 
    # requirepass foobared 改成 requirepass [password]


开启远程连接:

vi /etc/redis.conf
    #bind 127.0.0.1 改成 0.0.0.0或特定ip
    重启
    
配置防火墙开放6379端口

firewall-cmd --permanent --zone=public --add-port=6379/tcp

firewall-cmd --reload
