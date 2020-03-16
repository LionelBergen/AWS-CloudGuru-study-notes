|Object             |Weighting|
|-------------------|---------|
|Cloud Concepts     |26%      |
|Security           |25%      |
|Technology         |33%      |
|Billing and Pricing|16%      |

About The exam
--------------

|90 minutes long|65 Questions (may change)|Multiple choice|Must get 700/1000|
|---------------|-------------------------|---------------|-----------------|

Services part of the exam
-------------------------
AWS Global Infrastructure
Compute
Storage
Databases
Security, Identity & Complicane
AWS Cost Management
~Migration & Transfer
~Network & Content Delivery

Things to know *(Take from exam tips, or mentioned 'remember this for the exam')*
---------------------------------------------------------------------------------

These 3 terms & the differences: Avilability Zone vs Edge location vs Region
How to choose a Region / choosing the right region
[Different support packages] (#support packages)
[3 ways of accessing the AWS platform] (#IAM)
What is a group? - Group policies etc. Policies consist of JSON
Test an S3 bucket is successful; You get will always get a HTTP 200 code response when sucessfully creating a bucket
How data consistency works for S3
S3 is (Object-based)[#object-based] I.e allows you to upload files.
Because S3 is object based, it's not suitable for an operating system (And understand why)
Files in S3 can be from 0 bytes to 5 TB
There is an unlimited storage
Files are stored in (Buckets)[#bucket]
S3 is a universal namespace. Names must be globally unique.
Regonize S3 names. Example: S3-eu-west-1.amazonaws.com/bucketname so eu-west-1 is the region, region will always be present
S3 read after write consistency for PUTS vs delete or update (new file is automatic, others are (eventual consistency)[#eventual consistency]
S3 is one of the few services that does not require region selection
Bucket names share a common name space, you cannot have the same bucket name as someone else
You view buckets globally, but you can have buckets in individual regions
You can change encryption, other properties of buckets/objects on the fly
Know the different ways to restrict bucket access; Bucket policies - applies accross the whole bucket, Object Policies applied to indiviudal files, IAM policies
You can use bucket policies to make enture S3 buckets public
You can use S3 to host static websites. Not dynamic websites, such as wordpress, Database etc.
S3 scales automatically to meet your demand. Many enterprises will put static websites on S3 when they think there will be a large number of reequests (e.g movie preview)
Know [CloudFront's 3 key terms](#CloudFront key terms)
Edge locations are NOT read only. You can write to them, such as putting an object to them
Objects are cached for the [TTL](#TTL). The TTL is always in seconds
You can clear cached objects, but you will be charged for doing so
EC2 Is a web service that provides Resizeable compute capacity in the cloud. It reduces the time rquired to obtain boot and new server instances to minutes
[4 pricing models of EC2](#EC2 Pricing Models)
With spot pricing, you will not be charged for partial usage if terminated by Amazon EC2. You will be charged the full hour however, if you terminate it yourself.
[EBS](#EBS) GP2, IO2, ST1, SC1
~[FIGHTDRMCPXZ](#EC2 Instance Types)
EC2 is a compute based service. It is Not serverless. It's a server!
Use a private key to connect to EC2
Security Groups are virtual firewalls in the cloud. You need to open ports to use them
Always design for failure. Have one EC2 isntance in each availability zone
You can interact with AWS in 3 days; Console, CLI, SDKS


Q: How would you create a notification for going over $1000? 
A: Create a 'BillingAlarm', which uses an [SNS Service] (#SNS) to email you when you go over $1000 in billing

Q: What is the root account?
A: It's the email address you used to setup the AWS account. see [IAM] (#IAM). Never give this password, instead create a new user for users to have access

Overview of amazon Web Services
-------------------------------

Six advantages of cloud computing: 



### Terms
### Phrases
### Key Terms
### Key Phrases
Terms
-----

[**Cloud Computing**](#Cloud-computing) - On-demand delivery of compute, database, storage applications and other IT resources.

### Cloud computing
**Cloud Computing** - On-demand delivery of compute, database, storage applications and other IT resources.
Think of it like renting a computer.

**Avantages:**

	1) Pay a variable expense instead of static. In other words **Pay for what you use**
	2) Benefit from massive economies of scale
		Amazon has the ability to produce massive computing power
	3) Stop guessing about capacity.
		Standard approaches, you may over purchase computing power or under purchase. With Cloud computing you can automatically scale
	4) Increase speed & Agility - 'serverless computing', increase speed e.g ram as needed
	5) No need to manage/maintaining data centers. Stop managing infrastructure
	6) Go global in minutes - Deploy your application everywhere very quickly

**Types Of Cloud Computing:**

### IAAS
### Infrastructure As A Service
	1) IAAS - Infrastructure As A Service
		Database, storage - Physical or vertual, the provider usually has no access to your server.
### PAAS
### Platform As A Service
	2) PAAS - Platform As A Service
		Hardware & Operating system. Soemone else worried about security, patching, updates etc
### SAAS
### Software As A Service
	3) Software As A Service (SAAS)
		Software. Example is GMAIL
		
### CDN
**CDN**
	Amazon's Content delivery Network
	
### TAM
**TAM***
	Technical Account Manager available to Enterprise users

### S3
**S3**
	Simple Storage Service - Providers developers & IT teams with durable highly-scalable object storage
	S3 is basically a safe place to put your flat files, such as videos, images, txt files. Flat files don't change, so not a database
	It is Object-based storage
	Data is spread across multiple places
	Files can be 0 bytes - 5 TB
	S3 is a universal namespace. Names must be globall unique Example S3 bucket url: 'https://s3-eu-west-1.amazonaws.com/buckname'
	[Also see Data consistenct for S3] (#S3-detail)
	
### IAM
**IAM**
	Identity Access Management. is it Global, Not per region
	3 ways of setting up user access: 
		Programmatic access - access key ID and secret access key for development tools
		Management console access - password
		Amazon SDK
		
### ETL
**ETL**
	Extract, Transform and Load. AWS Glue is an ETL service
	
### bucket
### S3-bucket
**Bucket / S3 Bucket**
	Files in the cloud. A bucket is really just a folder name

### Cross Region Replication
***Cross Region Replication*** - Replication in anohter region

### ARN
***ARN*** - Amazon Resource Network
	
### SNS
**SNS**
    Simple Notification Service E.G Billing Alarm
	
### Eventual Consistency
**Eventual Consistency** - Data is not updated right away, may take a bit of time. For Deleted & updates.

### IA
### S3-IA
**IA / S3 - IA** - Infrequently Accessed. Data that is accessed less frequently, but still needs rapid access

### 11 9's
**11 9's / 11x9** 0 99.999999999% E.G 99.99999999% durability garuntee. Very close to 100%.

### TTL
**TTL** - Time to live. In an edge location, this is how long the file is cached for, from the first time it was queried

### IOPS
**IOPS** - Input Ouput Per Second

### VPC
**VPC** - Virtual Private Cloud
	
	
Types of Cloud Computing Deployments:
	
	1) Public Cloud
		AWS, Azure, GCP
	2) Hybrid
		Mixture of public and private - E.g public website but employee data is private
	3) Private cloud (Or On Premise)
		You manage it in your datacenter openstack or VMware.
	

AWS Global Infrastructure
-------------------------
Helps customers achieve lower latency and higher throughput & Ensure data is only accessible in Regions you specify

**Terms**
Availability Zone - Datacenter or several data centres close together
Region - Geographical area consisting of 2 or more Availability Zones
Edge Location - caching location  E.G CDN, CloudFront etc






### S3-detail
S3
--

### S3 Data Consistency
**S3 Data Consistency**

If you write a new file, you can view it immedietly
If you update an existing file, you may get the older version. Changes to objects take a little bit of time to propagate
	Same for Deleting, you may view it after deleting it (**Eventual Consistency**)

**S3 Guaruntees**

S3 has 99.99% availability for the S3 platform
99.9% availability
99.999999999% durability (Remember 11 x 9s). In other words, you won't lose your files.

**S3 Features**
Tiered Storage Available
Lifecycle Management
Versioning
Encryption
Secure your data using Access Control Lists and Bucket Policies

**S3 Storage Classes**
	S3 standard - 99.99% availability, 99.999999999% durability
	S3 - IA (Infrequently Accessed) - For data that is accessed less frequently, but requires rapid access when needed. Lower fee than S3 but charged a retrieval fee
	S3 One Zone - IA - For where you want a lower cost option for IA data but not require multiple availability zone data resilience
	S3 Intelligent Tiering - Used to otpmize costs, uses ML to determine lowest cost / lowest accessed
	S3 Glacier - Data Archiving, very low cost. Configure retirveal time, from minutes to hours
	S3 Glacier Deep Achive - Lowest cost, where retrieval time of 12 hours is acceptable.

**S3 - Charges**
	Storage
	Requests
	Storage Maangement Pricing
	Data Transfer Pricing
	Transfer Acceleration - Enables fast, easy and secure transfers of files over long distances between users and an S3 bucket. Takes advantage of CloudFront's Edge Locations
	Cross Region Replication Pricing - E.g when uploading a file, Amazon will automatically replicate the file in the closest region bucket

### CloudFront
CloudFront
----------

A content Delivery Network (CDN). Deliverys web content, webpages based on a users geographical locations, the oriign of the webpage and content delivery server

Can be used to deliver entire website including dynamic, static, streeaming, interactive content using a global network of edge locations.

### CloudFront key terms
**Key terms**
Origin - Where the files are. Could be an S3 bucket, EC2 Instance, an Elastic Load Balancer, or a Route53
Edge Locations - The files can be cached here, users will first query the closest one, seeing if the file is there. If it's not there, it gets it from the origin. The user gets it too, the next user gets it from the edge location
	This is seperate to AWS Region / AZ
Distribution -  Name given the CDN which consists of a collection of Edge Locations

**Other Terms**
TTL - Time to live, how long the file is cached for at the edge location

**Types of distribution**
Web Distribution - Typically used for websites
RTMP - used for Media Streaming. Not commonly used, for Flash

### EC2
### Elastic Compute Cloud
EC2 / Elastic Compute Cloud
---------------------------

A virtual server/servers in the cloud. Reduces the time required to obtain and boot new server instances to minutes. Quickly scale capacity both up and down.

### EC2 Pricing Models
**EC2 Pricing Models**
On demand - Pay fixed rate, by the hour or by the second with no commitment
Reserved - PRovides you with a capacity reservation. Offers a discount based on commitment time. Contract terms are 1 year or 3 years
Spot - Bid a price you want to pay. Price moves around all the time. Can be used if appliocations have flexible start and end times. You lose servers if it falls below bid price
Dedicated Hosts - Physical EC2 server dedicated for your use. Can help you reduce costs by allowing you to use your existing server-bound software licenses.
	Can be purchased as a reservation for up to 70% off on-demand price.
	
**Use cases for EC2 pricing models**
On demand - Low cost and flexibility of EC2 without any up-front payment or long term commitment
	Applications with short term, spiky or unpredictable workloads that cannot be interrupted
	Applications being developed or tested on EC2 for the first time
Reserved pricing - Users able to make upfront payments to reduce their total computing costs even further
	Applications with steady state or predicable usages
	Applications that require reserved capcity
Dedicated Hosts - Fewer and fewer people use this, but if you must use a dedicated server E.G for licesing terms, you may need this option
	Regulatory requirements do not support multi-tenant virtualization
	Licensing which does not support multi-tenancy or cloud deployments
Spot Pricing - Applications that have flexible start & end times
	Applications that are only feasible at very low compute prices
	Users with urgent computing needs for large amounts of additional capacity

**Reserved Pricing types**
	Standard Pricing Instances - Up to 75% off on demand instances. The more you pay up front and the longer the contract, greater the discount
	~Convertible Reserved Instances - Up to 54% off on demand capability to change the attributes of the RI as long as the exchange results in the creation of Reserved Instances of equal or greater value
	Schedules reserved Instances - Available to launch within the time windows you reserve. Match capacity reservation to predicable recurring schedule. E.G fraction of a day, week or month
	
### EC2 Instance Types
~**EC2 Instance Types**

### EBS
EBS
---

Virtual disks in the cloud. Allows you to create storage volumes and attach them to Amazon EC2 instances. Once attached you create a file system, or attach an OS etc.

**Types of EBS**

*SSD*
General Purpose SSD (GP2) - Balances price and performance for a wide variety of workloads
Provisioned IOPS SSD (IO1) - Highest-performance SSD volume for mission-critical low-latency or high-throughput workloads. Example: High performance database
*Magnetic*
Throughput Optimized HDD (ST1) - Low cost HDD volume designed for frequently accessed, thoughput-intensive workloads
COLD HHD (SC1) - Lowest-code HHD Volume designed for less frequently accessed workload (File servers)
~Magnetic - Previous Generation





AWS Security
------------

Benefits of AWS Security
	Keep Your data safe
	Meet Compliance Requirements
	Save Money
	Scale Quickly


How to choose a Region / choosing the right region / Why choose particular
--------------------------------------------------------------------------
**Data sovereignty Laws** - E.G data can only reside in a particular country
**Latency to end users** - Where the customers are located
**AWS Services** - Amazon may have more services in particular regions


### support packages
Different support packages
--------------------------
Basic - Access to fourms
	FREE
Developer - Support within 12-24 hour response time though Support Center during local business hours 
	Use Case: Experiments with AWS
	$29/month
Business - 24x7 support by phone and chat 1-hour response to urgent support cases 
	Use Case: Production use of AWS
	$100/month
Enterprise - TAM Technical Account Manager, 15 minute reponse time to urgent support cases
	Use Case: Mission-critical use of AWS
	$15,000/month




	
	
