The `ROW_NUMBER()` function in a window function assigns a unique sequential integer to rows within a partition of a result set. Here's how it works:

- **Assigns Numbers**: It starts at 1 for the first row in each partition and increments by 1 for each subsequent row.
- **Partitioning**: You can use the `PARTITION BY` clause to reset the row number for each partition (e.g., each movie title).
- **Ordering**: The `ORDER BY` clause within the window function determines the order in which the row numbers are assigned.

This is useful for tasks like ranking or identifying the position of a row within a group.
Here's an example of using `ROW_NUMBER()` in a SQL query:

```sql
SELECT 
  title, 
  gross, 
  ROW_NUMBER() OVER (ORDER BY gross DESC) AS rank
FROM 
  box_office;
```

In this example:
- The query selects the `title` and `gross` columns from the `box_office` table.
- `ROW_NUMBER()` assigns a unique rank to each row based on the `gross` value, ordered in descending order.
- The result includes a `rank` column showing the position of each movie based on its gross earnings.