# DDL
1. 查询所有数据库
   ```SQL
   SHOW DATABASES;
   ```
2. 查询当前数据库名称
    ```SQL
   SELECT DATABASE();
   ```
3. 创建数据库
   ```SQL
   CREATE DATABASE  数据库名称;
   ```
4. 删除数据库
   ```SQL
   DROP DATABASE  数据库名称;
   ```
5. 使用数据库
   ```SQL
   USE  数据库名称;
   ```

# DDL 表操作
1. 查询所有表
   ```SQL
   SHOW  TABLES;
   ```

2. 查询表结构
   ```SQL
   DESC  表名;
   ```

3. 查询指定表的建表语句
   ```SQL
   SHOW CREATE TABLE  表名;
   ```

4. 创建表
   ```SQL
   CREATE TABLE  表名(
    字段1 字段类型 [COMMENT 注释],
    字段2 字段类型 [COMMENT 注释],
    ...
   ) [COMMENT 表注释]
   ```

5. 修改表结构
   添加字段
   ```SQL
   ALTER TABLE  表名 ADD 字段名 类型(长度) [COMMENT 注释]
   ```
6. 修改字段
   修改数据类型
   ```SQL
   ALTER TABLE  表名 MODIFT 字段名 新数据类型(长度) [COMMENT 注释]
   ```

7. 修改字段名 和 类型
   ```SQL
   ALTER TABLE  表名 CHANGE 旧字段名 新字段名 新数据类型(长度) [COMMENT 注释]
   ```

8. 删除字段
   ```SQL
   ALTER TABLE  表名 DROP 字段名
   ```

9. 修改表名
    ```SQL
   ALTER TABLE  表名 RENAME TO 新表名
   ```

10. 删除表
   ```SQL
   DROP TABLE [IF EXISTS] 表名
   ```

11. 清空表 （删除然后重建表）
   ```SQL
   TRUNCATE TABLE 表名;
   ```