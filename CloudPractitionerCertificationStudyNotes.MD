# Cloud Practioner Certification Study Notes

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

|Importance:|***                          |***        |***        |***          |***                                |***                    |*                   |*                         |
|-----------|-----------------------------|-----------|-----------|-------------|-----------------------------------|-----------------------|--------------------|--------------------------|
|Topic:     |**AWS Global Infrastructure**|**Compute**|**Storage**|**Databases**|**Security, Identity & Compliance**|**AWS Cost Management**|Migration & Transfer|Network & Content Delivery|


Things to know *(Taken from exam tips, or mentioned 'remember this for the exam')*
---------------------------------------------------------------------------------

These 3 terms & the differences: Avilability Zone vs Edge location vs Region

How to choose a Region / choosing the right region

[Different support packages](#support-packages)

[3 ways of accessing the AWS platform](#IAM)

What is a group? - Group policies etc. Policies consist of JSON

How to test an S3 bucket is successful; You get will always get a HTTP 200 code response when sucessfully creating a bucket

[How data consistency works for S3](#S3-Data-Consistency)

S3 is [Object-based](#object-based) I.e allows you to upload files.  
Because S3 is object based, it's not suitable for an operating system (And understand why)  
Files in S3 can be from 0 bytes to 5 TB  
There is unlimited storage  
S3 is a universal namespace. Names must be globally unique.

Files are stored in [Buckets](#bucket)

Recognize S3 names. Example: `S3-eu-west-1.amazonaws.com/bucketname` so eu-west-1 is the region, region will always be present  
Bucket names share a common name space, you cannot have the same bucket name as someone else  
S3 read after write consistency for PUTS vs delete or update (new file is automatic, others are [eventual consistency](#eventual-consistency)  
S3 is one of the few services that does not require region selection  
You view buckets globally, but you can have buckets in individual regions

You can change encryption, other properties of buckets/objects on the fly  
Know the different ways to restrict bucket access; Bucket policies - applies accross the whole bucket, Object Policies applied to indiviudal files, IAM policies  
You can use bucket policies to make enture S3 buckets public  
You can use S3 to host static websites. Not dynamic websites, such as wordpress, Database etc.

S3 scales automatically to meet your demand. Many enterprises will put static websites on S3 when they think there will be a large number of reequests (e.g movie preview)

Know [CloudFront's 3 key terms](#CloudFront-key-terms)

Edge locations are NOT read only. You can write to them, such as putting an object to them  
Objects are cached for the [TTL](#TTL). The TTL is always in seconds  
You can clear cached objects, but you will be charged for doing so

EC2 Is a web service that provides Resizeable compute capacity in the cloud. It reduces the time rquired to obtain boot and new server instances to minutes  
[4 pricing models of EC2](#EC2-Pricing-Models)  
With spot pricing, you will not be charged for partial usage if terminated by Amazon EC2. You will be charged the full hour however, if you terminate it yourself.  

[EBS](#EBS) GP2, IO2, ST1, SC1  
[FIGHTDRMCPXZ](#EC2-Instance-Types)  
EC2 is a compute based service. It is Not serverless. It's a server!  
Use a private key to connect to EC2  
Always design for failure. Have one EC2 isntance in each availability zone

Security Groups are virtual firewalls in the cloud. You need to open ports to use them

You can interact with AWS in 3 ways; Console, CLI, SDKS

Load balancers come in 3 different flavours: Application Load Balancers, Network load balancers and Classic load balancers  
Application load balancers are layer 7, network is for extreme performance / static ip addresses and classic is for Tes&dev, keeping costs low. It's outdated  
When using load balancers, use multiple availability zones, incase one goes down

Business intelligence or data warehousing - go for Redshift

Speed up performnace of existing databases (frequent Identical queries) go for Elasticache

Route53 can be used to register domains. It is Amazon's DNS.

Know all the Compute services (Ex. select all the services that are under 'compute')

Know what ElasticBeanstalk is. Also configure an instance using it in the Sandbox for practice

Know what cloudformation is. Also configure for practice

ElsaticBeanstalk is limited in what it can provision and is not programmable. Cloudformation can provision almost any AWS service and is completly programmable.

Read the white paper the day before the exam: https://d1.awsstatic.com/whitepapers/AWS_Cloud_Best_Practices.pdf

Know [which services can be used on premise](#Which-AWS-Services-can-be-used-on-premise)

Cloudwatch is used for monitoring performance  
Cloudwatch can monitor most of AWS as applications un on AWS  
Cloudwatch with Ec2 will monitor events every 5 minutes by default  
Cloudwatch - You have 1 minute intervals by turning on detailed monitoring  
Cloudwatch is all about performance

Know the difference between cloud watch, cloud trail, aws inspector, aws trusted advisor.

Systems Manager can be used to manage fleets of EC2 instances & Virtual Machines
  - Can be both inside AWS and on premise. Run command is used to install, patch, uninstall software
  
Systems Manager integrates with CloudWatch to give you a dashboard of your entire estate

Know the 6 Advantages of Cloud

Know the 3 types of cloud computing (IASS, PAAS, SAAS)

Know the 3 types of computing deployments (public cloud, hybrid, private cloud)

Choosing the right AWS Region - Data soverignty laws, Latency to end users, AWS services needed

Read up on the different Route 53 policies: https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy.html

Cloudformation template sections: https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/template-anatomy.html

A CloudFront origin can be a Route53, EC2, S3 bucket

The collection of a CDN's Edge Locations is called a Distribution.

To restrict access to an entire bucket, you use bucket policies; and to restrict access to an individual object, you use access control lists.

Which are valid access types for an IAM user?

What is Lightsail?


Q: How would you create a notification for going over $1000? 
A: Create a 'BillingAlarm', which uses an [SNS Service] (#SNS) to email you when you go over $1000 in billing

Q: What is the root account?
A: It's the email address you used to setup the AWS account. see [IAM] (#IAM). Never give this password, instead create a new user for users to have access

Overview of amazon Web Services
-------------------------------

Six advantages of cloud computing: 
	Trade capital expense for Variable expense
	Benefit from massive economies of scale (Amazon can buy sevrers for chepear
	Stop guessing about capcity
	ioncrease speed and agility (start developing quickly)
	Stop spending money reunning and maintianing data centers
	Go global in minutes

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
**Identity Access Management**. is it Global, Not per region
	
**3 ways of setting up user access:**
- Programmatic access - access key ID and secret access key for development tools
- Management console access - password
- Amazon SDK
		
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

### OLTP
**OLTP** - Online Transaction Processing (see here)[#OLTP VS OLAP]

### OLAP
**OLAP** - Online Analytics Processing (see here)[#OLTP VS OLAP]

### Object based
**Object based** - consists of meta data
	
	
Types of Cloud Computing Deployments:
-------------------------------------
	
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
ES2 Fleet - A bunch of EC2 instances
EBS - Elastic Block Store






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
	Storage Management Pricing
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
	FPGA
	IOPS
	Graphics
	High Disk throughput
	T Cheap general purpose (think T2 micro)
	D Density
	R RAM
	M Main chocie for general purpose apps
	C Compute
	P Graphics (think pic)
	X Exteme Memory
	Z Exteme memory and CPU

### EBS
EBS (Elastic Block Store)
-------------------------

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

Databases 101
-------------
**RDS** (Amazon's Relational Database Service)
Supports Oracle, MySQL, PostgreSQL, MSSQL, MariaDB and Amazon's proprietary AuroraDB
Key features 
	Multi avaialbility zones for disaster recovery    
	Read replicas - for performance. Can have 5 copies. Writes goes to primary, reads to replicas
	
**Non-relational databases (NoSQL/JSON)**
	Collection = table, document = row key value pairs = columns/fields
	No structure, so rows have no affect on eachother.
	Amazon's NoSQL is DynamoDB
	
### OLTP VS OLAP
**OLTP vs OLAP**
	OLTP - OLTP e.g: Order number 2120121 opens up a row of data such as name, date, address etc
	OLAP - A lot more complicated, can be used by management to get costs for a region, taxes unit costs etc. Lots of queries. Data warehousing was built for this, so these things don't affect main database and servers. Tools such as SQL server reporting services, oracle hyperion, SAP NetWeaver
	*Redshift - Amazon's data warehousing solution*
	
**ElastiCache**  
	Caches commonly used database queries in the cloud. Takes a big load off production databases
	Supports tow open source in memory cahcing engines: Memcached, Redis
	



### Architecting for the cloud
Architecting for the cloud
--------------------------

**Traditional vs Cloud Computing**
	IT assets vs provisioned resources (Think CloudFormation, specifying resources based on a configuration)
	Global, Available, and Scaleable Capacity
	High Level Managed Services (E.g Machine learning. Products.)
	Build-in Security
	Architecting For Cost
	Operations on AWS

**Scalability**
	Scale up - E.g Adding more RAM 
	Scale out - E.G adding more VM's in an elastic load balancer. 
		Stateless applications
		Distribute load to multiple loads
		Stateless Components - E.G a user with cookies cachied. The user can interact as a stateless component
		Stateful Components - E.G storing the users data in a database
		Implement Session Affiinity - Sticky sessions
		Implement Distrubted Processing - E.g multiple EC2 instances working together for a single task

**Instantiating Compute Resources**
	Bootstrapping - Configure instances using a script
	Golden images - Image of EC2 instance.
	Containers
	
**Infrastructure As Code**
	CloudFormation
	
**Serverless Management and Deployment**

**Infrastructure Management And Deployment**
	AWS Elasstic Beanstalk
	Amazon EC2 auto recovery
	AWS Systems Manager
	Auto Scaling
	
**Alarms and Events**
	Amazon CloudWatch Alarms
	Amazon Cloudwatch Events - E.g adding a watermark via lambda function when an image is uploaded
	AWS Lambda scheduled events - E.g run lambda function everyday at midnight
	AWS WAF security automations - E.G respond automatically to SQL injection or XSS

**Loose Coupling**
	Using the IP address of an EC2 instance or database would be tightly coupled. It's better to use the DNS name and have the EC2/database attached to a load balancer
	Queue's are also a way to reduce coupling (SQS)
	
**Distributed Systems Best Practices**
	Graceful Failure in Practice - E.G error.html instead of default errors
	
**Services Not Servers**
	Managed Services
	Serverless Architectures

**Relational Databases (Aurora)**
	Scalability
	High availability - multi AZ
	Anti patterns - If you don't have a need for joins or complex trasnsacitons, use No-SQL instead

**Non-relational databses (DynamoDB)**
	Scalability
	High availability - multi AZ
	Anti patterns - If you need joins or complex trasnsacitons, use relational database instead (Aurora)
		If you have alrge binary files (audo, video images) consider storing them in S3
		
**Data Warehouse (Redshift)**
	Scalability
	high avaialbility - multi AZ
	Anti patterns - not meant for online transaction process (OLTP). It's more for large queries such as reports, to take stress away from production DB
	
**Database Search**
	Scalability
	High avaialbility
	
**Graph Databases**
	Scalability
	High availability
	Amazon Neptune is amazon's graph database

**Managing Increasing Volumes of Data (DataLake)**
	A Data Lake is an architectural approach that allows storagae of massiver amoutns if data in a central location ready to be categorized, processed naalyzed
	Data can be stored as-is, no need to convert to a prdefined data and no need to know which questiosn to ask the data beforehand (No schemas / rules)
	S3 is a good place to store data for a data lake

**Remove single points of failure**
	Introducing Redundancy
	detect failure
	durable Data Storage
	Automate multi=data centre resiliance (E.g if one region goes down, automatically switches to another)
	Fault isolation
	Sharding - Split data across multiple shards for speed
	
**Optimize for cost**
	Right sizing
	Elasticity
	Take Advantage of the Variety of Purchasing options (spot, reserved)
	
**Caching**
	Application cache
	edge caching - cloudfront

**Security**
	use AWS features for defence in depth
	Shared security responsibility in the cloud
	Reduce Privileged Accesss
	Security as Code
	Real-Time Auditing

Global AWS Services
-------------------

**Which AWS Services are Global?**
	IAM
	Route53
	CloudFront
	SNS
	SES
	
**Global views but are reigional**
	S3
	
### Which AWS Services can be used on premise
Which AWS Services can be used on premise
-----------------------------------------

	Snowball - Basically a gigantic disc. Amazon's send it to you and after outting all your data on ship it back to Amazon. 
		80TB in size
	Snowball Edge - Same as Snowball, but is also a computer. You can run lambdas functions with it
		When you cant get AWS connectivity, but need AWS resources.
	Storage gateway - Like snowball but Stays on Premise at all times. Can be virtual or physical.
		Way of caching files inside a datacenter or headquarters and replicates files to S3. If you lose connectivity, you'd still have access to files
	CodeDeploy - Way of deploying code to EC2 instances or on-premise instances
	Opsworks - similair to ElasticBeanstalk. Uses shef?. Deploy code to EC2 instance or on premise
	IoT Greengrass

CloudWatch 101
--------------

**What is CloudWatch?**
	Monitoring service to monitor AWS resources & applications run on AWS
	
**What can cloudWatch monitor?**
	Compute
		EC2 Instances
		Autoscaling Groups
		Elastic Load Balancers
		Route53 Health checks
	Storage & Content Delivery 
		EBS volumes
		Storage Gateways
		CloudFront
	Host level Metrics
		CPU
		Network
		Disk
		Status Check
		
AWS Systems Manager
-------------------
	Allows you to manage Ec2 instances as scale
	Run a command on a bunch of EC2 instances. Instead of SSH'ing into each individual one
	
Summay Of Cloud Concepts and Technology
---------------------------------------













	
	
