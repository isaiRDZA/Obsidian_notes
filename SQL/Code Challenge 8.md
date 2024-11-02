The `math_students` and `english_students` tables have the following columns:
- `student_id` - the student id
- `grade` - the grade level of the student
- `first_name` - the student's last name

1. Using a subquery, fins all students enrolled in english class who are not also enrolled in math class


```sql
select *

from english_students

where student_id not in(

  select student_id

  from math_students

);
```

Let's break down the SQL query line by line:

1. **`select *`**: This selects all columns from the resulting dataset. The asterisk (`*`) is a wildcard that means "all columns."

2. **`from english_students`**: This specifies the `english_students` table as the source of data for the query.

3. **`where student_id not in (`**: This introduces a condition to filter the results. It checks that the `student_id` is [[not in]] the list of IDs returned by the subquery.

4. **Subquery**:
   - **`select student_id`**: This selects the `student_id` column.
   - **`from math_students`**: This specifies the `math_students` table as the source for the subquery.

The overall query finds all students in the `english_students` table who are not also enrolled in the `math_students` table by comparing their `student_id`s.
select grade

2. Using a subquery, find out what grade levels are represented in both the math and english classes.
```sql
from math_students

where exists

(

  select grade

  from english_students

);
```
Let’s break down the SQL query line by line:

1. **`from math_students`**: This specifies the `math_students` table as the source of data for the query.
    
2. [[where exists]]:  This introduces a condition that checks for the existence of any rows returned by the subquery. If the subquery returns any rows, the condition is true.
    
3. **Subquery**:
    
    - **`select grade`**: This selects the `grade` column.
    - **`from english_students`**: This specifies the `english_students` table as the source for the subquery.

The overall query checks if there are any grades in the `english_students` table. If there are, it returns all rows from the `math_students` table