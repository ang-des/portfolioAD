---
title: Pet Salon Transactions
image: assets/img/portfolio/pet.png
alt: SQL

caption:
  title: Pet Salon Transactions
  subtitle: SQL
  thumbnail: assets/img/portfolio/pet.png
---

# Pet Salon Transactions

1. Write a query that returns the owner_id of the owners table and the transaction_id and service of the transactions table. Ensure that all records from the transactions table are returned, and sort the results in ascending order according to owner_id.  <br><br>
```
SELECT owner_id, transaction_id, service
FROM owners AS o
INNER JOIN transactions AS t ON o.pet_id = t.pet_id
ORDER BY owner_id;
```

2. Write a query that returns the owner_id, pet_id, transaction_id, and visits_count fields from their respective tables. Sort in order of transaction_id. Do not include records where transaction_id is NULL.  <br><br>
```
SELECT owner_id, o.pet_id, transaction_id, visits_count
FROM owners AS o
INNER JOIN transactions AS t ON o.pet_id = t.pet_id
INNER JOIN visits AS v ON t.pet_id = v.pet_id
ORDER BY transaction_id;
```

3. Write a query that returns the pet_id and size from the owners table, and the visits_count (as the alias num_visits) from the visits table. Keep only the records where dogs had 10 or more visits, and sort by the number of visits in descending order.  <br><br>
```
SELECT o.pet_id, size, visits_count AS num_visits
FROM owners AS o
INNER JOIN visits AS v ON o.pet_id = v.pet_id
WHERE visits_count >= 10
ORDER BY num_visits DESC;
```

4. There are 2 tables, owners and owners_2, that have information about dog owners. You want the list of all unique dog owners from both tables. Combine these 2 tables and return a single field that shows a list of owner_id records from both input tables, and order by owner_id. Keep only unique records.  <br><br>
```
SELECT owner_id
FROM owners
UNION
SELECT owner_id
FROM owners_2
ORDER BY owner_id;
```

5. You're having a customer rewards promotion, and you want to identify your top three customers (owner_id) based upon how many visits they've had. You also know that some owners have more than one pet, so you want to add up all of their visits across all pets. Once you have this, select the top three customers (owner_id) and list them in descending order according to number of visits (using the alias num_visits)!  <br><br>
```
SELECT owner_id, SUM(visits_count) AS num_visits
FROM owners AS o
INNER JOIN visits AS v ON o.pet_id = v.pet_id
GROUP BY owner_id
ORDER BY num_visits DESC
LIMIT 3;
```

6. Write a query that returns owner_id from both the owners and owners_2 tables and include the transaction_id, date, and service fields from the transactions table. Sort your results first by date, then by transaction_id, and finally by owner_id in descending order. All rows from owners and owners_2 tables should be returned. Do not include records where transaction_id is NULL.  <br><br>
```
SELECT o1.owner_id, transaction_id, date, service
FROM owners AS o1
LEFT OUTER JOIN transactions AS t ON o1.pet_id = t.pet_id
WHERE transaction_id IS NOT NULL
UNION ALL
SELECT o2.owner_id, transaction_id, date, service
FROM owners_2 AS o2
LEFT OUTER JOIN transactions AS t ON o2.pet_id = t.pet_id
WHERE transaction_id IS NOT NULL
ORDER BY date, transaction_id, owner_id DESC;
```

7. Return a table that includes all records from both owners and owners_2 tables, and include a new field, owner_pet which is formatted as owner_id, pet_id (in other words, the owner ID followed by a comma, then a space, then the pet ID). Return only the rows where the number of visits is greater than or equal to 3. Sort the results by number of visits (largest to smallest), and if there's a tie in this number, sort by your newly created owner_pet field. Use the CONCAT() function for this operation instead of the concat operator (||), as they behave differently when working with NULL values. Hint: You may notice that the same pet is owned by two different owners. Although uncommon, this is not necessarily an error.  <br><br>
```
SELECT CONCAT(owner_id, ', ', o.pet_id) AS owner_pet, visits_count
FROM owners AS o
LEFT OUTER JOIN visits AS v ON o.pet_id = v.pet_id
WHERE visits_count >= 3
UNION ALL
SELECT CONCAT(owner_id, ', ', o2.pet_id) AS owner_pet, visits_count
FROM owners_2 AS o2
LEFT OUTER JOIN visits AS v ON o2.pet_id = v.pet_id
WHERE visits_count >= 3
ORDER BY visits_count DESC, owner_pet;
```

8. Show the visit counts for each pet, and order the output from most to least visits. Include the owner_id, pet_id, and visits_count columns in your output.  <br><br>
```
SELECT owner_id, v.pet_id, visits_count
FROM visits AS v
LEFT OUTER JOIN owners AS o ON v.pet_id = o.pet_id
ORDER BY visits_count DESC;
```

9. Write a query that returns the owner_id, pet_id, date, and service for transactions that happened on June 17th, 2019, or for transactions where the service provided was a haircut. Order your results by date.  <br><br>
```
SELECT owner_id, t.pet_id, date, service
FROM transactions AS t
LEFT OUTER JOIN owners AS o ON t.pet_id = o.pet_id
WHERE date = '2019-06-17'
  OR service = 'haircut'
ORDER BY date;
```

10. You have a promotion where you'd like to give a gift to those pets who have had their nails done at the salon. Write a query that shows the pet_id and service for those pets that used the nails service from transactions. Then sort by those pets first who are receiving a gift. Hint: Use a CASE statement that assigns gift when the service is nails, and otherwise assigns no gift. End your CASE statement with the alias get_gift, and order by this field.  <br><br>
```
SELECT pet_id, service, 
CASE 
   WHEN service = 'nails' THEN 'gift'
   ELSE 'no gift'
END AS get_gift
FROM transactions
ORDER BY get_gift;
```

11. The town where the dog salon is located had a street fair on June 17 and 18. The business owner wants to know how many transactions took place on those days. Write a query that counts the number of transactions on '2019-06-17' and '2019-06-18' from the transactions table. <br><br> 
```
SELECT date, COUNT(transaction_id)
FROM transactions
WHERE date IN('2019-06-17', '2019-06-18')
GROUP BY date;
```

12. In this final challenge, you want to know how many dogs there are of each size, across both lists of owners. So, you'll want to combine the owners and owners_2 tables first, then get a count for each of the three sizes of dogs, small, medium, and large. Then sort the list from smallest to largest. Your final output should show the size and count. Hint: Use the alias all_owners to represent the union of both tables. Then, use the alias size_count to capture the count for each of the sizes.  <br><br>
```
WITH all_owners AS 
(
    SELECT *
    FROM owners
    UNION ALL
    SELECT *
    FROM owners_2
)
SELECT size, COUNT(size) AS size_count
FROM all_owners
GROUP BY size
ORDER BY size DESC;
```
