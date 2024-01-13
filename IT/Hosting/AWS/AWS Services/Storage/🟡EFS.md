Elestic File Store
Automatically grows and shrinks as you add and remove files with no need for management or provisioning.

• EFS scale 1000s of concurrent NFS clients, 10GB+/s throughput Grow to petabytes-scale network file system, automatically
• Performance mode (set at `EFS` creation time) General purpose (default): latency-sensitive use cases Max I/O - higher latency, throughput, highly parallel (big data, media processing)
• Throughput mode Bursting ( `1TB` = 50 `MiB/s` + burst of up to `100MiB`/s) Provisioned : set your throughput regardless of storage size


EFS – Storage Class
	• Standard : for frequently accessed files
	• Infrequent access (EFS-IA): cost to retrieve files, lower price to store. Enable
EFS-IA with a Life cycle Policy
	• Storage Tiers (life cycle management feature – move file after x Days)
	• Availability and durability
	• Regional: Multi-AZ, great for production
	• One Zone : one AZ, great for dev, uat. Backup enabled by default,compatible with IA
![[EBS vs EFS.png]]
[[🟡EBS]]

