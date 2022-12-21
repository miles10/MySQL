# DCL
> 管理数据库用户，控制数据库访问权限

1. 查询用户
   ```SQL
   USE mysql;
   SELECT * FROM user;
   ```

2. 创建用户
   ```SQL
   CREATE USER '用户名'@'主机名' IDENTIFIED BY '密码';
   ```

3. 修改用户密码
   ```SQL
   ALTER USER '用户名'@'主机名' IDENTIFIED WITH mysql_native_password BY '新密码';
   ```

4. 删除用户
   ```SQL
   DROP USER '用户名'@'主机名';
   ```

# 权限控制
|  权限 | 说明 | 
| :-----:| :----: |
| ALL, ALL PRIVILEGES | 所有权限 |     
| SELECT | 查询 |
| INSERT | 增加 |  
| UPDATE | 更新 |  
| DELECT | 删除 | 
| ALTER | 修改表 |   
| DROP | 删除表/库/视图 | 
| CREATE | 创建表/库 |   

1. 查询权限
   ```SQL
   SHOW GRANTS FOR '用户名'@'主机名';
   ```

2. 授予权限
   ```SQL
   GRANT 权限列表 ON 数据库名.表名 TO '用户名'@'主机名';
   ```

3. 撤销权限
    ```SQL
   REVOKE 权限列表 ON 数据库名.表名 FROM '用户名'@'主机名';
   ```