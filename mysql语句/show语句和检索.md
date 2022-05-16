[toc]

## show语句

```mysql
USE dborder;
SHOW DATABASES;
SHOW TABLES;
SHOW COLUMNS FROM customers;
/*SHOW COLUMNS 要求给出一个表名 */
```

- Extre 自动增量 

  > 在每个行添加到表中时，自动的填入下一个数据；
  >
  > 必须记住最后一次使用的值
  >
  > 必须在create表的时候，作为定义表的组成部分

```mysql
SHOW STATUS;#用于显示广泛的服务器状态
# TABLE，分别用来显示创建特定数据库或表的MySQL语句；
# 但是好像没有用
SHOW CREATE DATABASE;
SHOW CREATE TABLE;

# 显示授予用户（所有的或者特定的）的安全权限
SHOW GRANTS;
# 显示服务器错误或者警告信息
SHOW ERRORS;
SHOW WARNINGS;
```



## select 语句



- 使用slect 语句至少给出两点内容
   	1. 想选择什么
   	2. 从什么地方选取

```mysql
# 从products表中检索一个prod_name的列
# 可以有过滤 和 排序 
SELECT prod_name
FROM products;
```

>语句的结束要加 ;
>
>其他语言 可能是单句就要加分号，视情况而定
>
>SQL语句不区分大小写，但MYSQL4.之前，有些标识符区分大小写（数据库名，表名，列名）可能不同
>
>最佳方式是按照大小写的惯例，且使用时保持一致
>
>sql语句的空行会被忽略

### 检索多个列和所有的列

```mysql
##################################
# 从products表中检索一个prod_name的列
# 可以有过滤 和 排序 
SELECT prod_name
FROM products;
# 检索多个列
# 返回原始的没有格式的数据
SELECT `prod_id`,`prod_name`,`prod_price`
FROM products;
# 检索所有列 使用 * 通配符
# 返回表中所有列，列的顺序一般是列在表中定义的顺序
# 表的变化会打破这种顺序 
SELECT * 
FROM products;

```

>检索多个列的时候一般不使用，多余的列，会降低检索的性能。

### 检索行

```mysql
# 检索的是所有的行
SELECT vend_id
FROM products;

# 使用distinct检索不同的值（行）
SELECT DISTINCT vend_id
FROM products;

SELECT prod_price
FROM products;
# distinct 应用于所有的列， 因此不会出现两个列都相同的情况
SELECT DISTINCT vend_id,prod_price
FROM products;
```

### 限制检索的结果

```mysql
# 返回前几行
SELECT prod_name
FROM products
LIMIT 5;

# 返回第五行开始的第五行

SELECT prod_name
FROM products
LIMIT 5,5;

SELECT prod_name
FROM products
limit 3,4; 

SELECT prod_name
FROM products
limit 4 OFFSET 3;
```

>limit 1,1 返回的是第二行，limit 检索的行数是从0开始的
>
>带一个值得 limit 返回的是从第0行开始的前五行
>
>带两个值得 limit n,m  返回的是从 n行开始的m行
>
>行数不够的，mysql 只返回，能够放回的行
>
>LIMIT 3,4 相当于 LIMIT 4 OFFSET 3 

### 使用完全限定得表名

```mysql
SELECT products.`prod_name`
FROM dborder.`products`;
```

> 有些时候需要用到，但是现在只需要认识就好





- 本章学习了如何使用SQL的SELECT语句来检索单个表列、多个表列
  以及所有表列
