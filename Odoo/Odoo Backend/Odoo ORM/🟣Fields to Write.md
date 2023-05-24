Create the record , compute and update 

Goals to minimize update quaries
Stores column values
Accessible on the environment
The idea the group update by update. Reasonable minimum.
Depends on the current transaction ,, 

{{model_name: {record_id:{field_name:value}}}}
write() collects update until
flush() make actual database updates
	at most 1 update per record

flush () is automatically called by method like search(), read() and others
its important when use custom queries not forget to flush to database








Here to note that database itself does not update to actual heap it still store in [[DB WAL]] file to reduce the IO transaction.