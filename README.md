# goit-rdb-hw-03

Woolf University · Neoversity GoIT · Relational Database · Homework #3

## Homework Description

### 1) Select columns from tables

Write SQL queries to:
- select all columns (using wildcard `*`) from the `products` table;
- select only the `name` and `phone` columns from the `shippers` table.

**Solution:**

```sql
SELECT *
FROM products;

SELECT name, phone
FROM shippers;
```

### 2) Get average, maximum, and minimum price

Write an SQL query to find the average, maximum, and minimum values of the `price` column in the `products` table.

**Solution:**

```sql
SELECT
    AVG(price) AS average_price,
    MAX(price) AS max_price,
    MIN(price) AS min_price
FROM products;
```

### 3) Get unique `category_id` and `price` values

Write an SQL query to select unique combinations of `category_id` and `price` from the `products` table.

Display results sorted by `price` in descending order and return only 10 rows.

**Solution:**

```sql
SELECT DISTINCT category_id, price
FROM products
ORDER BY price DESC
LIMIT 10;
```

### 4) Count products in a price range

Write an SQL query to count the number of products with prices in the range from 20 to 100.

**Solution:**

```sql
SELECT COUNT(*) AS total_products
FROM products
WHERE price BETWEEN 20 AND 100;
```

### 5) Count products and average price per supplier

Write an SQL query to find the number of products and the average product price (`price`) for each supplier (`supplier_id`).

**Solution:**

```sql
SELECT
    supplier_id,
    COUNT(*) AS total_products,
    AVG(price) AS average_price
FROM products
GROUP BY supplier_id;
```