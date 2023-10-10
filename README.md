#  常用命令行

### Docker

```shell
# 创建 mysql5.7.x
docker run -d -p 3306:3306 -e MYSQL_ROOT_PASSWORD=chengxun --name mysql --restart always mysql:5.7 --lower_case_table_names=1 --character-set-server=utf8mb4 --collation-server=utf8mb4_general_ci --explicit_defaults_for_timestamp=true --max_allowed_packet=128M

# 创建 mysql8
docker run -d -p 3306:3306 -e MYSQL_ROOT_PASSWORD=chengxun --name mysql --restart always mysql:8 --lower_case_table_names=1 --default_authentication_plugin=mysql_native_password

# 创建 redis
docker run -d -p 6379:6379 --name redis --restart always redis:6 --requirepass redis@123

# 创建 nginx
docker run -d -p 9001:80 --name cube-demo -v /root/xinwuy/demo/dist:/usr/share/nginx/html -v /root/xinwuy/demo/default.conf:/etc/nginx/conf.d/default.conf --restart=always nginx:stable

# 创建 minio
docker run -d -p 9000:9000 -p 9001:9001 --name minio --restart always -v ~/minio/data:/data -e "MINIO_ROOT_USER=admin" -e "MINIO_ROOT_PASSWORD=chengxun" minio/minio server /data --console-address ":9001"

# 创建 nexus
docker run -d -p 8081:8081 --name nexus --restart always -v /root/nexus/nexus-data:/nexus-data sonatype/nexus3:3.37.3
```

### Maven

- 批量修改工程版本号

```shell
mvn versions:set -DnewVersion=2.5.3
```

### Shell

- nohup 启动程序

```shell
nohup java -jar cube-module-system-0.2.1.jar &
```

- nmcli 设置静态ip

```shell
# x.x.x.x/32 = x.x.x.x 255.255.255.255
# x.x.x.x/24 = x.x.x.x 255.255.255.0
# x.x.x.x/23 = x.x.x.x 255.255.254.0
nmcli con mod enp0s3 ipv4.method manual ipv4.addresses 192.168.151.161/23 ipv4.gateway 192.168.150.1
```

### Git

```shell
java -jar bfg-1.13.1.jar --delete-folders db #将文件从commit历史流中删除
```

### 配置文件

#### docker

```json
{
  "registry-mirrors": [
    "https://docker.mirrors.ustc.edu.cn/"
  ],
  "log-driver": "json-file",
  "log-opts": {
    "max-size": "100m",
    "max-file": "3"
  }
}
```
