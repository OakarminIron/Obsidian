[[Odoo ORM Methods]]
[[Odoo ORM Method Decorators]]
[[Odoo ORM Records]]
[[Odoo ORM DataStructure]]



### Set operations[](https://www.odoo.com/documentation/12.0/developer/reference/orm.html#set-operations "Permalink to this headline")

Recordsets are immutable, but sets of the same model can be combined using various set operations, returning new recordsets. Set operations do _not_ preserve order.

-   `record in set` returns whether `record` (which must be a 1-element recordset) is present in `set`. `record not in set` is the inverse operation
    
-   `set1 <= set2` and `set1 < set2` return whether `set1` is a subset of `set2` (resp. strict)
    
-   `set1 >= set2` and `set1 > set2` return whether `set1` is a superset of `set2` (resp. strict)
    
-   `set1 | set2` returns the union of the two recordsets, a new recordset containing all records present in either source
    
-   `set1 & set2` returns the intersection of two recordsets, a new recordset containing only records present in both sources
    
-   `set1 - set2` returns a new recordset containing only records of `set1` which are _not_ in `set2`


