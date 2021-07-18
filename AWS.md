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
- 
