###  常用命令行
###### Docker
- docker run -d -p 3306:3306 -e MYSQL_ROOT_PASSWORD=chengxun --name mysql --restart always mysql:5.7 --lower_case_table_names=1
- docker run -d -p 3306:3306 -e MYSQL_ROOT_PASSWORD=chengxun --name mysql --restart always mysql:8 --lower_case_table_names=1 --default_authentication_plugin=mysql_native_password
- docker run -d -p 6379:6379 --name redis --restart always redis:6 --requirepass redis@123
- docker run -d -p 9001:80 --name cube-demo -v /root/xinwuy/demo/dist:/usr/share/nginx/html -v /root/xinwuy/demo/default.conf:/etc/nginx/conf.d/default.conf --restart=always nginx:stable
###### Shell
- 备份gitlab
  - gitlab-rake gitlab:backup:create
  - scp /var/opt/gitlab/backups/*$(date +%Y_%m_%d)_13.0.5_gitlab_backup.tar root@25.30.10.224:/root/xinwuy
 - 修改gitlab的host和port
  - vim /opt/gitlab/embedded/service/gitlab-rails/config/gitlab.yml
  - gitlab-ctl restart
- nohup 启动程序
  - nohup java -jar cube-module-system-0.2.1.jar &
###### Git
- java -jar bfg-1.13.1.jar --delete-folders db #将文件从commit历史流中删除
