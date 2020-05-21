# AWS – Eliminate Heavylifting of IT infrastructure

### AWS Infrastructure
Regions – Geographical Area with atleast two availability Zones
Factors affecting region choice – Latency, Cost, Compliance
Each AWS Region has multiple, isolated locations that are known as Availability Zones

### AWS Compute
Amazon LightSail – Deploy web apps quick

### Networking and Storage
Virtual Private Cloud (VPC)
The idea of VPC is to provide an abstract frame which allows user to control access to the resources in frame. It is a multi-availability region service.
Subnets are primarily used to determine access to gateways, to ingress/egress, as well as to isolate specific traffic that you don't want to talk to each other or do want to talk to each other
CIDR Notation
An important concept that's used in networking on AWS is CIDR, or Classless Inter-Domain Routing. CIDR network addresses are allocated in a virtual private cloud (VPC) and in a subnet by using CIDR notation. A /16 block provides 65,536 IPv4 addresses. A /24 block provides 256 addresses. 
Each VPC has a private IP starting with 10.10.*.*/16 and subnet 10.10.*.*/24  – first 24 bits are frozen. The server is in the VPC.
Internet Gateway (IGW) is used to create map and assign it to the created VPC. A route table is to be created. The route table must be associated to the public subnet.
The data plane must be contained in a private subnet. Important is to not assign the IGW to this private subnet.

### Elastic Loadbalancer
The incoming traffic is distributed evenly across the available VPC. Using the endpoint, the server can be reacheable.

### Virtual Private Gateway (VGW)
The objects inside the VPC communicate each other with help of VGW instead of invoking IGW

Security groups 
A security group acts as a virtual firewall for your instance to control incoming and outgoing traffic. Inbound rules control the incoming traffic to your instance, and outbound rules control the outgoing traffic from your instance. The rules are evaluated by AWS. In order to make it work, attach it to a VPC where the server is located.

### AWS Storage

S3 – Object level storage (S3)
RDS – Block level storage (EBS, EFS)
Amazon Elastic Block Store (Amazon EBS) provides persistent block storage volumes for use with Amazon EC2 instances in the AWS Cloud. Each Amazon EBS volume is automatically replicated inside an Availability Zone to protect you from component failure, which offers high availability and durability. Amazon EBS volumes offer the consistent and low-latency performance that you need to run your workloads. Each EC2 instance has independent Boot and data EBS volumes. 

S3 is a very popular service that is used for scenarios such as basic object storage like images or text files, storage of backups, application file hosting, media hosting, and many other use cases. It can be used to store virtually any type of document or object at a large scale, as S3 has an unlimited capacity for your storage needs.

Buckets are repositories for objects that live in a specific region. These store the objects. Bucket permissions are controlled using Permissions, Access Control Policy.

Elastic File System, or EFS, and the elastic file system for AWS EFS is designed to be a regionally distributed, means it doesn't live inside any one subnet, a regionally distributed file store that can automatically attach to multiple EC2 instances simultaneously. EFS File Sync, you can even have that directory connect to your on-premises data center

### Database
Amazon Relational Database Service
RDS, a relational database of the flavor of choice, Ex: MySQL database, an Oracle database, a PostgreSQL database, or other flavors. But the difference is instead of taking care of the patching and the installs and installing the database itself, AWS takes care of all of the rest of the heavy lifting that otherwise your DBA would be doing.
Each RDS can be assigned to certain VPC, security groups and different encryption rules.

AWS DynamoDB 
DynamoDb is a fully managed, fast, and scalable NoSQL database. A solution that delivers reliable performance at any scale. The underlying hardware need not require explicit resource allocation rather asks for table and request throughput.

### Monitoring and Amazon CloudWatch
Amazon CloudWatch, you can monitor your cloud infrastructure intelligently. CloudWatch will collect data from your cloud-based infrastructure in one centralized location. With this data, you can create statistics, which drive operational procedures using features such as CloudWatch Alarms, Monitoring.

CloudWatch Logs is a place where you can send your log files for viewing in the console, and to stream to other services, like Lambda or Amazon Elasticsearch for analytics. CloudWatch is used to set alarms, visualize logs and metrics side-by-side, take automated actions, troubleshoot operational issues, and discover insights to optimize your applications.

Scaling with Load balancing and Auto Scaling
Amazon ELB (Elastic Load balancer)
Scales in a adaptive manner. Auto-traffic distribution and decoupling instances

Auto Scaling
Auto Scaling is what allows us to provision more capacity on demand, depending on different thresholds that we set, and we can set those in CloudWatch. 
AWS Security

### AWS Shared responsibility model
The AWS Shared Responsibility Model for EC2 is the model most businesses are familiar with because it’s easier in this model to understand the concept of ‘Security of the Cloud versus Security in the Cloud’. In this version of AWS’ Shared Responsibility Model, AWS takes responsibility for the security of its global infrastructure and what it calls its foundation services: compute, storage, database, and networking
Credentials, IAM are the important service that user needs to take on responsibility.
AWS responsibility
Security of the Cloud: We are responsible for protecting the infrastructure that runs all of the services that are offered in the AWS Cloud. This infrastructure is composed of the hardware, software, networking, and facilities that run AWS Cloud services.
Customer responsibility
Security in the Cloud: Customer responsibility will be determined by the AWS Cloud services that a customer selects. This determines the amount of configuration work the customer must perform as part of their security responsibilities.


### AWS Costs
The AWS Cost Explorer is a service that helps you easily visualize and understand costs and usage. AWS Cost Explorer also allows you to create reports. There are default reports built in, or you can create your own and more granular reports to analyze cost drivers.
Another tool AWS offers is AWS Budgets. AWS Budgets allows you to create alerts when your costs or usage exceeds a threshold over a specific time period. You define the time period, whether it be a week, month, or year, and you also define your thresholds. When you exceed the threshold, a notification can be sent out


