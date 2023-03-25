Common virtual machine

On Demand == short workload, predictable pricing, pay by second
EC2 Reserved Instances
	• Up to 72% discount compared to On-demand
	• You reserve a specific instance attributes (Instance type, region, tenancy, OS)
	• Reservation Period – 1 yr (+discount) or 3 yrs (+++discount)
	• Payment Options – No upfront, partial upfront, and all upfront
	• Reserved Instance's scope – Regional or Zone
	• Recommended for steady-state usage applications (think database)
	Convertible Reserved Instance
	• Can change the EC2 instance type, instance family, OS, scope and tenancy
	• Up to 66% discount
	• Offering Class : Standard / Convertible
EC2 Spot Instances
	• Can get a discount of up to 90% compared to On-demand
	• Instances that you can lose at any point of time if your max price is less than the 	current spot price
	• The MOST cost-efficient instances in AWS
	• Useful for workloads that are resilient to failure
	• Batch jobs, Data analysis, Image processing, any distributed workloads, workloads with flexible start and end time
	• NOT suitable for critical jobs or database

EC2 savings plans
	• Get a discount based on long-term usage (up to 72% - same as RIs)
	• Commit to a certain type of usage
	• Usage beyond EC2 savings plans is billed at the on-demand price
	• Locked to a specific instance family & AWS region
	• Flexible across: instance size, OS, tenancy


EC2 Dedicated Hosts
	• A physical server with EC2 instance capacity fully dedicated to your use
	• Allows you address compliance requirements and use your existing server bound software license (per-socket, per-core, per-VM license)
	• Purchasing Options:
	• On-demand – pay per second for active Dedicated host
	• Reserved – 1 or 3 years (no upfront, partial upfront, all upfront)
	• The MOST expensive option
	• Useful for software that have complicated licensing model (BYOL)
	• For companies that have strong regulatory or compliance needs
![[ec2 types.png]]

