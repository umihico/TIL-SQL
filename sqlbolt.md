```
SELECT title FROM movies;
SELECT director FROM movies;
SELECT title,director FROM movies;
SELECT * FROM movies;
SELECT * FROM movies where id = 6;
SELECT * FROM movies where year between 2000 and 2010;
SELECT * FROM movies where year not between 2000 and 2010;
SELECT title,year FROM movies where id <= 5;
SELECT * FROM movies where title like "Toy Story%";
SELECT * FROM movies where director like "John Lasseter";
SELECT * FROM movies where director not like "John Lasseter";
SELECT * FROM movies where title like "WALL-%";
SELECT distinct director FROM movies order by director;
SELECT title FROM movies order by year desc limit 4;
SELECT title FROM movies order by title asc limit 5;
SELECT title FROM movies order by title asc limit 5 offset 5;
SELECT city,population FROM north_american_cities where country = "Canada";
SELECT city FROM north_american_cities where country = "United States" order by latitude desc;
SELECT city FROM north_american_cities where longitude<-87.629798 order by longitude asc;
SELECT city FROM north_american_cities where country='Mexico' order by population desc limit 2;
SELECT city FROM north_american_cities where country='United States' order by population desc limit 2 offset 2;
SELECT * FROM movies inner join boxoffice on movies.id=boxoffice.movie_id;
SELECT title,domestic_sales,international_sales FROM movies inner join boxoffice on movies.id=boxoffice.movie_id where domestic_sales>international_sales;
SELECT title,rating FROM movies inner join boxoffice on movies.id=boxoffice.movie_id order by rating desc;
SELECT distinct building_name FROM buildings left join employees on buildings.building_name=employees.building where building;
SELECT distinct building_name,role FROM buildings left join employees on building_name=building;
select building_name from buildings left join employees on building_name=building where role is null;
SELECT title,(domestic_sales+international_sales)/1000000 FROM movies left join boxoffice on id = movie_id;
SELECT title,rating*10 FROM movies left join boxoffice on id = movie_id;
SELECT title,year FROM movies left join boxoffice on id = movie_id where year%2=0;
SELECT max(years_employed) FROM employees;
SELECT role,avg(years_employed) FROM employees group by role;
SELECT building,sum(years_employed) FROM employees group by building;
SELECT max(years_employed) FROM employees;
SELECT role, avg(years_employed) as avg FROM employees group by role;
SELECT building,sum(years_employed) as avg FROM employees group by building;
SELECT count() FROM employees group by role having role="Artist";
SELECT role,count() FROM employees group by role;
SELECT role,sum(years_employed) FROM employees group by role having role="Engineer";
SELECT director, count() FROM movies group by director;
SELECT director, sum(Domestic_sales)+sum(International_sales) FROM movies left join boxoffice on id=movie_id group by director;
INSERT INTO Movies (Id,Title,Director,Year,Length_minutes) VALUES (4, "Toy Story 4", "John Lasseter",2019,120);
INSERT INTO boxoffice (Movie_id,Rating,Domestic_sales,International_sales) VALUES (4, 8.7, 340000000,270000000);
update movies set Director="John Lasseter" where title="A Bug's Life";
update movies set year=1999 where title="Toy Story 2";
update movies set title="Toy Story 3",director="Lee Unkrich" where title="Toy Story 8";
delete from movies where year<2005;
delete from movies where director="Andrew Stanton";
create table if not exists Database(Name text, Version float, Download_count integer);
alter table movies add Aspect_ratio float;
ALTER TABLE Movies ADD COLUMN Language TEXT DEFAULT "English";
drop table if exists movies;
```

## Intermidiate
```
SELECT * FROM sales_associates WHERE salary > (SELECT AVG(revenue_generated) FROM sales_associates);
SELECT * FROM employees WHERE salary > (SELECT AVG(revenue_generated) FROM employees AS dept_employees WHERE dept_employees.department = employees.department);
SELECT * FROM mytable WHERE column IN/NOT IN (SELECT another_column FROM another_table);
SELECT column, another_column FROM mytable
  UNION / UNION ALL / INTERSECT / EXCEPT
  SELECT other_column, yet_another_column FROM another_table
  ORDER BY column DESC
  LIMIT n;
```
