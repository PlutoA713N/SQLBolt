## SQL Lesson 1: SELECT queries 101

+ SELECT title FROM movies;
+ SELECT director FROM movies;
+ SELECT title, director FROM movies;
+ SELECT title, year FROM movies;
+ SELECT * FROM movies;


### SQL Lesson 2: Queries with constraints (Pt. 1)

+ SELECT *
  FROM Movies
  WHERE id = 6
+ SELECT * 
  FROM Movies
  WHERE year BETWEEN 2000 AND 2010
+ SELECT *
  FROM Movies
  WHERE year NOT BETWEEN 2000 AND 2010+
+ SELECT Title, Year FROM Movies
   WHERE Year <= 2003;


### SQL Lesson 3: Queries with constraints (Pt. 2)

+ SELECT * FROM Movies
  WHERE Title LIKE "%Toy Story%"  || SELECT * FROM MOVIESwhere title like "toy story%"
+ SELECT * FROM Movies
  WHERE Director = "John Lasseter"
+ SELECT * FROM Movies
  WHERE Director != "John Lasseter"
+ SELECT * FROM Movies
  WHERE Title LIKE '%wall%' || select * from movieswhere title like 'wall-_'


## SQL Lesson 4: Filtering and sorting Query results

+ SELECT DISTINCT Director FROM Movies
  ORDER BY Director ASC/DESC;
+ select title from movies
  order by year desc
  limit 4;
+ select title from movies
  order by title asc
  limit 5;
+ select title from movies
  order by title asc
  limit 5 offset 5;

## SQL Review: Simple SELECT Queries

+ select city, population from north_american_cities
  where country = "Canada";
+ select city, latitude from north_american_cities
  where country = "United States"
  order by latitude desc;
+ select city, longitude from north_american_cities
  where longitude < -87.629798
  order by longitude asc;
+ select city, population from north_american_cities
  where country = "Mexico"
  order by population desc
  limit 2;
+ SELECT city, population FROM north_american_cities
  WHERE country LIKE "United States"
  ORDER BY population DESC
  LIMIT 2 OFFSET 2;


## SQL Lesson 6: Multi-table queries with JOINs


+ select * from Movies
  join Boxoffice
  on Movies.id = Boxoffice.Movie_id;
+ select * from movies
  join boxoffice
  on movies.id = boxoffice.movie_id
  where international_sales > domestic_sales
+ select * from movies
  join boxoffice
  on movies.id = boxoffice.movie_id
  order by rating desc;


## SQL Lesson 7: OUTER JOINs


+ select distinct building from employees
+ select building_name, capacity from buildings
+ select distinct building_name, role
  from buildings
  left join employees
  on buildings.building_name = employees.building;


## SQL Lesson 8: A short note on NULLs

+ select name, role
  from employees
  where building isNull;
+ SELECT DISTINCT building_name
  FROM buildings 
  LEFT JOIN employees
    ON building_name = building
  WHERE role IS NULL;


## SQL Lesson 9: Queries with expressions


+ select title, (boxoffice.domestic_sales + boxoffice.international_sales)/ 1000000 as sales
 from movies
 join boxoffice
  boxoffice.movie_id = movies.id
+ SELECT title, rating * 10 AS rating_percent
  FROM movies
  JOIN boxoffice
    ON movies.id = boxoffice.movie_id;
+ select title 
  from movies
  where year % 2 = 0


##  SQL Lesson 10: Queries with aggregates (Pt. 1)


+  select max(years_employed) as longest_time
   from employees
+ select role, avg(years_employed) as average
  from employees
  group by role;
+ select building, sum(years_employed) as service
  from employees
  group by building





