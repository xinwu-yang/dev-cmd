###  常用命令行
###### Docker
- docker run -d -p 3306:3306  -e MYSQL_ROOT_PASSWORD=chengxun --name mysql --restart always mysql:8 --lower_case_table_names=1 --default_authentication_plugin=mysql_native_password
