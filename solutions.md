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

