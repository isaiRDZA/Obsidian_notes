 So far we've learned how to retrieve information from tables and perform calculations on them. But we've seen that GROUP BY and SUM reduce the number of rows in your query results because they are combining or grouping roes.
Window functions, on the other hand allow you to maintain the values of your original table while displaying grouped or summative information alongside in another column. This is why many Data Scientist and Data Engineers  love to use window functions for complex data analysis.
So we have these two querys let's see how their results differ:
The first one is using the SUM and GROUP BYU instructions:
```sql
select username, sum(change_in_followers)
from social media
wher username = 'instagram'
group by username;
```
Result:

| username  | sum(change_in_followers) |
| --------- | ------------------------ |
| instagram | 38.17                    |
The second query is using a window function:
 ```sql
 SELECT
	 mont,
	 change_in_followes,
	 SUM(change_in_followers) OVER(
		 ORDER BY month
	 ) AS 'running_total'
FROM
	social_media
WHERE
	username = 'instagram'
	limit 10;
```

| month | change_in_followers | running_total |
| ----- | ------------------- | ------------- |
| 1     | 6.27                | 6.27          |
| 2     | 4.71                | 10.98         |
| 3     | 5.73                | 16.71         |
| 4     | 5.43                | 22.14         |
| 5     | 4.99                | 27.13         |
| 6     | 2.52                | 29.65         |
| 7     | 4.61                | 34.26         |
| 8     | 3.91                | 38.17         |

Sure! Let's break down this SQL query line by line:

```sql
SELECT
    month,
    change_in_followers,
    SUM(change_in_followers) OVER(
        ORDER BY month
    ) AS 'running_total'
```
- `SELECT`: This clause is used to specify the columns that you want to retrieve from the database.
- `month`: Specifies the column `month` that will be selected and included in the result set.
- `change_in_followers`: Specifies the column `change_in_followers` that will be selected and included in the result set.
- `SUM(change_in_followers) OVER(ORDER BY month) AS 'running_total'`: This part creates a running total of `change_in_followers` ordered by `month`. The `SUM(...) OVER(...)` clause is a window function that calculates a cumulative sum (`SUM`) over a specified ordering of rows (`ORDER BY month`). The result of this calculation is given the alias `running_total`.

```sql
FROM
    social_media
```
- `FROM social_media`: This clause specifies the table `social_media` from which to retrieve the data that is being selected.

```sql
WHERE
    username = 'instagram'
```
- `WHERE username = 'instagram'`: This clause filters the results to only include rows where the `username` column has the value `'instagram'`.

```sql
LIMIT 10;
```
- `LIMIT 10`: This clause limits the number of rows returned by the query to 10. That means the query will only return the first 10 rows that match the specified conditions.

The overall query can be summarized as follows:
- It selects the `month` and `change_in_followers` columns.
- It computes a running total of the `change_in_followers` column, ordered by `month`.
- It filters rows to only include those where the `username` is 'instagram'.
- Finally, it limits the result to the first 10 rows.
### Differences Explained

1. **Columns Selected:**
    
    - **Original Query:** Selects `month`, `change_in_followers`, and computes a running total of `change_in_followers` as `running_total`.
    - **New Query:** Selects `username` and computes the total sum of `change_in_followers` for that user.
2. **Aggregation:**
    
    - **Original Query:** Uses a window function (`SUM(change_in_followers) OVER (ORDER BY month)`) to compute a running total of the `change_in_followers` column over a sequence of months.
    - **New Query:** Uses the `SUM(change_in_followers)` function in conjunction with `GROUP BY` to compute the total sum of `change_in_followers` for the specified user (`instagram`).
3. **ORDER BY and GROUP BY:**
    
    - **Original Query:** Utilizes the `ORDER BY` clause within the window function to compute the running total ordered by `month`.
    - **New Query:** Uses the `GROUP BY` clause to aggregate results by `username`. There is no concept of ordering in the context of the `SUM` function here.
4. **Data Filtering:**
    
    - Both queries filter the data to only include rows where the `username` is `'instagram'` using the `WHERE` clause.
5. **Row Limitation:**
    
    - **Original Query:** Uses the `LIMIT 10` clause to limit the output to the first 10 rows after filtering and selecting the required data.
    - **New Query:** Does not use any `LIMIT` clause, meaning it will return all aggregated results for the filtered condition.

### Summary:

- The **original query** provides month-by-month information including a running total of followers change, limited to the first 10 rows, whereas the **new query** aggregates the data by calculating the total sum of followers change for the user `instagram`.
- The **original query** includes columns for month and individual month changes, while the **new query** only includes the username and the total aggregated change in followers without considering individual months.
- **Original Query’s** use of a window function allows for cumulative sums over a sequence, while **New Query’s** use of `GROUP BY` provides a simple aggregated sum per group (in this case, per username).
