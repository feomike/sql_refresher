First Investigation Approach
----------------------------
I ***ALWAYS*** repeat the following process with new data:
- Import the data, save the import script to .sql file.  [See Getting Data In/Getting Data Out](https://github.com/feomike/sql_refresher/blob/master/posts/data_in_data_out.md)
- Count the number of rows in the resulting table.

Use code like this to investigate:

```javascript
	select count(*) from sbi2012dec.nces;
```

- Check the source to make sure I expected that number of rows

- Look at how the fields are defined (which ones are characters, which ones are numeric, which ones are dates etc).  Do they make sense?  Why/Why not?

- Examine the variation in each field.
Use code like this to investigate character fields:

```javascript
	select type, count(*) 
		from sbi2012dec.nces
		group by type
		order by type;
```

Use code like this to investigate numeric fields;

```javascript
select max(member) as max, min(member) as min, avg(member) as average
  from sbi2012dec.nces
```javascript

For a complete list of aggregate numeric functions, see [your favorite database help section](http://www.postgresql.org/docs/8.2/static/functions-aggregate.html).

- Examine variation in groups of fields.
Use code like this to investigate groups:
```javascript
	select type, ulocal, status, level, count(*), sum(member) as total_students 
		from sbi2012dec.nces
		group by type, ulocal, status, level
		order by type;
```

Character fields in the select statement need to also be in the group statement.  You can add as many aggregate numeric fields as you want as well.  Above I am summing the number of students in this table.
