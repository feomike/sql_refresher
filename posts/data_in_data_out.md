Getting Data In/Getting Data Out
--------------------------------
Here we go over how to get data in to a table and how to get it out.

**Getting Data In to a Database**
- Set up a table
- Copy data into the table  

Use code like the following to create a new table:

```javascript 
 
      -- Table: analysis.caf1
      -- DROP TABLE analysis.caf1;
      CREATE TABLE analysis.caf1
        (
          geoid10 character varying(15),
          carrier character varying(200)
        )
          WITH (
          OIDS=FALSE
        );
      ALTER TABLE analysis.caf1
      OWNER TO postgres;
      -- Index: analysis.analysis_caf1_geoid10
      -- DROP INDEX analysis.analysis_caf1_geoid10;
      CREATE INDEX analysis_caf1_geoid10
        ON analysis.caf1
        USING btree
        (geoid10 COLLATE pg_catalog."default" );
```

- Copy data into the table from a file
Use code like the following to copy data:

```javascript
	copy analysis.caf1
		from '/users/feomike/downloads/caf1.csv'
		csv header delimiter '|';
```


**Getting Data Out of a Database**
- Copy data to a file
Use code like the following to copy data to a file:
```javascript
	copy analysis.caf1
		to '/users/feomike/downloads/caf1.csv'
		csv header delimiter '|';
```

- Or select the data to the output window and copy it w/ your mouse
Use code like the following:

`select * from analysis.caf1;`
