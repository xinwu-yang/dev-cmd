###  常用命令行
###### Docker
- docker run -d -p 3306:3306  -e MYSQL_ROOT_PASSWORD=chengxun --name mysql --restart always mysql:8 --lower_case_table_names=1 --default_authentication_plugin=mysql_native_password
- 修改gitlab的host和port
  - vim /opt/gitlab/embedded/service/gitlab-rails/config/gitlab.yml
  - gitlab-ctl restart
