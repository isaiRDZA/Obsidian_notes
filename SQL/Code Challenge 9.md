The `box_office` table has the following collumns:
- `id` - the id of each row.
- `title` - the title of the movie
- `week` - the week following the film's release
- `gross` - the gross for that week
- `to_date_gross` - the total gross of the movie up to each week

1. Using a window function with `PARTITION BY`, get the running total in `gross` for each movie up to the current `week` and display it next to the current `week` column along with the `title`, `week`, and `gross` columns.

```sql
select title,
        week,
        gross,
        sum(gross)        
        over(partition by title order by week) as running_total_gross
        from box_office
```
1. **`select title, week, gross,`**: This selects the columns `title`, `week`, and `gross` from the `box_office` table to be included in the result set.
    
2. **`sum(gross) over(partition by title order by week) as running_total_gross`**:
    
    - **`sum(gross)`**: This calculates the cumulative sum of the `gross` column.
    - **`over(partition by title order by week)`**: This specifies a [[Window function]]. It partitions the data by `title` and orders it by `week`, calculating the running total of `gross` for each movie.
    - **`as running_total_gross`**: This assigns an alias `running_total_gross` to the calculated running total for easier reference.
3. **`from box_office`**: This specifies the `box_office` table as the source of data for the query.
    

The query calculates a running total of weekly gross earnings for each movie, displaying it alongside the movie’s title, week, and weekly gross.
