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
|Data base|DB2,MS SQL Server,My SQL, Mongo DB, Couchbase etc |Amazon RDS,Dynamo DB,MS SQL Server,MySQL,Postgres SQL etc|
|Load balancing| Hardware and software balancing, HA proxy (https://www.digitalocean.com/community/tutorials/an-introduction-to-haproxy-and-load-balancing-concepts)| Elastic load balancing,software and hardware balancing,HA proxy|
|Scaling|Clustering,Zookeeper| Auto scaling,software clustering|
|DNS| DNS providers| Amazon route 53|
|Analytics| Hadoop, Cassandra,spark | Amazon elastic map reduce|
|Data warehousing|Specialized HW/SW |Amazon redshift|
|Messaging and workflow | Messaaging and workflow software | Amazon SQS,SNS,SWF|
|Caching|memcached,SAP Hana (http://en.wikipedia.org/wiki/SAP_HANA),(http://memcached.org/)| Amazon Elastic Cache|
|Archiving| Tape Library,tape storage |Amazon Glacier|
|Email|Email software| Amazon simple Email Storage|
|Identity Management| LDAP| AWS IAM,LDAP|
|Deployment|Chef,Puppet|AMIs,CloudFormation,OpsWorks,Elastic Beanstalk|
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








