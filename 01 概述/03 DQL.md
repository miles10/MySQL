# DML
   * 添加数据 INSERT
   * 更新数据 UPDATE
   * 删除数据 DELETE

## 添加数据
1. 添加数据
   ```SQL
   INSERT INTO 表名 (字段名1, 字段名2) VALUES (值1, 值2)
   ```
2. 更新数据
   ```SQL
   UPDATE 表名 SET 字段名1 =  值1 WHERE 字段名2 = 值2;
   ```

3. 删除数据
   ```SQL
   DELETE 表名  WHERE 字段名2 = 值2;
   ```

# 查询语句
1. 查询语句
   ```SQL
   SELECT * FROM 表名  WHERE 字段名 = 值;
   ```
   > 尽量不直接使用 * 影响效率

2. 比较运算符   逻辑运算符
   | 比较运算符  | 功能 | 
   | :-----:| :----: |
   | = | 等于 | 
   | >= | 大于等于 | 
   | > | 大于 | 
   | <= | 小于等于 | 
   | < | 小于 | 
   | <> 或 != | 不等于 | 
   | BETWEEN...AND | 某个范围之间（含最小、最大值） |
   | IN(...) | 在 in 的列表之中的值 |
   | LIKE | 模糊匹配 |
   | IS NULL | 为 NULL |

   |  逻辑运算符 | 功能 | 
   | :-----:| :----: |
   | AND 或 && | 且 |     
   | OR 或 ||  | 或 |
   | NOT 或 !  | 非 |  

3. 聚合函数
   > 将一列数据作为一个整体计算，所有的 null 值不参与 聚合函数计算  
   ### 常用聚合函数
     函数 | 功能 | 
   | :-----:| :----: |
   | COUNT | 计数 |  
   | SUM | 求和 |     
   | AVG | 平均  |
   | MAX | 最大 |  
   | MIN | 最小 |  

4. 分组查询
   ```SQL
   SELECT * FROM 表名  [WHERE 字段名 = 值] GROUP BY 分组字段名 [HAVING 分组过滤条件];
   ```

   > WHERE 与 HAVING 区别
   > * 执行时机不同：WHERE 是分组之前进行过滤，不满足 WHERE 条件，不参与分组；HAVING 是分组之后对结果进行过滤。
   > * 判断条件不同：WHERE 不能对聚合函数进行判断，HAVING 可以。
   > * 执行顺序：WHERE > 聚合函数 > HAVING
   > * 分组之后 查询字段一般为 聚合函数 与 分组字段，其他字段无意义。

5. 排序查询
   ```SQL
   SELECT * FROM 表名  [WHERE 字段名 = 值] ORDER BY 字段1 排序方式1, 字段2 排序方式2;
   ```
   > 升序 ASC 默认，降序 DESC

6. 分页查询
   ```SQL
   SELECT * FROM 表名  [WHERE 字段名 = 值] LIMIT 起始索引, 查询记录数;
   ```
   > * 起始索引 从 0 开始，起始索引 = (查询页码 - 1) * 每页显示记录数
   > * MySQL 使用 LIMIT 分页查询，其他数据库用其他方式实现
   > * 如果查询数据是第一页，起始索引可以省略，直接写 LIMIT 10

## DQL 执行顺序
    1. FROM 表
    2. WHERE 条件
    3. GROUP BY 分组
    4. SELECT 选取 字段
    5. ORDER BY 排序
    6. LIMIT 分页