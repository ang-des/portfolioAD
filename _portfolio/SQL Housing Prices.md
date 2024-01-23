---
title: Housing Prices Data
image: assets/img/portfolio/housingmarket.png
alt: SQL

caption:
  title: Housing Prices Data
  subtitle: SQL
  thumbnail: assets/img/portfolio/housingmarket.png
---

# Housing Prices Data

<br>

1. Write a query that returns a list of distinct values in the yearbuilt field.  <br><br>
```
SELECT DISTINCT yearbuilt
FROM houseprices;
```

2. How many unique values are there for the mszoning field (alias this as count_mszoning), and mssubclass field (alias this as count_mssubclass)?  <br><br>
```
SELECT COUNT(DISTINCT mszoning) AS count_mszoning, 
	COUNT(DISTINCT mssubclass) AS count_mssubclass
FROM houseprices;
```

3. Write a query that returns a list of all the unique combinations for street and lotshape, sorted alphabetically by street.  <br><br>
```
SELECT DISTINCT street, lotshape
FROM houseprices
ORDER BY street;
```

4. Create a report that shows the number of records for each neighborhood and lotconfig pair. Alias the count of records to count_lotconfig. Order the results by neighborhood (A-Z), count_lotconfig (smallest-largest), and lotconfig (A-Z).  <br><br>
````
SELECT neighborhood, lotconfig, COUNT(lotconfig) AS count_lotconfig
FROM houseprices
GROUP BY neighborhood, lotconfig
ORDER BY neighborhood, count_lotconfig, lotconfig;
````

5. Write a query that returns the average saleprice of houses per yearbuilt—call this field avg_saleprice—rounded to the nearest whole number and sorted from newest to oldest. Hint: Within the first line of your query, use the following code so that the proper data type is used to avoid results displaying in scientific notation: ROUND(AVG(saleprice),0)::float  <br><br>
````
SELECT yearbuilt, ROUND(AVG(saleprice), 0)::float AS avg_saleprice
FROM houseprices
GROUP BY yearbuilt
ORDER BY yearbuilt DESC;
````

6. Write a query that shows the average number of cars for the column garagecars (using the alias avg_garage) per yearbuilt. Only includehouses that have 1 or more garagecars in this average. Round your answer to the nearest whole number. Hint: Within the first line of your query, use the following code so that the proper data type is used to avoid results displaying in scientific notation: ROUND(AVG(garagecars),0)::float  <br><br>
````
SELECT yearbuilt, ROUND(AVG(garagecars), 0)::float AS avg_garage
FROM houseprices
WHERE garagecars >= 1
GROUP BY yearbuilt;
````

7. Write a query that shows for each yearbuilt, how many houses had zero garages and the largest lotarea amount for that year.  <br><br>
````
SELECT yearbuilt, MAX(lotarea), COUNT(*)
FROM houseprices
WHERE garagecars = 0
GROUP BY yearbuilt;
````

8. For each yearbuilt, find the average lotarea — call it avg_lot_per_year —and return only those results for which the average is smaller than 10,000, sorted high to low. Hint: Within the first line of your query, use the following code so that the proper data type is used to avoid results displaying in scientific notation: avg(lotarea)::float  <br><br>
`````
SELECT yearbuilt, AVG(lotarea)::float AS avg_lot_per_year
FROM houseprices
GROUP BY yearbuilt
HAVING AVG(lotarea)::float < 10000
ORDER BY avg_lot_per_year DESC;
`````

9. Write a query that shows, for each yearbuilt, how many houses had a lotarea between 10,000 and 15,000, inclusive. Finally, order it by yearbuilt from oldest to newest.  <br><br>
`````
SELECT yearbuilt, COUNT(*)
FROM houseprices
WHERE lotarea BETWEEN 10000 AND 15000
GROUP BY yearbuilt
ORDER BY yearbuilt;
`````

10. Write a query that shows the average overall quality overallqual (rounded to 0 decimals and renamed as avg_quality) and the number of unique garage types (garagetype) renamed as garage_count for each neighborhood, sorted by neighborhood. Hint: Within the first line of your query, use the following code so that the proper data type is used to avoid results displaying in scientific notation: ROUND(AVG(overallqual),0)::integer  <br><br>
`````
SELECT ROUND(AVG(overallqual), 0)::integer AS avg_quality, 
	COUNT(DISTINCT garagetype) AS garage_count, neighborhood
FROM houseprices
GROUP BY neighborhood
ORDER BY neighborhood;
`````

11. Write a query that selects the average lotarea (rounded to 2 decimals) per yearbuilt where the street is not gravel (Grvl) and lotconfig is a corner (Corner). Moreover, select only the average lotarea records greater than 1,000, and sort your results by yearbuilt from oldest to newest. Hint: Within the first line of your query, use the following code so that the proper data type is used to avoid results displaying in scientific notation: ROUND(AVG(lotarea),2)::float  <br><br>
```````
SELECT ROUND(AVG(lotarea), 2)::float, yearbuilt
FROM houseprices
WHERE street != 'Grvl' AND lotconfig = 'Corner'
-- (or) WHERE street NOT IN('Grvl')
GROUP BY yearbuilt
HAVING AVG(lotarea) > 1000
ORDER BY yearbuilt;
```````
