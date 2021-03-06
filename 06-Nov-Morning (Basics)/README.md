# Topics

    - Introduction and basics of AWS (EC2, ELB, CloudWatch, S3 and VPC).

# Navigating the AWS Pages

1. AWS Home Page
    - https://aws.amazon.com/

1. Different Services
    - FAQ
    - Pricing
    - Getting started

1. AWS free tier
    - https://aws.amazon.com/free/

1. AWS documentation
    - http://aws.amazon.com/documentation/

1. Making changes to the AWS documentation
    - https://aws.amazon.com/blogs/aws/aws-documentation-is-now-open-source-and-on-github/
    - https://docs.aws.amazon.com/lambda/latest/dg/with-s3-example.html
    - https://github.com/awsdocs/aws-lambda-developer-guide/pull/217

1. AWS Console
    - http://console.aws.amazon.com/ (Personal Account)
    - https://cloudlabs.nuvepro.com/company/EdurekaLive/home (Edureka AWS Account)

# AWS Management Console

1. Navigating the AWS Management Console.

1. Selecting the Regions. We will do most of the labs in North Virginia.

1. Opening the services in different tabs.

1. Here are the AWS limitations with the AWS Account
    - EC2 Instance Type - only t2.medium
    - RDS Instance Type - only db.r5.large

# EC2

## Theory

1. What is EC2? (A virtual server)

1. Connecting to an EC2 (KeyPairs and Username/Passwords)
    
1. Security Groups

1. Pricing Models

1. Shared Tenancy vs Dedicated Hosts

## Practicals (By Praveen)

1. Creating Security Groups and KeyPair.

1. Creating a Launch Template and using it.

1. Launch the EC2 via the Launch Template.

1. Grab the Public IP address of the EC2 instance.\
![](images/2020-11-05-10-35-39.png)

1. Open Putty and specify the username and IP as shown below.\
![](images/2020-11-05-10-37-29.png)

1. In Putty navigate to `Connection --> SSH --> Auth`, click on browse and point to the Keypair (ppk file).\
![](images/2020-11-05-10-38-15.png)

1. Click on `Connect` to establish a connection to the EC2 instance. When prompted with the security alert for the first time say `yes`. 
![](images/2020-11-05-10-42-43.png)

1. Install a static website with Apache2 using the below commands.
    >sudo su\
    >apt-get update\
    >apt-get install apache2 -y\
    >service apache2 start\
    >cd /var/www/html\
    >rm index.html\
    >echo "Welcome to AWS" > index.html
    
1. Access the website via the browser by using the Public IP address of the EC2 instance. 

## Further Reading

1. Connecting to Your Linux Instance if You Lose Your Private Key
    - https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/replacing-lost-key-pair.html

1. How to create a username/password for EC2?
    - https://aws.amazon.com/premiumsupport/knowledge-center/ec2-password-login/
    - http://stackoverflow.com/a/7696451/614157

1. EC2 Instance Types
    - https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-types.html

1. How to work with shared and dedicated EC2 instances?
    - https://aws.amazon.com/ec2/dedicated-hosts/getting-started/
    - https://aws.amazon.com/ec2/dedicated-hosts/faqs/

1. How many EBS can be attached to EC2?
    - https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/volume_limits.html

1. Attaching a volume to multiple instances with Amazon EBS Multi-Attach
    - https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-volumes-multi.html

1. How to extend a existing EBS for Windows and Linux?
    - https://docs.aws.amazon.com/AWSEC2/latest/WindowsGuide/ebs-modify-volume.html
    - https://docs.aws.amazon.com/AWSEC2/latest/WindowsGuide/recognize-expanded-volume-windows.html
    - https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/recognize-expanded-volume-linux.html

1. EC2 accidental termination
    - https://docs.aws.amazon.com/AWSEC2/latest/WindowsGuide/terminating-instances.html#Using_ChangingDisableAPITermination

# CloudWatch

## Theory

1. A centralized monitoring solution similar to Task Manager in Windows and much more

1. Standard vs Detailed monitoring

1. Alarms (OK, ALARM, INSUFFICIENT states) on metrics

1. AutoScaling works with Alarms

1. Event Handling (like an EC2 getting terminated)

1. Scheduling activities

## Practicals (By Praveen)

1. Enable detailed monitoring and watch the metrics in the CloudWatch DashBoard

1. Create an Alarm and notice the change in the state
    >dd if=/dev/urandom | bzip2 -9 >> /dev/null

## Further Reading

1. How CloudWatch works?
    - https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/cloudwatch_architecture.html

1. See Key Metrics from all the AWS Resources
    - https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/CloudWatch_Automatic_Dashboards_Cross_Service.html

1. Using DashBoards
    - https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/CloudWatch_Dashboards.html

# S3

## Theory

1. Use cases

1. Buckets, folders and files (with constraints)

1. Storage classes and Lifecycle Management

1. Versioning

1. Cross Region Replication

1. Snow Devices

## Practicals (By Praveen)

1. Creating buckets and uploading files

1. Using different storage classes

1. Versioning in S3

## Further Reading

1. Storage Classes
    - https://docs.aws.amazon.com/AmazonS3/latest/dev/storage-class-intro.html

