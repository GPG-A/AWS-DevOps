1. 创建容器名[db2]数据库名[srcb_db2],密码[1q2w3e]，映射端口[50000]，映射宿主机目录：[/home/db2001/databases]
```bash
docker run -d -p 50000:50000 --name db2 --privileged=true -e DB2INST1_PASSWORD=1q2w3e -e DBNAME=srcb_db2 -e LICENSE=accept -v /home/db2001/databases:/database ibmcom/db2
```
2. 进入容器
```
docker exec -it db2 bash
```
3. 查看数据库状态
```bash
su - db2inst1 #切换实例用户
db2pd - #查看运行状态
db2level #查看数据库和补丁版本
db2 list db directory #查看已经创建的数据库
df -h #查看文件目录映射
```
4. 创建用户ods
```bash
exit  #退出db2inst1
useradd -g users -d /home/ods -s /bin/bash -m ods
passwd ods
```
5. 创建数据库mydb
```bash
db2 create db mydb using codeset utf-8 territory CN
db2 grant dbadm on database to user ods #数据库授权给用户
db2 list db directory #查看当前数据库
```

#### 参考链接
[Docker安装DB2](https://www.hangge.com/blog/cache/detail_2831.html)