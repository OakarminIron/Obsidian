Goals is to argumented database cache
Store field Values
Access on Environment

Prefatching 
	First Iteration
		- Look at the cache -> nothing
		- Fetch the field on record:
				Look up record._prefetch_ids for  missing values -> all ids
				if fields is a clomn, fetch all column
				invoke records._read(fields)
	Next Iterations:
		- Just look up the cache ->

Record Cache is a dictionary
{fiedl : {record_id: value}}

Has Challenge is the consistency
When things change it invalidate and update

Before Odoo 13 invildate the cache aggrasively  , after 13 mininize the invildate and just update the data to get better performance.