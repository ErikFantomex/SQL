# Problem Statement

Write a solution to find the ids of products that are both low fat (`low_fats = 'Y'`) and recyclable (`recyclable = 'Y'`).

Return the result table in any order.

# Intuition

To solve this problem, we can use a straightforward SQL query to filter the `Products` table for products that meet both desired conditions: being low in fats and being recyclable.

# Approach

1. Select the `product_id` from the `Products` table.
2. Apply a `WHERE` clause to only include products where `low_fats = 'Y'` and `recyclable = 'Y'`.

# Complexity

- Time complexity: Generally expected to be O(n), where n is the number of rows in the table, depending on the database management system's implementation.
- Space complexity: O(m), where m is the number of products that meet the criteria, as it determines the size of the output.

# Code

```sql
SELECT product_id
FROM Products
WHERE low_fats = 'Y' AND recyclable = 'Y';
```
```
