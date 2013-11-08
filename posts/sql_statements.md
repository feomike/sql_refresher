Basics of SQL Statements
------------------------
SQL is very very basic.  You have one verb (generally) ***SELECT****.  You ***SELECT**** ***fields*** from a ***table*** with certain ***conditions*** then ***order*** the output rows.  So lets say you want to select all the schools, addresses,  from a table that has all schools but you only want the ones that have more than 1000 students.

This statement would look like the following:

```javascript
select leaid, schno, schnam, type, status, ulocal, member
	from sbi2012dec.nces
	where member > 1000
	order by member desc
```

Tips:
- You will likely always need to use the `<schema>.<table>` nomenclature
- Some SQL Clients allow you to drag and drop fields from the `browser` to the SQL Editor.  This is super helpful, because SQL will throw errors if you do not spell table names exactly as they are defined.  NOTE: Fields are often not intuitively named, OR they are very explicitly named resulting in long names.  
- You can have as many `column` names as you want.  You can rename columns on output with the `as` statement.  You can also select all fields with the `*` instead of explicitly saying every field.
- You can format text to appear the way you want in the results.  This is helpful in viewing large numbers, percents, money, etc.  For explicit formatting see [format examples for your favorite database](http://www.postgresql.org/docs/8.3/static/functions-formatting.html).
- You can perform math on numbers in the select statement, by simply including the field names in parenthesis with the mathematical operation like this `(white / member) as pct_whie`.  This code will result in the decimal of white students with a column named pct_white.
- You can limit the number of rows with the `LIMIT` statement.  
- You can have as many `WHERE` statements as you want.  You need to think about ***OR*** and ***AND*** statements.  Using parenthesis will help you refine your sets.
- I ALWAYS START SMALL AND BUILD BIGGER.
