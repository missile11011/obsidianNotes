EBS Volumes are network attached storage connected to an instance. You can attache a volume to one instance or more but with restriction or have the volume not be attached to an instance at all.
EBS volumes have to be in the same Availablity Zone as the instance. Volumes are replicated to other servers in the same AZ. Root EBS are deleted on the termination of the instance. <font class="highlight-m">This action can be changed with the "DeleteOnTermination" attribute possible test question.</font> You can move volumes across AZ creating an EBS Snapshot(backup) and creating a new volume with the Snapshotin the diffrent AZ. A Snapshot is just a copy or backup from a point in time doesn't change.
<font class="h3 highlight-b">Amazon Machine Images(AMI):</font> are templates for instance. Each AMI has everything needed to launch a EC2 instance. AMI  includes the OS, configuration and software packages.
<font class="h3 highlight-b">Instance Store:</font> is disk storage attached to the host computer. Instance Store is high performance tempory storage. It's ideal for buffers Cache, Sratch Data, and temporary content. Also good for data that replicated across many instance. <font class="highlight-m">Look out for questions that mention destributed or replicated databases with high I/O. Also the cost of the instance storeis included with instance charge.</font>
<font class="h3 highlight-b">Multi-Attach:</font> allows you to attach Provisioned IOPS SSD to multiple instances that are in the same Availability Zone. Each instance has read and write permission to the shared instances. Mulit-Attach makes achiveing higher application availablity in clustered Linux application.
#AWS #AWS-compute #AWS-developer-associate
