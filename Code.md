The below are the question can be raised by the given dataset

## Customer Behaviour and Demographics

1._What is the average spend per customer by gender_?
```sql
SELECT 
  CASE 
    WHEN age BETWEEN 18 AND 24 THEN '18-24'
    WHEN age BETWEEN 25 AND 34 THEN '25-34'
    WHEN age BETWEEN 35 AND 44 THEN '35-44'
    WHEN age BETWEEN 45 AND 54 THEN '45-54'
    ELSE '55+'
  END AS age_group,
  SUM(total_spend) AS total_spending
FROM customers
GROUP BY age_group
ORDER BY total_spending DESC;
```

2._Which age group has the highest total spending_?

```sql
SELECT 
  city,
  SUM(total_spend) AS total_spending
FROM customers
GROUP BY city
ORDER BY total_spending DESC;
```

3._How does spending vary across cities_?

```sql
SELECT 
  membership_type,
  COUNT(*) AS total_customers
FROM customers
GROUP BY membership_type
ORDER BY total_customers DESC;
```

4._What is the distribution of membership types among customers_?
```sql
SELECT 
  city,
  COUNT(*) AS satisfied_customers
FROM customers
WHERE satisfaction_level = 'Satisfied'
GROUP BY city
ORDER BY satisfied_customers DESC;
```
5._Which city has the highest number of high-satisfaction (Satisfied) customers_?
```sql
SELECT 
  discount_applied,
  SUM(total_spend) AS total_revenue
FROM customers
GROUP BY discount_applied;
```
