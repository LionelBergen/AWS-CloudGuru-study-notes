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

White paper conclusion
----------------------

While the number and types of services offered by AWS have increased dramatically, the philosophy on pricing has not changed.
You pay as you go, pay for what you use, pay less as you use more and pay even less when you reserve capacity. Projecting costs for a user case, such as web hosting can be challenging, because a solution typically uses multiple features across multiple AWS products, which in turn means there are more factors and purchase options to consider.



RCU - Read Capacity Unit
WCU - Write Capacity Unit


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
