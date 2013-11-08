Other Things I Like
--------------------

#Store Code
As a general rule, I will keep a SQL editor window ope adding bits of SQL statements to it over time until i get what I want.  I do this no matter how large or small the project, or how many times I have written the same code.  I continue to refine edit a generally linear process.  Then I will save that SQL file to a local directory (or [github](https://github.com/feomike)).  This approach ensures that I have my whole process in code.  This approach minimizes human introduced errors b/c the code is re-runable.

#Spatial Queries
- Creating Point Geometry from latitude and longitude.  Here is an example of creating a geometry column from latitude and longitude columns.

```javascript  
	drop table if exists bchs.airports;
	create table bchs.airports (id serial,geom geometry);
	INSERT into bchs.airports (geom) values (geomfromtext('Point(-71.1217787  41.7154923 0)',4326));
	INSERT into bchs.airports (geom) values (geomfromtext('Point(-70.9457635  43.1369197 0)',4326));
```

- Selecting based on Geometry
Here is an example of selecting things from one table where the locations intersect some geometry features in another table.

```javascript  
select geom from table where ST_Intersects(geom, (select geom from othe_table where source_id = '123'))
```


#Using Python w/ SQL
- Make a connection
I often use python to write SQL.  This approach can get very complicated (see below) but also be very simple.  I use the [psycopg2 library](http://initd.org/psycopg/) to do this with postgres.  The basic setup is below, and is very easy to implement.  The [pysycopg2 help on cursors is also very good](http://initd.org/psycopg/docs/cursor.html) and useful.


```javascript  

	import psycopg2
	#global variables - database connection
	myHost = "localhost"
	myPort = "54321"
	myUser = "postgres"
	db = "feomike"
	schema = "mmba"
	myHex = "hex_75000"

	#create the connection string to postgre
	myConn = "dbname=" + db + " host=" + myHost + " port=" + myPort + " user=" + myUser
	conn = psycopg2.connect(myConn)
	cur = conn.cursor()

	val = 1
	while val < 10:
		mySQL = "INSERT INTO " + schema + ".tests VALUES (" 
	   	mySQL = mySQL + str(val) + "); Commit;"
		cur.execute(mySQL)
		val = val + 1
 		conn.commit()
	cur.close 
```




- Have Python loop/branch to write SQL
SQL does not really have branching and looping alternatives.  So when necessary, what I tend to do is write python which writes SQL based on a loop or a branch.  A complicated scheme for this is found in the [FCC Low Power FM Analysis](https://github.com/FCC/lpfm/blob/master/processing/lpfm_setup.py) and the [FCC Measuring Mobile Broadband America Project](https://github.com/feomike/mmba_viz_processing/blob/master/processing/mmba.py)

