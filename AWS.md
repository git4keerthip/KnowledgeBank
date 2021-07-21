### Cloud Computing Types 
- Infrasturcture as service - EC2 (provides network , servers , stoareg as service)
- Platform as service - EBS (plug and play your application and data, everything from runtime to networking is managed by othes))
- Software as service - gmail , zoom


### AWS
- Elastic cloud compute EC2
- EC2 types are c
    - General purpose (t2 ,t4 ,,,m5 ,m4)
    - Memory OPtimized (R*)
    - COmpute optimized (C*)
    - Storage Optimized (I*)
    - Accelerated computing
- m5.2xlarge
  m : instance class (general purpose)
  5 : generation
  2xlarge : size 
### EBS
- Network attached storage for EC2
### Elastic Load Balancing
- Load balancers that serves the forward internet traffic down to EC2 instances.
- ELB types 1.Application Load balancer (http/https) 
            2.Network load balancer (tcp)

### ASG - Auto Scaling Group
- Automatically register new instnces to load balancer
- Scale out (add) instances to match an increase load
- Scale in (remove) instances to match an decrease load
- ASG mathches up desired capacity

### S3
- Max size is 5TB else multi-part upload
- s3 can host static websites (make bucket public for this website hosting)
### ECR
- Elastic container registrey,private docker resgistry on AWS.
- We store our docker images so that we can run them on ECS/Fargate
### ECS
- Elastic container service , docker containers for AWS
- We will create and manage EC2 here
### Fargate
- Launch Docker containers for AWS
- We dont need to create EC2 ,Fargate will takescare of that
- ServerLess offering ,AWS will run EC2 based on cpu and ram specified
### Lambda
- Intended for shorter executions, no servers to manage, runs on demand , scaling is automated.
- Event Driven functions
### Cloud Formation
- Infrastructure as code , declarative way of outlining AWS infrastructure. 

### CLoudFront 
- Global CDN for AWS
### Rout53
- Managed DNS
- Route users to closet deployment with least latency 
- Types - General Routing policing , Weighted (kinda like Load balancer) Routing, Latancy Routing, Failover ROuting policy.
### CloudWatch Metrics
### Virtual Private CLoud 
-  VPC is partitioned into public and private subnets
-  Public subnet is connected to internet via internetgateway
-  NAT gateway is present in public subnet
-  Private can connect to internet via NAT gateway and NAT gateway is connected to internet gateway.
-  Each avialiable zone will have VPC
### CLoud communication
- Two ways for applications  can communicate. 1. synchoronous 2.asynchronous using message queue (two applocations will be decoupled).This is event based.
- AWS has below
    - SQS (queue model)
    - SNS (pub/sub model)
    - kinesis (real time data streaming)
### SQS (Simple Queue Service)
- AWS queue model for messaging service
- Producers pushing messages to SQS and comsumers read those messages and delete them later. 
- Serverless and its scalable
- retention within 4 to 14 days
- No limit to how many messages in queue
- low latency on publish and receive
### SNS (Simple Notification Service)
- One message can be delivered to different receivers
- SNS can even sent notification to SQS
- Many event subscribers can listen to SNS topic



