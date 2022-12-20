ACID is a set of properties that are used to ensure the integrity and consistency of data in a database. The acronym ACID stands for Atomicity, Consistency, Isolation, and Durability.

[[Atomicity ACID]]  meaning that it is either completed in its entirety or not at all. This ensures that if a transaction fails,  rolled back, and the database remains in a consistent state.

[[Consistency ACID]] refers to the idea that a transaction must leave the database in a consistent state, meaning that it must adhere to all defined rules and constraints. For example, if a transaction is trying to add a new record to a database table, the transaction must ensure that the new record meets all of the table's defined rules and constraints.

[[Isolation ACID]] refers to the idea that multiple transactions occurring concurrently must be isolated from one another. This ensures that the results of one transaction do not affect the results of another transaction.

[[Durability ACID]] refers to the idea that once a transaction has been committed, it will remain permanent, even if the system crashes or experiences some other failure. This ensures that data is not lost and that the database remains consistent even in the case of system failures like crashes or power outages.

Together, these properties ensure that data in a database is accurate, consistent, and protected from corruption or loss. They are an important part of database engineering and are used to ensure the reliability and integrity of data in a database.
