Things to know *(Taken from exam tips, or mentioned 'remember this for the exam')*
----------------------------------------------------------------------------------

Know difference between AZ and Edge Location  

S3 is object based allows you to upload files. Not suitable for an OS or DB. That would be block-based storage  
0 byes to 5TB unlimited storage, files are stored in 'buckets'.  
HTTP 200 status code  
Can use MFA Delete.  
Know the fundamentals of S3 (Key, value, versionID metadata, subresources (ACLs, Torrent))  
Know the Read/write consistencies of S3  
Know the different storage clasees (standard, IA, One Zone IA, S3 Glacier, S3 Glacier Deep Archive, Intelligent Tiering)  
RSS/S3 RSS - think of S3 one zone IA. RSS is being phased out.  
Read the S3 FAQ's - https://aws.amazon.com/s3/faqs/  
Understand how to get the best value of S3 price wise. Intelligent tiering has a tiny monitoring cost per 1,000 objects. Avoid S3 standard

ACL VS Bucket policies - ACL can be down to the indiviudal objects (individual files). They are JSON. Bucket policy applies to the entire bucket.

Versioning in S3 stores deletes & writes to an object. Remember deleting the delete of an object to restore it  
great backup tool, integrates lifecycle rules  
MFA delete capability  
Once enabled, cannot be disabled. Only suspended

Lifecycle automates moving objects between different storage tiers  
Can be used in conjunction with versioning

Always enable multi-factor authentication on root account  
Paying account should be used for billing purposes only. Don't deploy resources into the paying account  
Enable/disable AWS services using SCP (Service Control Policies)

(Know the 3 different ways to share S3 buckts accross accounts)[#S3-Cross-Account-Access-3-ways]

Versioning must be enabled on both source and destination buckets  
Files in existing bukcets are NOT replicated automatically.  
All files after turning on replication will be replicated automatically  
Delete markets are not replicated. Deleted individual versions are not replicated.  
Know what Cross Region Replication is at a high level.

Know what S3 Transfer Acceleration is

Know what an Edge Location, Origin, Distribution is.  
Web Distribution - Typically used for Websites  
RTMP - Media streaming  
Edge locations are not just READ, you can write. Objectes are cahced for TTL. You can clear cached objects, but you will be charged.

Know what Snowball is  
It can Import to S3 & Export from S3.


Key terms
---------

### SNS Topic
SNS Topic - A way of emailing you when your bill goes over a certain amount. Inside CloudWatch

(SCP Service Control Policies)[#Service Control Policies]


S3
--
HTTP code 200 - returned when successful upload  
Key, value, versionID metadata, subresources (ACLs, Torrent)

**S3 features**  
Tiered Storage Available  
Lifecycle management  
Versioning  
Encryption  
MFA Delete  
Secure data using Access Control Lists and Bucket Policies

**S3 Storage Classes**
S3 standard  99.99% availbility.. 99.99999.. durability  
S3 IA (Infrequently Accessed) Lower cost, data that is accessed less often  
S3 One Zone IA  Even lower cost, but only one avilability zone. Data resilience  
S3 intelligent Tiering  Uses Machine Learning to determine the best storage class automatically  
S3 Glacier  
S3 Glacier Deep Archive  Lowest cost storage, retrieval time of 12 hours is acceptable

**S3 billed**  
  Storage  
  Requests  
  Storage Management Pricing (different tiers/classes)  
  Data Transfer Pricing  
  Transfger Acceleration  
  Cross region replicaiton
  
**Security & Encryption**  
You can log requests/access in another S3 bucket. Or even send the logs to another bucket in another account

**SSL/TLS** - Encryption in Transit is always achieved using this

**Encryption at Rest (Server Side) is achieved by**  
S3 Managed Keys - SSE-S3  
AWS Management Service, Managed Keys SSE-KMS  
Server Side Encryption with Customer PRovided Keys SSE-C  
Client Side Encryption (upload encrypted object)

**versioning**  
Stores all versions of an object (including all writes and even if you delete an object  
Greate backup tool  
Once eneabled, you cannot disable. Only disabled  
Integrated with Lifecycle rules  
Comes with MFA delete capability  
When uploading a newversion, the file is automatically made private again

### S3 Cross Account Access 3 ways
Use Bucket Policies & IAM (applies across the entire bucket). Programmatic Access Only.  
Using Bucketr ACLS & IAM (individual objects). Programmatic Access Only.  
Cross-account IAM Roles. Programatic AND Console access.

### S3 transfer Acceleration  
Transfer to Edge locations which use AWS network to transfer to the bucket
  
IAM
---
PCI DSS compliance (relates to Credit card transactions)  
IAM policies are made up of Documents. Documents are written in JSON  
IAM - new users have no permissions when first created  
new users are assigned access key ID and secret access keys when first created. These are not the same as passwords. It's only for programmatic access

AWS Organization & Consolidated Billing
---------------------------------------

### AWS Organizations  
Account management service enables you to consolidate multiple AWS accounts to centrally manage  
Best practice use Root account for Billing only.  
**OU** Organization Unit, consists of AWS accounts, and other OUs. Can apply Policies to them.  
Paying Account is independent. Cannot access resources of other accounts. All linked accounts are independent.

### Consolidated Billing  
**Advantages of Consolidated Billing** One bill per AWS account  
Easy to track charges and allocate costs  
Volume pricing discount

### Service Control Policy  
Applied to Organizational Units or Accounts. Used to restrict what the accounts can do

CloudFront
----------

A CDN (Content Delivery Network). Delivers webpages & other web content to a user  
An Origin is the origin of all the files CDN distribute. It can be S3 bucket, ec2 instance or route53 or load balancer  
Distribution - name given o the CDN which consists of a collection of edge Locations  

Snowball
--------  
Used to move large amounts of data in/out of S3. A snowball is a petabyte in size  
Snowball Edge is a Snowball, with compute power. So you can run Lambda functions for example on your data    
Snowmobile is a 45 foot container pulled by a semi truck, used to move Extrabytes? of data. Such as moving an entire data center







