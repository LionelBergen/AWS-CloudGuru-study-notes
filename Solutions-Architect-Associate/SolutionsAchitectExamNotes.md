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


Key terms
---------

### SNS Topic
SNS Topic - A way of emailing you when your bill goes over a certain amount. Inside CloudWatch


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
  
IAM
---
PCI DSS compliance (relates to Credit card transactions)  
IAM policies are made up of Documents. Documents are written in JSON  
IAM - new users have no permissions when first created  
new users are assigned access key ID and secret access keys when first created. These are not the same as passwords. It's only for programmatic access