1. Versioning
    - https://docs.aws.amazon.com/AmazonS3/latest/dev/Versioning.html

1. Server Access Logs vs Object-level logging
    - https://acloud.guru/forums/aws-certified-solutions-architect-associate/discussion/-L5KnjS2mlyqPvuMu00f/Serve%20access%20logging%20vs%20Object-level%20logging

1. Requester pays
    - https://docs.aws.amazon.com/AmazonS3/latest/dev/RequesterPaysBuckets.html

1. Events
    - https://docs.aws.amazon.com/AmazonS3/latest/dev/NotificationHowTo.html

1. Static Website Hosting
    - https://docs.aws.amazon.com/AmazonS3/latest/dev/WebsiteHosting.html

1. Lifecycle Management
    - https://docs.aws.amazon.com/AmazonS3/latest/dev/object-lifecycle-mgmt.html

1. Cross Region Replication (CRR)
    - https://docs.aws.amazon.com/AmazonS3/latest/dev/crr.html
    - https://aws.amazon.com/about-aws/whats-new/2019/09/amazon-s3-introduces-same-region-replication/

1. Snowball and Snowmobile
    - https://aws.amazon.com/snowcone/ (8TB)
    - https://aws.amazon.com/snowball/ (50TB and 80TB)
    - https://aws.amazon.com/snowmobile/ (10 PB)
    - https://www.youtube.com/watch?v=H3_ZqnqLyVo (CNBC Video)
    - https://aws.amazon.com/blogs/publicsector/from-deserts-to-the-battlefield-aws-snowball-edge-brings-technology-to-the-tactical-edge/ (AWS Article)

1. S3 Intelligent Tiering
    - https://aws.amazon.com/about-aws/whats-new/2018/11/s3-intelligent-tiering/

1. Permissions in S3 (IAM vs Bucket Policy vs ACL)
    - https://cloudonaut.io/s3-security-best-practice/
    - https://aws.amazon.com/blogs/security/iam-policies-and-bucket-policies-and-acls-oh-my-controlling-access-to-s3-resources/

1. Optimizing Amazon S3 Performance
    - https://docs.aws.amazon.com/AmazonS3/latest/dev/optimizing-performance.html

# VPC

## Theory

1. What is VPC (logically isolated network)

1. Significance of VPC (Isolating environments, applications and customers)

1. Default and additional VPCs

1. Subnet within a VPC

1. VPC Peering for connectivity across VPCs

## Practicals (By Praveen)

1. Selecting the VPC and the Subnets while launching an EC2 instance for the sake of High Availability.

## Further Reading

1. VPC Peering
    - https://docs.aws.amazon.com/vpc/latest/peering/what-is-vpc-peering.html

1. VPC Flowlogs
    - https://docs.aws.amazon.com/vpc/latest/userguide/flow-logs.html

1. Traffic Mirroring
	- https://aws.amazon.com/blogs/aws/new-vpc-traffic-mirroring/

1. Transit Gateway (a better alternate to VPC Peering)
	- https://docs.aws.amazon.com/vpc/latest/tgw/tgw-getting-started.html
	- https://aws.amazon.com/blogs/networking-and-content-delivery/migrate-from-transit-vpc-to-aws-transit-gateway/
	- https://aws.amazon.com/blogs/aws/new-use-an-aws-transit-gateway-to-simplify-your-network-architecture/
	- https://www.youtube.com/watch?v=yQGxPEGt_-w/

# ELB (Elastic Load Balancer)

## Theory

1. What is an ELB and significance?

1. Routing algorithms in ELB (RoundRobin and WeightBased)

1. High Availability in ELB

1. Different types of ELB\
![](images/2020-11-05-10-45-38.png)\
https://www.geeksforgeeks.org/layers-of-osi-model/

## Practicals

1. In the Noon Session

## Further Reading

1. Different types of ELB
    - https://aws.amazon.com/elasticloadbalancing/details/#compare
    - https://www.sumologic.com/aws/elb/aws-elastic-load-balancers-classic-vs-application/
    - https://medium.com/containers-on-aws/using-aws-application-load-balancer-and-network-load-balancer-with-ec2-container-service-d0cb0b1d5ae5

1. Specific use cases for Private ELB?
    - https://docs.aws.amazon.com/elasticloadbalancing/latest/classic/elb-internal-load-balancers.html

1. How to configure SSL in ELB?
    - https://docs.aws.amazon.com/elasticloadbalancing/latest/classic/elb-create-https-ssl-load-balancer.html
    - https://docs.aws.amazon.com/elasticloadbalancing/latest/application/create-https-listener.html
    - https://docs.aws.amazon.com/elasticloadbalancing/latest/network/create-tls-listener.html

1. How do I set up weighted target groups for my Application Load Balancer?
    - https://aws.amazon.com/premiumsupport/knowledge-center/elb-make-weighted-target-groups-for-alb/

1. Limits of the ELB
    - https://docs.aws.amazon.com/elasticloadbalancing/latest/classic/elb-limits.html
    - https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-limits.html
    - https://docs.aws.amazon.com/elasticloadbalancing/latest/network/load-balancer-limits.html