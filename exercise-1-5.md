# Exercise 1 — Tasks

# Movies Table

| id | title               | director          | year | length_minutes |
|----|--------------------|------------------|------|---------------|
| 1  | Toy Story          | John Lasseter    | 1995 | 81            |
| 2  | A Bug's Life       | John Lasseter    | 1998 | 95            |
| 3  | Toy Story 2        | John Lasseter    | 1999 | 93            |
| 4  | Monsters, Inc.     | Pete Docter      | 2001 | 92            |
| 5  | Finding Nemo       | Andrew Stanton   | 2003 | 107           |
| 6  | The Incredibles    | Brad Bird        | 2004 | 116           |
| 7  | Cars               | John Lasseter    | 2006 | 117           |
| 8  | Ratatouille        | Brad Bird        | 2007 | 115           |
| 9  | WALL-E             | Andrew Stanton   | 2008 | 104           |
| 10 | Up                 | Pete Docter      | 2009 | 101           |
| 11 | Toy Story 3        | Lee Unkrich      | 2010 | 103           |
| 12 | Cars 2             | John Lasseter    | 2011 | 120           |
| 13 | Brave              | Brenda Chapman   | 2012 | 102           |
| 14 | Monsters University| Dan Scanlon      | 2013 | 110           |


## 1. Find the title of each film
~~~sql 
SELECT title FROM movies;
~~~
## 2. Find the director of each film

~~~sql 
SELECT director FROM movies;
~~~
## 3. Find the title and director of each film
~~~sql 
SELECT title ,director FROM movies;
~~~

## 4. Find the title and year of each film
~~~sql 
SELECT title ,year FROM movies;
~~~

## 5. Find all the information about each film
~~~sql 
SELECT * FROM movies;
~~~

# Exercise 2 — Tasks 

## 6. Find the movie with a row id of 6
~~~sql
SELECT * 
FROM movies
WHERE id = 6;
~~~

## 7. Find the movies released in the years between 2000 and 2010
~~~sql
SELECT * 
FROM movies
WHERE year BETWEEN 2000 AND 2010;
~~~

## 8. Find the movies not released in the years between 2000 and 2010
~~~sql
SELECT * 
FROM movies
WHERE year NOT BETWEEN 2000 AND 2010;
~~~

## 9. Find the first 5 Pixar movies and their release year
~~~sql
SELECT title, year 
FROM movies
where id between 1 and 5;
~~~

# Exercise 3 — Tasks 

## 10. Find all the Toy Story movies
~~~sql
SELECT * 
FROM movies
WHERE title LIKE 'Toy Story%';
~~~

## 11. Find all the movies directed by John Lasseter
~~~sql
SELECT * 
FROM movies
WHERE director = 'John Lasseter';
~~~

## 12. Find all the movies (and director) not directed by John Lasseter
~~~sql
SELECT title, director 
FROM movies
WHERE director != 'John Lasseter';
~~~

## 13. Find all the WALL-* movies
~~~sql
SELECT * 
FROM movies
WHERE title LIKE 'WALL-%';
~~~

## 14. List all directors of Pixar movies (alphabetically), without duplicates
~~~sql
SELECT DISTINCT director
FROM movies
ORDER BY director ASC;
~~~

## 15. List the last four Pixar movies released (ordered from most recent to least)
~~~sql
SELECT * 
FROM movies
ORDER BY year DESC
LIMIT 4;
~~~

## 16. List the first five Pixar movies sorted alphabetically
~~~sql
SELECT * 
FROM movies
ORDER BY title ASC
LIMIT 5;
~~~

## 17. List the next five Pixar movies sorted alphabetically
~~~sql
SELECT * 
FROM movies
ORDER BY title ASC
LIMIT 5;
~~~
# EXERCISE 5 

## 18. List all the Canadian cities and their populations
~~~sql
SELECT city, population
FROM north_american_cities
WHERE country = 'Canada';
~~~

## 19. Order all the cities in the United States by their latitude from north to south
~~~sql
SELECT city, latitude
FROM north_american_cities
WHERE country = 'United States'
ORDER BY latitude DESC;
~~~

## 20. List all the cities west of Chicago, ordered from west to east
~~~sql
SELECT city, longitude
FROM north_american_cities
WHERE longitude < -87.629798
ORDER BY longitude ASC;
~~~


## 21. List the two largest cities in Mexico (by population)
~~~sql
SELECT city, population
FROM north_american_cities
WHERE country = 'Mexico'
ORDER BY population DESC
LIMIT 2;
~~~

## 22. List the third and fourth largest cities (by population) in the United States and their population
~~~sql
SELECT city, population
FROM north_american_cities
WHERE country = 'United States'
ORDER BY population DESC
LIMIT 2 ;
~~~

# Exercise 6

## 23. Find the domestic and international sales for each movie
~~~sql
SELECT Movies.Title, Boxoffice.Domestic_sales, 
Boxoffice.International_sales
FROM movies
JOIN Boxoffice 
ON Movies.Id = Boxoffice.movie_id
~~~

## 24. List all the movies by their ratings in descending order
~~~sql
SELECT title, rating
FROM movies
  JOIN boxoffice
    ON movies.id = boxoffice.movie_id
ORDER BY rating DESC;
~~~

# Exercise 7
## 25. Find the list of all buildings that have employees 
~~~sql
SELECT DISTINCT FROM BUILDING;

~~~

## 26. Find the list of all buildings and their capacity
~~~sql
SELECT * FROM buildings;
~~~

## 27. List all buildings and the distinct employee roles in each building (including empty buildings) 
~~~sql
SELECT DISTINCT building_name, role 
FROM buildings 
LEFT JOIN employees
ON building_name = building;
~~~
# Exercise 8

## 28. Find the name and role of all employees who have not been assigned to a building
~~~sql
SELECT name, role FROM employees
WHERE building IS NULL;
~~~
## 29. Find the names of the buildings that hold no employees 
~~~sql
SELECT DISTINCT building_name
FROM buildings 
  LEFT JOIN employees
    ON building_name = building
WHERE role IS NULL;
~~~

# Exercise 9

## 30. List all movies and their combined sales in millions of dollars
~~~sql
SELECT Titil, ( domestic_sales + International ) / 100000 as million
FROM movie 
join boxoffice on movies.ID = Boxoffice.Movie_ID;
~~~
## 31. List all movies and their ratings in percent
~~~sql
SELECT Title, Rating * 10 AS rating_percent
FROM movies
JOIN boxoffice ON movies.Id = Boxoffice.Movie_id;
~~~

## 32. List all movies that were released on even number years

~~~sql
SELECT Title, Year
FROM movies
JOIN boxoffice ON movies.Id = Boxoffice.Movie_id
WHERE Year % 2 = 0;
~~~

# Exercise 10

## 33. Find the longest time that an employee has been at the studio

~~~sql

~~~
