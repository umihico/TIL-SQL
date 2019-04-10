```
SELECT time FROM products where time between date_format('2017-6-28', '%Y-%m-%d') AND date_format('2017-6-30', '%Y-%m-%d')
SELECT COLUMN_name,COLUMN_COMMENT FROM information_schema.COLUMNS WHERE TABLE_NAME = 'products_table'
SELECT table_name, table_comment FROM information_schema.tables
whereRaw("products_name like ? ",["%".$http_request->products_name."%"])
SELECT table_name, table_comment FROM information_schema.tables WHERE table_schema = database();
create table tag(
	id int primary key auto_increment,
	tag0 varchar(60) not null,
	tag1 varchar(60) not null,
	pair_id varchar(60) not null unique,
	count int not null
)DEFAULT CHARSET=utf8
show table status from database_name
show variables like 'character%';
drop table xxxx;
select sleep(5);
sELECT * FROM t_stock_customer WHERE mid(replace(mobile,'-',''), 1) = replace'8012345678'
create table products( id int not null primary key auto_increment, products_id int not null, tag_id int not null, foreign key(tag_id) references tag(id), foreign key(products_id) references products(products_id), UNIQUE KEY (products_id, tag_id)) DEFAULT CHARSET=utf8
SHOW VARIABLES LIKE '%query_cache_%'
show create table products
ALTER TABLE products DROP column 7digit_id;
ALTER TABLE products ADD 7digit_id varchar(7) GENERATED ALWAYS AS (right(`id`,7)) STORED
```
