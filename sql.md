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
```
