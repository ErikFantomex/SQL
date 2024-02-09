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


# SQL Query Problem

This SQL query retrieves the unique ID and name of employees from two tables: Employees and EmployeeUNI, employing a left join to ensure comprehensive selection.

## Intuition
The query combines data from Employees and EmployeeUNI tables. It utilizes a left join to fetch all employee records from the Employees table and corresponding entries from the EmployeeUNI table, defaulting to null for non-matching EmployeeUNI records.

## Approach
A left join is used, linking the ID columns of both tables. The join condition specified in the "ON" clause aligns the IDs, facilitating the retrieval of employee IDs and names across the two tables.

## Complexity
The query's complexity hinges on the tables' sizes and the match extent between them. While left joins can be intensive for large datasets, selecting only two columns may mitigate the computational demand. The complexity is deemed moderate, given reasonably sized tables and a fair match rate.

## Code
```sql
SELECT e.unique_id, e.name 
FROM Employees AS e
LEFT JOIN EmployeeUNI AS c ON e.id = c.id;
```
```
