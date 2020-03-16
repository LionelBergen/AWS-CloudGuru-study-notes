Forgot to commit at home, so making a new file for easier merging

Exam notes / Tips:
------------------
Whitepapers for AWS pricing is a must read
Whitepapers conclusion especially
The terms 'Capex' and 'Opex' will come up a lot
Know which services are free / what free tier offers - remember resources provisioned are not free. E.G EC2 instances created
4 RC2 Pricing Models
Know the different Serverless features inside AWS
What 'Snowball' is and how it's priced
Budgets VS Cost explorer - Budgets is before costs incurred, explorer is for after costs incurred
What Level Of Support do you need for TAM? - Enterprise!
(Know the Case severity / response times...)[#Case Severity / Response time] Especially production down response time.
Know (what tags are)[#what are tags] & (what resource groups are)[#resource groups]
Tag Editor is a global service, while system manager and resource groups are on a regional basis.
Know the (Best practices with AWS Organizations)[#Best practices with AWS Organizations]
You can only have 20 linked accounts. Or you can add more by going to a link
Know what Billing alerts are. When monitiroing is turned on the paying account, billing data for all linked accounts is included
	You can still create billing alerts per individual account
Know what CloudTrail is - per AWS account and enabled per region
Know the 3 steps in CloudTrail to consolidate logs using an S3 bucket
Remember what an Organization is - it allows you to attach OU's & accounts and policies to those OU's & accounts
Know the difference between (quick starts and landing zones)[#Quick starts & aws landing zones]
[Calculates](#AWS calculators) comes up a lot, be sure to actually use both of them a few times.
[Calculates](#AWS calculators) Know the difference between the 2 and what each could be used for (C-level exec presentation to move to cloud)
Consolidated billing allows you to get volume discounts on all of your accounts
Unused reserved instances of EC2 are applied across the group
	
White paper conclusion
----------------------

While the number and types of services offered by AWS have increased dramatically, the philosophy on pricing has not changed.
You pay as you go, pay for what you use, pay less as you use more and pay even less when you reserve capacity. Projecting costs for a user case, such as web hosting can be challenging, because a solution typically uses multiple features across multiple AWS products, which in turn means there are more factors and purchase options to consider.


Terms to be added to main list
------------------------------
RCU - Read Capacity Unit
WCU - Write Capacity Unit
Meta data  - Data about data
OU - Organizational Unit
TCO - Total Cost Ownership


How AWS pricing works
---------------------

**Fundamental Principles**
Pay less the more you use
Pay less when you reserve capacity

**Capex** - Capital Expenditure. You pay up front, it's a fix sunked cost
**Opex** - Operational Expenditure. You pay for what you use. Think of Utility such as gas, water etc

**Pricing Policies**
Pay as you go
Pay less when you reseverve
Pay even less per unit by using more
Pay even less as AWS grows
Custom pricing

**Best practices / principles**
Understand the fundamentals of pricing
Start early with cost optimization - 
Maximimize the power of flexibility - You don't pay for cloud resources when they are not running. By turning off instances you don't use, you save 70%+ compared to using them 24/7
Use the right pricing model for the job - On demand, dedicated, spot, reservations

**Free services**
1 year free EC2 for new users
Amazon VPC
Elastic Beanstalk (Instances may not be)
CloudFormation (resources provisioned are not)
Identity Access MAnagement (IAM)
Auto Scaling (EC2 instances povisioned are not)
OpsWorks (instances povisioned are not)
Consolidated Billing

**What determines Price?**
Clock Hours of Server Time
Instance Type - T1 Micro or R4 etc
Pricing Model
Number of instances
Load Balancing
Detailed Monitoring
Auto Scaling
Elastic IP Addresses
Operating Systems and Software Packages

**3 fundamentals**
	Compute
	Storage 
	Data Outbound
	
Lambda Pricing
--------------

**What determines Price for Lambda?**
	Request Pricing - Free Tier: 1 million requests per month. After that, $0.20 per 1 million requests therafter
	Duration Pricing - 400,000 GB-seconds per month free, up to 3.2 million seconds of compute time 0.00001667 for ever GB-second thereafter
	Additional chargest - If lambda function uses other AWS services or transfers data. E.G reads and writes data to/from S3 you'll be billed for read/writes to S3
	
**What Determines Price for EBS?**
	Volumes (Per GB)
	Snapshots (Per GB)
	Data Transfer
	
**What Determines Price for S3?**
	Storage Class (IA, or 1AZ IA etc)
	Storage
	# of Requests (GET,PUT,COPY)
	Data transfer
	
**What Determines Price for Glacier?**
	Storage 
	Data retrieval time

**What is Snowball?**
	AWS Snowball is a PB-scale (Petabyte-Scale) data transport solution to transfer large amounts of data in/out of AWS cloud. Like a gigantic disk to move data into AWS

**What Determines Price for Snowball?**
	Service fee per job - Snowball 50TB : $200, 80TB : $250
	Daily Charge: First 10 days are free, after that it's $15 a day
	Data transfer: Data Transfer into S3 is free. Data transfer out is not.
	
**What Determines Price for RDS?**
	Clock Hours of Server Time
	Database Characteristics - eg how large
	Database Purchase Type
	Number of Database Instances
	Provisioned Storage
	Additional Sotrage
	Reqeusts
	Deployment Type
	Data Transfer
	
**DynamoDB**
	Provisioned throughput (Write)One write capcity Unit provides up to one write per second, enough for 2.5 million writes per month
	Provisioned throughput (Read) - one read capcity unit (RCU) provides up to two read per second, enough for 5.2 million reads per month
	Indexed data storage - Hourly rate per GB of disk space tha your table consumed 
	
**What determines Price for CloudFront?**
	Traffic Distribution
	Requests
	Data Transfer out
	
AWS Budgets VS Cost Explorer
----------------------------

**AWS Budgets** - Gives you ability to set custom budgets taht alert you when your costs or usage exceed your budgeted amount
	Used to budget costs **BEFORE** They have incurred.
**AWS Cost explorer** - Easy to use interface used to visualize, understand, manage AWS costs and usage over time.
	Used to budget costs **AFTER** they have incurred.

AWS Support Plans
-----------------

**4 types of support plans**

|--------------------------------------------------------------------------------------------------------------------------------|
|                   |Basic|Developer                     |Business                           |Enterprise                         |
|-------------------|-----|------------------------------|-----------------------------------|-----------------------------------|
|COST               |FREE |$29 / month                   |$100 / month                       |$15,000/Month                      |
|Tech Support       |     |Businees hour access via email|24x7 email, phone & chat           |24x7 email, phone & chat           |
|TAM                |NO   |NO                            |NO                                 |YES                                |
|Who can open cases?|None |1 Person / Unlimited Cases    |Unlmited Contacts / Unlimited Cases|Unlmited Contacts / Unlimited Cases|
|--------------------------------------------------------------------------------------------------------------------------------|

### Case Severity / Response time
**Case Severity / Response time**
|------------------------------------------------------------------------------------------------------------|
|Basic|Developer                            |Business                              |Enterprise                  |
|-----|-------------------------------------|--------------------------------------|----------------------------|
|     |General guidance: < 24 business hours|GeneralGuidance: < 24 hours		   |General guidance < 24 hours
|	  |System Imparied: < 12 business hours |System impaired < 12 hours			   |System impaired < 12 hours
											 Production system impaired: < 4 hours |Production system impaired < 4 hours
											 Production system Down: < 1 hour      |Production system down: < 1 hours
																				   |Business-critical system down: < 15 minutes
|------------------------------------------------------------------------------------------------------------|

Tagging & Resource Groups
-------------------------

### what are tags
** What are tags?**
	Key value pairs attached to AWS resources
	Meta data (Data about data)
	Tags can sometimes be inherited
	Resource group make it easy to group resources using the tags. You can group resources that share one or more tags
	Could contain for example EC2 public & Private IP addresses. For ELB, port configurations
	
**Resource groups**

Resource gorups contains:
	Region
	Name
	Employee Id
	Department
	etc.
	
You can group resources using tags that are assigned to them. You can group resources that share on or more tags E.G Name, region employe ids...

You can apply automation resources tagged with speicifc tags. E.G stopping all EC2 instances with XYZ tags
	
AWS Organizations & Consolidated Billing
----------------------------------------

**What is AWS Organizations?** - An account management service enabling you to consolidate multiple AWS accounts into an orgnization that you create and centrally manage

Two features sets:
	Consolidated billing
	all features

### Orgnization chart
TODO

All linked accounts are indenepndent

**Advantages of Consolidated billing**
	One bill per AWS account
	Very easy to track cahrges and allocate costs
	Volume pricing discount
	
### Best practices with AWS Organizations
**Best practices with AWS Organizations**
- Always enable multi-factor authentication on root account
- Always use a strong and complex password on root account
- Pay account for billing purposes only. Don't deploy resources on it

**Cloud Trail Tips**
	Cloud trail per AWS account and is enabled per region 
	Can consolidate logs using an S3 bucket:
		1)Turn on CloudTrail in paying account
		2)Create a bucket policy that allows cross-account access
		3)Turn on CloudTrail on the ohter accounts and use the bucket in the paying account
	This way, the buckets can only read to the bucket and not write
	
### Quick starts & aws landing zones
AWS quick starts & AWS landing zones
------------------------------------

quick start - Automatically setup solutions created by professionals in X technology. For example, An exchange expert setup a SQL exchange AWS solutions.

landing zone - Multi-account organization solutions. Uses AWS best practices to set up multiple accounts with policies etc.
	Currently E.G shared services account, log archive account, orgnizations account & Security account. 
	Automating multi-account setup

### AWS calculators
AWS Calculators
---------------

AWS helps you calculate costs using a couple different calculators

AWS simple Monthly Calculator - Calculates monthly cost

AWS Total Cost of Ownership Calculator - Cloud aws price VS On location cost comparison (doing it yourself)

**Calculator areas of cost**

Server costs - Software, OS, racks etc
Storage costs - hardware storage disks
network costs -  Switches, core/aggregation
IT labor costs - Server Admin Virtualization Admin









