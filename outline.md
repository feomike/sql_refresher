SQL Refresher
-------------

This document describes the refresher 'course' given about SQL.  It is purely a simple notes kind of approach.  I tend to want very simple SQL for speed of analysis.  This is not meant to be a course in database administration, or SQL or analysis, but a general idea of how I manage SQL for analytics.  The core group first given to was the erate team.

Dependencies
------------
The following are the set of dependencies I typically work with.  Again this is not an exhaustive list.
- a database.  in the erate team case we are using Oracle as an enterprise service.  I tend to use a local test environment on a local box.  I recommend Postgres because it is an open source software and easy to install.  I use the [community version of OpenGeo from the company Boundless Geospatial](http://boundlessgeo.com/solutions/opengeo-suite/download/) because it includes geospatial libraries for the database (also called PostGIS) with which we can perform spatial analysis.  It is the same version of Postgres we run in enterprise IT.
- a SQL client.  Oracle SQL is being loaded on each of your machines from IT.  I tend to use PG SQL, which comes with the above mentioned OpenGeo Suite.  I just do this because it is part of one suite I use all the time, so it is an easy button.
- data. tables need to be loaded into the database.  i will go through this with you a little
- imagination.  you need to want to investigate the data 

Step 1: Setup - anatomy of a SQL client
- the database has to be running.  these databases are enterprise class, so they typically need a server to run.  In the Postgres version from Boundless, it will run in the background, and will continue to run until you turn the machine off.  When you turn it back on you will need to restart the database server.  
- I will not cover tablespaces, groups and roles
- databases have schema's, tables, views, index's 
- schema's are containers to logically group tables

Step 2: Getting Data In/Getting Data Out

Step 3: SQL Statements Outline

Step 4: First Investigation Approach

Step 5: Indexes

Step 6: Joins

Step 6: Resources
