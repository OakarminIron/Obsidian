To avoid reading one field on one record at a time, Odoo prefetches records and fields following some heuristics to get good performance.
Once a field must be read on a given record, the `ORM` actually reads that field on a larger record-set, and stores the returned values in cache for later use. 
The prefetched record-set is usually the record-set from which the record comes by iteration.
Moreover, all simple stored fields are fetched altogether; they correspond to the columns of the model’s table, and are fetched efficiently in the same query.

Goals is to argument-ed database cache
Store field Values
Access on Environment

Prefatching
	First Iteration
		- Look at the cache -> nothing
		- Fetch the field on record:
				Look up `record._prefetch_ids` for  missing values -> all ids
				if fields is a column, fetch all column
				invoke records._read(fields)
	Next Iterations:
		- Just look up the cache ->

Record Cache is a dictionary
{field : {record_id: value}}

Consider the following example, where `partners` is a record-set of 1000 records. 
Without prefetching, the loop would make 2000 queries to the database. With prefetching, only one query is made:
```python
for partner in partners:
    print partner.name          # first pass prefetches 'name' and 'lang'
                                # (and other fields) on all 'partners'
    print partner.lang
```

The prefetching also works on _secondary records_: when relational fields are read, their values (which are records) are subscribed for future prefetching. Accessing one of those secondary records prefetches all secondary records from the same model. This makes the following example generate only two queries, one for partners and one for countries:

```python
countries = set()
for partner in partners:
    country = partner.country_id        # first pass prefetches all partners
    countries.add(country.name)         # first pass prefetches all countries
```

Has Challenge is the consistency
When things change it invalidate and update

Before Odoo 13 invalidate the cache aggressively  , after 13 minimize the invalidate and just update the data to get better performance.
[[🐿Caching]]