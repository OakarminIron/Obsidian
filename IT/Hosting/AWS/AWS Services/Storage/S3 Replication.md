- Source and Destination Versioning On ထားရမယ်
- Bucket can be in different accounts
- One-way replication
- No Glacier , Glacier Deep Archive
- Update file ကိုပဲကူးသွားတာ ထပ်လိုချင်ရင် Batch Job  Run ပေးရတယ်

- Cross-Region Replication (CRR) -->Use cases : compliance, lower latency access, replication across accounts
- Same-Region Replication (SRR)  -->Log aggregation, live replication between prod and test accounts

S3 Replication Options
• All objects or a subset
• Storage Class – default is to maintain
• Ownership – default is the source account
• Replication Time Control (RTC)
S3 Replication Considerations
• Must be enable versioning on both source and destination
• Bucket can be in different accounts
• One-way replication source to destination (not a bi-directional replication)
• Source bucket owner needs permissions to objects
• NO Glacier or Glacier Deep Archive