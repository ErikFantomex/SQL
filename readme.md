```markdown
# Problem Statement

Given a table `Products` with the following structure:

```
+-------------+---------+
| Column Name | Type    |
+-------------+---------+
| product_id  | int     |
| low_fats    | enum    |
| recyclable  | enum    |
+-------------+---------+
```

- `product_id` is the primary key for this table, indicating unique product identifiers.
- `low_fats` is an ENUM of type ('Y', 'N'), where 'Y' means the product is low fat and 'N' means it is not.
- `recyclable` is an ENUM of types ('Y', 'N'), where 'Y' means the product is recyclable and 'N' means it is not.

The task is to write a solution to find the ids of products that are both low fat (`low_fats = 'Y'`) and recyclable (`recyclable = 'Y'`).

Return the result table in any order.

## Example

### Input

Products table:

```
+-------------+----------+------------+
| product_id  | low_fats | recyclable |
+-------------+----------+------------+
| 0           | Y        | N          |
| 1           | Y        | Y          |
| 2           | N        | Y          |
| 3           | Y        | Y          |
| 4           | N        | N          |
+-------------+----------+------------+
```

### Output

```
+-------------+
| product_id  |
+-------------+
| 1           |
| 3           |
+-------------+
```

### Explanation

Only products 1 and 3 are both low fat and recyclable.

# Intuition

To solve this problem, a straightforward SQL query can be used to filter the `Products` table for products that meet both conditions: `low_fats = 'Y'` and `recyclable = 'Y'`.

# Approach

1. Select the `product_id` from the `Products` table.
2. Use a `WHERE` clause to filter for products where `low_fats = 'Y'` and `recyclable = 'Y'`.

# Complexity

- Time complexity: Dependent on the implementation of the database management system, generally expected to be O(n) where n is the number of rows in the table.
- Space complexity: O(m) where m is the number of products that meet the criteria, determining the size of the output.

# Code

```sql
SELECT product_id
FROM Products
WHERE low_fats = 'Y' AND recyclable = 'Y';
```
```
