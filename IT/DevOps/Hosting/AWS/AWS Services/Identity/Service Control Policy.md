• Whitelist or blacklist IAM actions
• Applied at the OU or account level
• Does not apply to the Master account
• SCP is applied to all the users and roles of the account, including Root user
• SCP must have an explicit Allow (does not allow anything by default)


Use cases:
• Restrict access to certain services (for example: can't use S3)
• Enforce PCI compliance by explicitly disabling services




![[AWS SCP.png]]
![[SCP Hierarchy.png]]


[[Deny List]]  High Priority
[[Allow List]]
