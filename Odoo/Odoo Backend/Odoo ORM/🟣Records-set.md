
A Record-set is a set of records of the same Model. It can be a single record or collection of records. 
Record-sets are immutable, but sets of the same model can be combined using various set operations, returning new record-sets. Set operations do not preserve order.
-   `record in set` returns whether `record` (which must be a 1-element record-set) is present in `set`. `record not in set` is the inverse operation    
-   `set1 <= set2` and `set1 < set2` return whether `set1` is a subset of `set2` (resp. strict)    
-   `set1 >= set2` and `set1 > set2` return whether `set1` is a super-set of `set2` (resp. strict)    
-   `set1 | set2` returns the union of the two record-sets, a new record-set containing all records present in either source    
-   `set1 & set2` returns the intersection of two record-sets, a new record-set containing only records present in both sources    
-   `set1 - set2` returns a new record-set containing only records of `set1` which are _not_ in `set2`
- 
Record-set and its operations.

We can use decorators like ‘@one’, ‘@multi’ etc to control the records in a record-set. Odoo allows manipulating data in a record-set using different built-in methods. These functions return the filtered values of the current record-set. Major operations are :

1. [[🟣filtered()]]
2. [[🟣sorted()]]
3. [[🟣mapped()]]


 [[🟣Record Cache]]

