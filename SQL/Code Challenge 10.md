The `box_office` table has the following collumns:
- `id` - the id of each row.
- `title` - the title of the movie
- `week` - the week following the film's release
- `gross` - the gross for that week
- `to_date_gross` - the total gross of the movie up to each week

1. Write a query using a window function with [[ROW_NUMBER]] and `ORDER BY` to see where each row falls in the amount of `gross`.
2. 
```sql
select row_number()
      over(
        order by gross
      ) as 'row_num', title, week, gross
      from box_office
```
Let's break down the SQL query and its particularities:

1. **`select row_number() over(order by gross) as 'row_num'`**:
   - **`ROW_NUMBER()`**: This function assigns a unique sequential integer to each row in the result set.
   - **`OVER(order by gross)`**: This specifies that the row numbers should be assigned based on the order of the `gross` column, from smallest to largest.
   - **`as 'row_num'`**: This assigns an alias `row_num` to the result of the `ROW_NUMBER()` function for easier reference.

2. **`title, week, gross`**:
   - These columns are indeed explicitly included in the `SELECT` clause. They are listed after the `row_number()` function, which is why they appear in the result set. They provide additional context for each row number, showing the movie title, the week of release, and the gross earnings for that week.

3. **`from box_office`**:
   - This specifies the `box_office` table as the source of data for the query.

The query ranks each row in the `box_office` table based on the `gross` value, while also displaying the `title`, `week`, and `gross` for each row. These columns are included in the `SELECT` clause, which is why they appear in the output.

![[Pasted image 20241103131133.png]]
