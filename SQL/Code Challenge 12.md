The `weather` table has the following columns:
- `id` - the id of each entry
- `date` - the date of each entry
- `high` - the high temperature of the date, in Fahrenheit
- `low` - the low temperature of the date, in Fahrenheit

1. Utilize `CAST` to calculate the average of the `low` and  `high` temperatures for each `date` such that the result is of type `REAL`. Select ehte `date` column and alias this result column as 'average'.

```sql
select date, (cast(high as real) +
        cast(low as real)) / 2.0 as 'average'

from weather
```
