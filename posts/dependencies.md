Dependencies
------------
The following are the set of dependencies I typically work with.  Again this is not an exhaustive list.
- a database.  in this team's case we are using Oracle as an enterprise service.  I tend to use a local test environment on a local box.  I recommend Postgres because it is an open source software and easy to install.  I use the [community version of OpenGeo from the company Boundless Geospatial](http://boundlessgeo.com/solutions/opengeo-suite/download/) because it includes geospatial libraries for the database (also called PostGIS) with which we can perform spatial analysis.  It is the same version of Postgres we run in enterprise IT.
- a SQL client.  Oracle SQL is being loaded on each of your machines from IT.  I tend to use PG SQL, which comes with the above mentioned OpenGeo Suite.  I just do this because it is part of one suite I use all the time, so it is an easy button.
- data. tables need to be loaded into the database.  i will go through this with you a little
- imagination.  you need to want to investigate the data 

what to know about the data
---------------------------
- know the source;  where did you get the data.  store the url somehwere.  know the metadata.  keep every effort to keep the source data intact, and don't change it
- know the record counts of each table.  often (nearly always) this is the one key that lets you know which dataset you are dealing with.
- know what the definitaion of a row in a table is.  1 row is 1 school.  1 census block.  1 license.  1 thing by area by time etc.  knowing this simple information is critical to how you do analysis and therefor how you write SQL
