Cheap storage , [[Object Storage]]

Default (Standard Class) မှာသိမ်းတယ် , အနဲဆုံးတစ်လထားပြီးမှ တစ်ခြား Class ကိုပြောင်းလို့ရတယ် စရိတ်အရမ်းနဲလို့ . 
- Standard 
- Standard IA
- Glacier 
စသည်ဖြင့် Life-cycle အရ class ကိုလျော့လိုရတယ် Hot file to Cool file 

• Amazon S3 allows people to store objects in "buckets"
• Buckets must have a globally unique name (across all regions all accounts)
• Buckets are defined at the region level
• S3 looks like a global service but buckets are created in a region
• S3 is private by default
• Bucket can't be encrypt but object can on service side (SSE-C) or client side (SSE-S3)
![[S3 Encryption.png]]

Amazon S3 overview – Objects
• Objects (files) have a key
• The key is the full path: eg. S3://my-bucket/myfile.txt
• The key is composed of prefix + object name . Eg: s3://mybucket/myfolder/myfile.txt
• There is no concept of "directories" within buckets
• Just keys with very long names that contain slashes ("/")
• Object versioning 

[[S3 Replication]]
[[S3 Sync]]

[[S3 Websites]]
• S3 can host static websites and have them accessible on the www
• If you get a 403 (Forbidden) error, make sure the bucket policy allows public reads.

[[S3 Access Logs]]
• For audit purpose, may you want to log all access to S3 buckets
• Any request made to S3, from any account, authorized, or denied will log to S3 bucket
• That data can be analyzed using data analysis tools
Log format link:
https://docs.aws.amazon.com/AmazonS3/latest/userguide/LogFormat.html