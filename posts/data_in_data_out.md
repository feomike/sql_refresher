Getting Data In/Getting Data Out
--------------------------------
Here we go over how to get data in to a table and how to get it out.

**Getting Data In to a Database**
- Set up a Table.  Use code like the following to create a new table:
```-- Table: analysis.caf1
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
  (geoid10 COLLATE pg_catalog."default" );```
