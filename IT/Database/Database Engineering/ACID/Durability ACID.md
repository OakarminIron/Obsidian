Durability guarantees that once a transaction has been committed, it will remain committed even in the case of a system failure (e.g., power outage or crash). 
This usually means that completed transactions (or their effects) are recorded in non-volatile memory.
This ensures that data is not lost.

[[DB WAL]]

- Journaling: Journaling is a technique similar to `WAL` but implemented differently. It involves recording changes to the database in a separate journal or log file before updating the actual data. The journal file is written sequentially and ensures that changes can be replayed in case of a failure.

- Shadow Paging: Shadow paging is a technique used in some databases where the entire database is duplicated or "shadowed" in another location. Changes are made to the shadow copy, and once a transaction is committed, the shadow copy becomes the new main copy. This method provides durability by always having a consistent copy of the data available.

- Logging to Multiple Locations: Some databases write transaction logs to multiple locations or devices to ensure redundancy and durability. This approach protects against hardware failures or data corruption in a single location.

- [[Backup & Restore]]: Regular database backups are taken and stored in separate locations. While not a real-time durability technique, backups ensure that data can be restored to a consistent state after a failure.

- [[DB Replication]]: In distributed database systems, data can be replicated across multiple nodes. Changes are applied to multiple copies of the data, and a quorum or consensus algorithm is used to ensure that changes are committed only when a majority of copies acknowledge them. This replication provides durability in the face of node failures.
	- Replication and Fail-over: Some databases employ replication and fail-over mechanisms to ensure high availability and durability. In case of a failure in one database server, traffic is automatically redirected to a standby server with replicated data.

- Storage Redundancy: Many database systems run on storage systems that provide redundancy, such as RAID (Redundant Array of Independent Disks). These systems use techniques like mirroring and parity to ensure data durability even when individual disks fail.

- Checksum and Data Verification: Databases may use checksum or cryptographic hashes to verify the integrity of data and logs. This helps detect corruption and ensures that data remains durable.



