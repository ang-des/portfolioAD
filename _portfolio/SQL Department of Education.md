# Department of Education Data

1. From the naep table, Write a query that selects column_name and data_type from information_schema.columns.  
```
SELECT column_name, data_type
FROM information_schema.columns
WHERE table_name = 'naep';
```

2. Write a query to select the first fifty records of the naep table.  
```
SELECT *
FROM naep
LIMIT 50;
```

3. Write a query that returns summary statistics for avg_math_4_score by state. Do this by using aliases, such as COUNT(avg_math_4_score) as count_4, and repeat this for the remaining aliases avg_4, min_4, and max_4, for AVG, MIN, and MAX, respectively. Finally, sort the results alphabetically by state name.  
```
SELECT state, COUNT(avg_math_4_score) AS count_4,
		AVG(avg_math_4_score) AS avg_4,
		MIN(avg_math_4_score) AS min_4,
		MAX(avg_math_4_score) AS max_4
FROM naep
GROUP BY state
ORDER BY state;
```

4. Write a query that alters the previous query so that it returns only the summary statistics for avg_math_4_score by state with differences in max and min values that are greater than 30.  
```
SELECT state, COUNT(avg_math_4_score) AS count_4,
		AVG(avg_math_4_score) AS avg_4,
		MIN(avg_math_4_score) AS min_4,
		MAX(avg_math_4_score) AS max_4
FROM naep
GROUP BY state
HAVING (MAX(avg_math_4_score) - MIN(avg_math_4_score)) > 30
ORDER BY state;
```

5. You want to report the 10 lowest-performing states for avg_math_4_score in the year 2000. Write a query that returns the avg_math_4_score as the alias avg_score and the state as the alias bottom_10_states that lists the states in the bottom 10 for avg_math_4_score in the year 2000. Hint: You'll need to use the following type declaration in your query, or it will render as scientific notation in Qualified. SELECT avg_math_4_score::float AS avg_score, state AS bottom_10_states  
```
SELECT avg_math_4_score::float AS avg_score, state AS bottom_10_states
FROM naep
WHERE year = '2000'
ORDER BY avg_score
LIMIT 10;
```

6. Write a query that calculates the average avg_math_4_score rounded to the nearest 2 decimal places over all states in the year 2000. The resulting variable should still be named avg_math_4_score.  
```
SELECT ROUND(AVG(avg_math_4_score), 2) AS avg_math_4_score
FROM naep
WHERE year = '2000';
```

7. Write a query that returns a field called below_250 that lists all states with an avg_math_4_score less than 250, over all states in the year 2000. Hint: Your query should produce 41 records.  
```
SELECT state AS below_250
FROM naep
WHERE avg_math_4_score < 250
    AND year = '2000';
```

8. Write a query that returns a field called scores_missing_y2000 that lists any states with missing values in the avg_math_4_score column of the naep data table for the year 2000.  
```
SELECT state AS scores_missing_y2000
FROM naep
WHERE avg_math_4_score IS NULL
    AND year = '2000';
```

9. Write a query that returns, for the year 2000, the state, avg_math_4_score, and total_expenditure fields from the naep table left outer joined on the finance table, using id as the key and ordered by total_expenditure, from largest to smallest. Be sure to round avg_math_4_score to the nearest 2 decimal places, keeping the variable name as is using an alias, and then filter out NULL from avg_math_4_scores in order to see the results more clearly.  
```
SELECT n.state, ROUND(n.avg_math_4_score, 2) AS avg_math_4_score, f.total_expenditure
FROM naep AS n
LEFT OUTER JOIN finance AS f ON n.id = f.id
WHERE n.year = '2000'
    AND avg_math_4_score IS NOT NULL
ORDER BY f.total_expenditure DESC;
```
