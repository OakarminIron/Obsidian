The `WAL` is a log file that records changes (inserts, updates, deletes) made to the database before they are applied to the actual data pages. 
When a transaction makes changes to the database, these changes are first written to the `WAL`. 
Once the changes are safely stored in the WAL, the transaction is considered committed.
Co-work with [[Dirty Pages]]
