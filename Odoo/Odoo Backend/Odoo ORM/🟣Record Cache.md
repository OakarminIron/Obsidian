To avoid reading one field on one record at a time, Odoo prefetches records and fields following some heuristics to get good performance.
Once a field must be read on a given record, the ORM actually reads that field on a larger record-set, and stores the returned values in cache for later use. The prefetched record-set is usually the record-set from which the record comes by iteration. Moreover, all simple stored fields (boolean, integer, float, char, text, date, date-time, selection, many2one) are fetched altogether; they correspond to the columns of the model’s table, and are fetched efficiently in the same query.

Goals is to argument-ed database cache
Store field Values
Access on Environment

Prefatching
	First Iteration
		- Look at the cache -> nothing
		- Fetch the field on record:
				Look up record._prefetch_ids for  missing values -> all ids
				if fields is a column, fetch all column
				invoke records._read(fields)
	Next Iterations:
		- Just look up the cache ->

Record Cache is a dictionary
{field : {record_id: value}}

Has Challenge is the consistency
When things change it invalidate and update

Before Odoo 13 invalidate the cache aggressively  , after 13 minimize the invalidate and just update the data to get better performance.
[[🐿Caching]]