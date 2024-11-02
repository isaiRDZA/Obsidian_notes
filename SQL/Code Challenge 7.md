The `math_students` and `english_students` tables have the following columns:
- `student_id` - the student id
- `grade` - the grade level of the student
- `first_name` - the student's last name

## Instructions 

1. Using a subquery, get all students in math who are also enrolled in english.

```sql
select student_id, grade, first_name, last_name
from(
select *
from math_students as m
join english_students as e
on m.student_id = e.student_id) sub;
```
The selected SQL code is attempting to retrieve `student_id`, `grade`, `first_name`, and `last_name` from a temporary table called `sub`. This temporary table is formed by joining `math_students` and `english_students` where their `student_id`s match.

2. Using a subquery, find out which students in math are int eh same ` grade` level as the student with id `7`

```sql
select m.student_id, m.grade, m.first_name, m.last_name
from math_students as m
join (
select grade
from math_students
where student_id = 7) sub
on m.grade = sub.grade;
```
1. **Subquery**: The subquery finds the grade level of a specific student with a given ID.
2. **Main Query**: The main query retrieves details of all students from the math class who are in the same grade as the student identified in the subquery.
3. **Join Operation**: The main query uses a join to match students based on the grade level obtained from the subquery, ensuring only those in the same grade are selected.