# DataBase

```
http://tsuozoe.pixnet.net/blog/post/21283890-mysql-%E5%9F%BA%E6%9C%AC%E6%93%8D%E4%BD%9C%E8%AA%9E%E6%B3%95
```

# 啟動 MySQL
```
net start mysql
```
# 查詢資料庫、資料表、欄位等資訊
```
mysqlshow [-h ipAddress] -u user_name -p
mysqlshow -u user_name@ipAddress -p
列出所有資料庫
```
# 列出該 database_name 所有資料表
```
mysqlshow -u user_name -p db_name
```
# 列出該 database_name 裡 table_name 資料表裡的欄位
```
mysqlshow -u user_name -p db_name table_name
```
# 列出該 database_name 裡 table_name 的 field_name 的欄位資訊
```
mysqlshow -u user_name -p db_name table_name field_name
```
# 更改密碼:更改目前系統登入使用者的密碼
```
mysqladmin password 'new_password'
```
# 於資料庫中導入執行sql script 檔
```
mysql db_name < sql_filename.sql
```
與 MySQL 連線
mysql [-h ipAddress] -u user_name -ppassword
mysql [-h ipAddress] -u user_name -p

切換使用資料庫 database_name
mysql> USE db_name

mysql> SELECT DATABASE();
列出目前預設的資料庫名稱

mysql> SHOW DATABASES;
列出所有資料庫

mysql> SHOW DATABASES LIKE 'my%';
列出所有資料庫名稱為 my 開頭的

mysql> SHOW TABLES FROM db_name [LIKE ...];
列出該資料庫所有資料表名稱

mysql> SHOW COLUMNS FROM table_name [LIKE ...];
mysql> SHOW COLUMNS FROM table_name FROM db_name  [LIKE ...];
mysql> SHOW FIELDS FROM table_name [LIKE ...];
mysql> DESCRIBE table_name ;
mysql> EXPLAIN table_name ;
列出該資料表所有欄位名稱

mysql> SHOW INDEX FROM table_name [LIKE ...];
mysql> SHOW INDEX FROM table_name FROM db_name  [LIKE ...];
mysql> SHOW KEY FROM table_name [LIKE ...];
列出該資料表所有索引資訊

mysql> SHOW TABLE STATUS;
mysql> SHOW TABLE STATUS FROM db_name  [LIKE ...];列出資料表的相關資訊

mysql> SHOW VARIABLES [LIKE ...];
顯示 MySQL 相關參數設定

mysql> SHOW VARIABLES LIKE '%character%' ;
顯示資料庫語系設定資訊

mysql> SHOW PROCESSLIST;
列出與 MySQL 連線的 threads 狀態

mysql> SHOW STATUS;
列出與 MySQL 目前的狀態

當進行資料表檢查或修補時，鎖定資料表可確保資料表的安全
(READ：唯讀狀態、WRITE：無法寫入也無法讀取)
mysql> LOCK TABLE table_name READ;
mysql> FLUSH TABLES;
鎖定資料表 

mysql> UNLOCK TABLE;
資料表解除鎖定 
