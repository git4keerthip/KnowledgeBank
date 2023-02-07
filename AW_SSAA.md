# AWS

A region would have one or more availability zones
   60 miles between two availability zones 
A availability zone has one or more data centers

Edge locations are used for CDN and regional cache static data , increases latency 
Cloud front is for Cache

Regional Edge  cache has data storage 
Edge location has services that needs to be cached are hosted 

Local zones  - EDGE OF INFRASTRUCTURE . Local zone has commonly used AWS services
Faster than aws regions , low latency  , part of application can be deployed in local zone


IAM --  Authentication by Identity managements  
       Authorization by access management 

Groups cant assume role

Role will have temporary access

AWS fargate -- > serverless containarization env
	•   Dependencies
	•   Runtime engine
	•   Configuration engine
	•   Code






Lambda has 15 min code execution

Computation on AWS can be done in these forms

	• Instances   (EC2 , VMs)
	• Containers  
	• Serverless (EFS)

Security Groups

AMI -- Amazon machine Image

Dedicated Hosts will have license and entire rack for customer and not have shared tenancy . Related to compliance level  as well. 


AWS contains orchestration services as below
	ECS - run and scale containerized applications
	EKS -- run and scale kubernetes application

ECS vs EKS

CIDR -- classlesss inter domain routing 

Storage
-----------------

Block storage - Instance store , high through put  , temporary
                             EBS Volume - Data not lost , remounted 

File storage - EFS for linux , shared file system across multiple EC2 instances
                         Fsx for windows

Object storage - s3

AWS Database
-----------------------

Relational -
Key value - Dynamo DB
In memory-
Document
Wide column
Graph
Time series
Ledger


Resilient -
Security-
Highly -

Well architecture infrastructure Pillars

Security
Cost optimization
Reliability
	•    Recover from failure
	•    Scale to increase availability
	•    Test recovery procedures
Performance efficiency
	•     Reduce Latency
Operational excellence  
	•       perform operations with code
	•       Test response for unexpected events
Sustainability
	•   Maximize utilization



