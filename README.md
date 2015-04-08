# AWS Solution Architect

## A deep dive in to traditional vs AWS cloud

### Traditional 

A traditional approach would have the below steps 
  - setting up data center
  - racks
  - internet (connect  to multiple provides - blend)
  - Equipments
  - configure it
  - move to different datacenter for redundancy

### AWS approach is much simpler than traditional
  -  Select region
  -  availability zone
  -  provision
  -  configure
  -  expand to other zones
  -  other region

### Basic comparison
  - cost
  - pas as you go
  - elastic computing (add server on need basis and remove after use - automatic)
  - scalable
  - sucrity complaince are offered(PCI,HIPAA).

## Understand the below topics before starting AWS 
  - Vertical vs horizontal scaling
  - web server vs application server
```
http://javarevisited.blogspot.com/2012/05/5-difference-between-application-server.html
http://www.diffen.com/difference/Application_Server_vs_Web_Server
```


## Core AWS services

###Traditionional to AWS mapping to understand AWS architecture


| Technology stack | on-premises                     | AWS                       |
| -----------------|:--------------------------------:| ----------------------------:|
| Network      | VPN,MPLS,VLAN, Routing tables | Amazon VPC,VPN,AWS Direct connect,routing tables |
| Security     | Firewalls,SSL,user groups etc      | AWS security groups, Cloud HSM, s3 SSE, cloudtrial etc |
| Storage | DAS,SAN,NAS,SSD      |  Amazon EBS, s3, EC2 Instance storage (SSD) |
| Computer | Hardware, virtualization | EC2|
Content Delivery|CDN (http://searchaws.techtarget.com/definition/content-delivery-network-CDN)|Cloud Front|
|Data base|DB2,MS SQL Server,My SQL, Mongo DB, Couchbase etc | Amazon RDS,Dynamo DB,MS SQL Server,MySQL,Postgres SQL etc|
|Load balancing| Hardware and software balancing, HA proxy (https://www.digitalocean.com/community/tutorials/an-introduction-to-haproxy-and-load-balancing-concepts)| Elastic load balancing,software and hardware balancing,HA proxy|
|Scaling|Clustering,Zookeeper| Auto scaling,software clustering|
|DNS| DNS providers| Amazon route 53|
|Analytics| Hadoop, Cassandra,spark | Amazon elastic map reduce|
|Data warehousing|Specialized HW/SW | Amazon redshift|
|Messaging and workflow | Messaaging and workflow software | Amazon SQS,SNS,SWF|
|Caching| memcached,SAP Hana (http://en.wikipedia.org/wiki/SAP_HANA),(http://memcached.org/)| Amazon Elastic Cache|
|Archiving| Tape Library,tape storage | Amazon Glacier|
|Email|Email software| Amazon simple Email Storage|
|Identity Management| LDAP| AWS IAM,LDAP|
|Deployment|Chef,Puppet| AMIs,CloudFormation,OpsWorks,Elastic Beanstalk|
|Management and Monitoring| CA,BMC,Rightscale| AWS cloudwatch,cloudtrial|


#The security model in AWS

Amazon Web Services (AWS) delivers a scalable cloud computing platform with high availability and dependability,
providing the tools that enable customers to run a wide range of applications. Helping to protect the confidentiality,
integrity, and availability of our customers’ systems and data is of the utmost importance to AWS, as is maintaining
customer trust and confidence.
###Shared Security Responsibility Model

```
http://d0.awsstatic.com/whitepapers/Security/AWS%20Security%20Whitepaper.pdf
http://media.amazonwebservices.com/AWS_Security_Best_Practices.pdf
http://aws.amazon.com/compliance/
```
AWS products that fall into the well-understood category of Infrastructure as a Service (IaaS)—such as Amazon EC2,
Amazon VPC, and Amazon S3—are completely under your control and require you to perform all of the necessary
security configuration and management tasks

AWS managed services like Amazon RDS or Amazon Redshift provide all of the resources you need in order to perform a
specific task—but without the configuration work that can come with them. With managed services, you don’t have to
worry about launching and maintaining instances, patching the guest OS or database, or replicating databases—AWS
handles that for you.
####AWS Account Security Features

  - AWS Credentials
  - Passwords
  - AWS Multi-Factor Authentication (AWS MFA)
  - Access Keys 
  - Key Pairs 
  - X.509 Certificates
  - Individual User Accounts
  - Secure HTTPS Access Points
  - Security Logs
  - AWS Trusted Advisor Security Checks

Data stored in Amazon EBS volumes is redundantly stored in multiple physical locations as part of normal operation of those services and at no additional charge. However, Amazon EBS replication is stored within the same availability zone, not across multiple zones; therefore, it is highly recommended that you conduct regular snapshots to Amazon S3 for long-term data durability.

## AWS Global Infrastructure
Deciding between Regions

  - Latency
  - Cost
  - Features
  - Legal

###Regions and availability zones

####Region level services and AZ level services

| Region level      | AZ level           | Global|
| ------------- |:-------------:| ---------:|
| S3      | EC2 | IAM |
| Dynamo DB      | EBS      | Route 53|   
| Auto Scaling |       | CloudFront|
| Cloud search |     | | 
| Highly available | Not highly available| |
| Managed by AWS | managed by user | Managed by AWS|


#### Services

   - Elastic Load Balancing
   - Auto scale group (based on time , metric, load)
   - S3 (span across AZs)
   - Dynamo DB (stored in SDD)
   - Amazon Machine image (basic unit of deployment)
   - RDS (back up, patch mgmt,native access to mySQL)
   - EC2


##Accessing AWS

  - AWS is API driven
  - Can do much more than 'management console' using API calls
  - REST API
  - Identity and Access Management (IAM)
  - IAM is not applicable for application management
  - Dont use 'root' account
  - Enable MFA as a best practice with IAM
  -  IAM roles can be assigned for shot span of time
  -  Two policies while creating roles  
        - trust policy (principal)
        - access (what actions)
  - Accessing AWS through Mgmt Console(username/password), AWS CLI(access key + secret key), SDK,APIs (access key + secret key).
  - Policies are stored in JSON
  - Create policies using template,policy generator, custom, check with simulator
  - Role based Access management

##AWS Security Token Service using Federation 

```
http://docs.aws.amazon.com/STS/latest/APIReference/Welcome.html
```

  - STS lightweight web service can request temp credentials  for IAM users
  - federated user
  - STS identity broker with federation user
  - To access by a third party , using their AWS account id and external id we define a truested entitly for the role. After creating the role, we can share Amazon resource Name (ARN) with the 3rd party.

## SSO Federation Using SAML 2.0

  - Single sign-on
  - Use existing identity management software to manage access to AWS resources
  - open standard
  - one username and password
  - Assume Role with SAML API

## AWS Directory Service
  - Active Directory to AWS
  - AD connector
  - Simple AD powered by Samba 4

## Web Identity Federation
  - temporary access to AWS
  - support for Amazon,google,facebook

## IAM
  - templates
  - Administrative access
  - Power User access
  - Read only access
  - Automated policy 
  - consolidated billing
  - MFA
  - API access with roles


# VPC
                                                                                                                  - Its like on premise private data centers
                                                                                                                  
