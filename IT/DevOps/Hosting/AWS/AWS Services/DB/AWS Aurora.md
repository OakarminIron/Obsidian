▪ Aurora is a proprietary technology from AWS (not open sourced)
▪ PostgreSQL and MySQL are both supported as Aurora DB
▪ Aurora is "AWS cloud optimized" and claims 5x performance improvement over MySQL on RDS, over 3x the performance of postgres on RDS
▪ Aurora Storage automatically grows in increments of 10GB, upt to 128 TB
▪ Aurora can have 15 replicas while MySQL has 5, and the replication process is faster
▪ Aurora costs more than RDS (20% more) - but is more efficient
▪ 6 copies of your data across 3 AZ
▪ One Aurora instance take writes (master)
▪ Automated failover for master in less than 30 seconds
▪ Master + up to 15 aurora read replicas
▪ Support for Cross Region Replication
▪ All SSD Based – high IOPS, Low latency
▪ Storage is billed based on what's used
▪ High water mark – billed for the most used
▪ Storage which is freed up can be re-used
▪ Replicas can be added and removed without requiring storage provisioning.
▪ No free-tier option
▪ Aurora doesn't support Micro Instances
▪ Compute – hourly charge, per second, 10 min minimum
▪ Storage – GB-month consumed, IO cost per request
▪ 100% DB size in backups are included
▪ Security Similar to RDS because use the same engines
▪ Encryption at rest using KMS
▪ Automated backups, snapshots and replicas are also encrypted
▪ You are responsible for protecting the instance with security groups
▪ You can't SSH



![[AWS Aurora.png]]