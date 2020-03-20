exam tips:
----------
Read: https://aws.amazon.com/compliance/shared-responsibility-model/
Remmeber what the customer is responsbile for, versus AWS in terms of Security
Try to visualize the question, ask yourself if you are able to do the task, if you are, most likely the customer IS responsible for the securtiy of it. 
	(E.G IAM users, patching EC2 instance) Otherwise it's AWS, such as cabling, security cameras etc
Encryption is a shred responsibility (you are respoinsible for turning it on e.g HTTPS)
AWS WAF is a web application firewall, designed to stop hackers
AWS Shield is a DDOS mitigation service designed to stop DDOS attacks
AWS Inspector used for inspecting EC2 isntances for Vulnribilities
AWS Trusted advisor inspects your AWS account as a whole. It does more than just security checks it also does cost optmization, perofrmance and fault tolerance
AWS CloudTrail records console actions and API calls. You can identify the user & IP address, time of each action
Lots of scnario questions on which to use: Inspector, CloudWatch, AWS Config, Trusted Advisor and CloudTrail. So know the differences between those 5



ETL - Extract/Transform/Load



Compliance On AWS & AWS Artifact
---------------------------------

AWS follows a bunch of compliance standards from many different countires. You can visit aws.amazon.com/compliance for a comprehensive list & to print out for auditors etc.

AWS Artifact - the same as above, but you can visit it from AWS console, under security, AWS Artifact
	- Get compliance documents
	
AWS Shared Responsibility Model
-------------------------------

AWS manages security of the cloud. Security inside the cloud is responsibility of the customer.
Customers retain control of what security is implemented the same way they would their own content, platform, applications systems and networks on site.

customers responsbility: Updating EC2 instances with latest patches, encryption, data integritiy and authentication. Network traffic protection. Operayting system, network firewall configuration, platform applications, Identity and access management, customer data

AWS WAF & AWS Shield
--------------------

**WAF - Web Application Firewall**

	Helps protect your web applications from common web exploits that could affect application availability, compromise security or consume excessive resouces
	Inspects web traffic for maliciousness At the application layer
	cross site scripting, SQL injection
	
**AWS Shield**

	DDOS protection
	Standard & Advanced

AWS Insepector VS AWS Trusted Advisor VS CloudTrail
---------------------------------------------------

**Amazon Inspector** - checks best practises being followed, vulnribilities
	Installed on an *EC2 instance*

**Trusted Advisor** - Online resource to help reduce cost, increase performance and improve security by optimizing AWS environment
	Gives real time guidance to help provision resources following best practices.
	Cost optimiziation, performance, security, fault tolerance.
	Core checks & recommendations (free), Full trusted advisor (business & enterprise only)
	checks *whole environment*
	
**CloudTrail** - Monitors API calls in AWS platforms
	Records AWS Management console actions and API calls. You can identify the IP addreess and user who made calls
	
CloudWatch vs AWS Config
------------------------

**CloudWatch** - Online monitoring resources and applications
	All about *performance*
	CPU, Disk, Network utilizations, Status check of EC2 instances
	
**AWS Config** - Detailed view of the *configurations* of AWS resources in an AWS account
	Can see how configuration changed overtime and how resources are related to one another
	Examples: Security group change, Port change on an EC2 instance

Athena VS Macie
---------------

**Athena** - Run SQL queries on S3 buckets. Remember S3 buckets are files and such.
	Serverless nothing to providision, pay per query / per TB scanned.
	No need for ETL processes (Extract/Transform/Load)
	Works directly with data stored in S3

**Uses for Athena** - Querying logs stored in S3, Generating business reports on data stored in S3, Analyse AWS cost and usage reports, run queries on click-stream data

**Macie**