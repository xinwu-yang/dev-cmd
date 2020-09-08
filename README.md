###  常用命令行
###### Docker
- docker run -d -p 3306:3306  -e MYSQL_ROOT_PASSWORD=chengxun --name mysql --restart always mysql:8 --lower_case_table_names=1 --default_authentication_plugin=mysql_native_password
- 修改gitlab的host和port
  - vim /opt/gitlab/embedded/service/gitlab-rails/config/gitlab.yml
  - gitlab-ctl restart
###### Shell
- 备份gitlab
  - gitlab-rake gitlab:backup:create
  - scp /var/opt/gitlab/backups/*$(date +%Y_%m_%d)_13.0.5_gitlab_backup.tar root@25.30.10.224:/root/xinwuy
