General tips
------------
Read the certification FAQ: https://aws.amazon.com/certification/faqs
Read exam blueprint and ensure you know everything in scope
Check the acloud fourms for the certs, people post about topics they were surprised / needed to study more after taking the cert exam


# AWS-CloudGuru-study-notes
Notes taken from cloud guru videos in preparing for the 'AWS Certificate Solutions Architect Associate Exam'.

Areas marked with '\*' are important, areas marked with ~ are not so important and areas marked with two ~'s should not come up in the exam at all.

AWS Certificate Solutions Architect Associate Exam
--------------------------------------------------
**Services covered on Exam**

    Compute ***
    AWS Global Infrastructure ***
    Storage ***
    Databases ***
    Networking & Content delivery ***
    Security & Identity, Access Management **
    Messaging
    Desktop & App Streaming (Very high level, workspaces)
    Management Tools (Little bit)
	
**Need to know:**

    How to build a VPC from memory. - [See here](#NetworkingContentDelivery)
    'Lambda' is important, but may not be on the course. There is a course in Cloud Guru on Lambas to look at
    Region VS availabilty zone: Availbility zone is a physical data center, region is an geographical area
    What is WorkSpace? (It's a virtual Desktop in the cloud)
    VDI?
	
**AWS Global Infrastructure:**

    A Region: has 2 or more availability zones. Geographical area
    An Availability Zone: is just a Data Center
    Edge location: CDN end points for CloudFront, there are more Edge Locations than regions.
        Cache images, content in another area so the region doesn't need to be reached everytime (only for the first person)

## NetworkingContentDelivery<a name="NetworkingContentDelivery"></a>
**Networking & Content Delivery:**

    VPC***: Virtual Private Cloud, virtual data center where you deploy assets. You can connect multiple VPC's together
    Route53*: Amazon's DNS. Why the name: 53 is the Port for DNS. Route66 is the first interstate across the US
    Cloud Front: Consists of a whole bunch of Edge Locations
    Direct Connect*: Way of connecting directly using a dedicated line
    EC2: Elastic Compute Cloud are Virtual machines in the cloud. 
    ~EC2 Container Service~: Supports docker containers, cluster management taken care of cluster management infastructure for you
    Elastic Beanstalk: Takes a look at application and provisions the archecture for you
    ~Lambda~: 
    ~Lightsail~: Out of the box cloud, deploys your site for you, for users who don't want to learn AWS

**Storage:**

    S3***: Simple Storage Service A Virtual Disk in the cloud to store objects (Files). *Object-based storage*. One of the first services
    Glacier: Low cost data archiving. A place to archive from S3 off.
    EFS: Elastic File Service File based storage you can share it with multiple version machines. Unlike S3, you could to install applications here.
    ~EBS~: Elastic Block Store A virtual disk to attach ES2 isntances to
    Storage Gateway: A virtual machine image normally installed on premise. A way to connect S3 to On premise datacenter / headcourters, connects between S3 and on premise
	
**Databases:**

    ~RDS: Relational Database Service consists of Mysql, PostgreSQL, MariaDb.. Aurora & more.
    DynamoDB**: Non-relationsal database. AKA NoSQL database Very scalable, high performance
    ~Redshift: Amazon's Data warehousing solutions. Example usage: Running reports, instead of a heavy load on the production database, send a copy of the DB to Redshift and run reports there
    ~Elasticache: Cache data in the cloud *Take a load of your database*
	
**Migration:**

    Snowball: Small appliance, used for sending data? Snowball-edge has compute capacity added.
    DMS: Database Migration Services - Used for migrarting databases to other regions, redshift etc. You can move Databases. E.G from Oracle to Aurara
    ~SMS~: Server Migration Service - Migrate Virtual Machines. Specifically VMware virtual machines to replicate to AWS cloud 50 concurrently at the same time

**Analytics:**

    ~Athena: Allows you to run SQL queries on S3
    ~EMR: Elastic Map Reduce produce large amounts of data. E.G log analysis, market analysis. Uses Hadoop.
    ~Cloud Search: Search capabilities within website
    ~Elastic Search: Search capabilities within website
    Kinesis***: Streaming & Analysing realtime data at massive data. Store & analyis terabytes of data per hour. E.G financial anlysis or social media feeds
    Data Pipeline: Move data from one place to another. E.g from S3 to DynamoDB or visa-versa. A pipeline job
    ~Quick site~: Business Analytics tools make rich dashboards for data.

**Security & Identity:**

    IAM***: Identity Access Management
    ~Inspector~: Agent installed on a VM to inspect the VM and does reporting on Security of those VMs.
    Certificate Manager: Gives you free SSL certificates for domain names
    Directory Service*: Connect Active Directory to AWS
    ~WAF: Web Application firewalls Application level protection. E.G SQL Injection, cross site scripting
    ~Artifacts: Documentation in the AWS console

**Management Tools:**

    Cloud Watch: Used to monitor performance. E.G ES2 RAM, DISK utilization
    Cloud Formation*: Turn infrastructore into code. Document that describes the AWS environment
    Cloud Trail: Auditing AWS resources. E.G if someone creates a user, cloud trail will audit that
    Opsworks: Automated deployments using shef?
    ~Config manager: Monitor environment, gives warnings when your environment may break. E.G something that breaks company policy
    ~Service Catalog~: 
    Trusted Advisor: Gives you tips on security fixes, cost optimizations etc. Automated way of scanning your environment to give you tips

**Application Services:**

    ~Step Functions~: Way of visuilizing what's going on in your application E.g what microservices you're using
    SWF***: Simple Workflow - Way of coordinating automated & human tasks. E.G ordering a product a human needs to deliver / get.
    API Gateway: A way to create, publish, secure and monitor API's at scale. A way for applications to access backend data/services
    ~AppStream~: Way of streaming desktop applications to users
    Elastic Transcoder: Transfer video format to something suitable for different devices. E.G different format/resolution for an Ipad vs desktop

**DeveloperTools:**

    CodeCommit: Basically Github. A place to store code in the cloud, can be open / closed
    CodeBuild: Paid for by the minute, a way of compiling your code
    CodeDeploy: Way of deploying code to ES2 instances. Very automated
    CodePipeline: ??

**Mobile Services:**

    Mobile HUB: Add, configure design features for a mobile app. E.g push notifications, backend logic, User auth, data storage, content delivery, analytics
    ~Cognito~: User sign in. E.G using Social login, gmail credentials etc
    Device Farm: Test your application on hundreds of physical devices
    Mobile analytics: Collect & analyse app usage data
    ~PinPoint~: Enables and engage your application users. Collect data on what users are doing with your app

**Business Productivity:**

    ~WorkDocs~: store word docs in the cloud
    ~WorkMail~: Send/recieve emails in AWS

**Internet Of Things:**

    ~iOT~: Internet Of Things
	
**Desktop & App Streaming:**

    Workspaces: Way of having your desktop in the cloud.
    AppStream 2.0: Way of streaming desktop applications to users

**Artificial Intelligence:**

    Alexa: Amazon's voice service in the cloud. Echo's uses it
    lex: You no longer need an Echo to use Alexa, you can connect any device to Alexa
    Polly: Turns text into voice E.G MP3 files. Helps Alexa render her voice
    ~Machine Learning~: Give AWS a dataset for ML to predict outcomes
    Rekognition: Upload pictures and it'll tell you whats in that picture

**Messaging:**

    SNS***: Simple Notifcation Services. Notify you via text, or email. Or even HTTP endpoints
    SQS***: Decoupling applications (If one system goes does, the request will still be queued, another ES2 can pick it up). A queue system. 
    SES***: Simple email service. A way of sending and recieving emails

## ObjectBasedStorage<a name="ObjectBasedStorage"></a>
**Object based storage:**
    A place to store files, Not a place to install things
    
Block based storage:

	
	
