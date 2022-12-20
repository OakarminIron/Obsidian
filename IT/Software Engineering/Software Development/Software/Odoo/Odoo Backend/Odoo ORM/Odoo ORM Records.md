
Recordset and its operations.

A Recordset is a set of records of the same Model. It can be a single record or collection of records. We can use decorators like ‘@one’, ‘@multi’ etc to control the records in a recordset. Odoo allows manipulating data in a recordset using different built-in methods. These functions return the filtered values of the current recordset. Major operations are :

1. filtered()

2. sorted()

3. mapped()

Cashing 

To avoid reading one field on one record at a time, Odoo _prefetches_ records and fields following some heuristics to get good pe
rformance. Once a field must be read on a given record, the ORM actually reads that field on a larger recordset, and stores the returned values in cache for later use. The prefetched recordset is usually the recordset from which the record comes by iteration. Moreover, all simple stored fields (boolean, integer, float, char, text, date, datetime, selection, many2one) are fetched altogether; they correspond to the columns of the model’s table, and are fetched efficiently in the same query.