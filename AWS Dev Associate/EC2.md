EC2 is AWS cloud computing sevice. EC2 offers several services such as instances which are virtual machines, images are templates of instances can run multiple, Elastic Block Storage for virtual data storage. Network and Security , Load Balancing, and Auto Scaling. To securely connect to EC2 you need <font class="highlight-y">Key Pairs</font> to connect via SSH, and Windows AMI's.
```ad-warning
title: Test prep
To securely connect to EC2 you need <font class="highlight-y">Key Pairs</font> to connect via SSH, and Windows AMI's.
```

### EC2 User Data 
is used to automate boot cammands. using bootstrap to run commands when the machines boots up. Metadata is used to configure or manage the instance. They're a varity of Amazon Machine Images(AMI) to choose. Instances cna be assigned to IAM role for access. With Windows instance you can enable Elacsitc GPU. Use EFS to mount existing Filesystem. Also need to create a key pair for access.

### EC2 Instance Type
The diffrent types fo instances are omptimized for certain use cases. These instance types have a varying amount of CPU, memory, strorage, and network capacity. This is the instance type naming scheme "m5.2xlarge" The first letter is the instance calass what follows is the generation and afterthe is period is the sizeof the instance. They're 5 main categories General Purpose, Compure Optimized,  Memory Optimized, Accelerated Computing, and Storage Optimized.

### Security Groups
control the inbound and outbound traffic. Virtual Private Cloud(VPC) come with a security  group. Security Groups have allow rules which are the Protocal, Port range, ICMP type and code source or destination, and Description(optional). Look at docs for more.
```ad-info
title: Security Groups will not be on the Test
```

### Pricing Model
On-Demand
- Pay as you go no contract or commitment
- Great for auto scaling and unpredictable loads
- Flexible pricing with no upfront cost
Spot
- unused EC2 capacity in the cloud
- Its 90% cheper than on-demand pricing
- Price is determind by current demand for spot there's no bidding
- Spot gives you a two minute warning for when it needs the instance back
Reservered
- Puchase EC2 instance in advance for huge discount
- Capacity terms are 1 or 3 years
- Three ways to reserve schedule, standard, and convertible all different discounts
	- Standard - default no changes
	- Schedule - reserver for specific period of time hourly
	- Convertible - similar to standard, but make changes to instance
- used for steady perdictable work
- You get charege weather used or not






#AWS #AWS-compute #aws-developer-associate