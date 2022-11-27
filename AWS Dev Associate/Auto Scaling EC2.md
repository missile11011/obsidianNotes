Auto Scaling monitors the application, and adjusts capacity. Some services to use Auto Scaling for [[EC2]], ECS, Dynamo DB, and Aurora. Auto Scaling Groups(ASG) <font class="highlight-m">scales in and out</font> <font class="highlight-y">EC2 instances using scaling Policy</font>. Other features fo ASG health checks to monitor EC2 instances, and replace unhealthy EC2 instances. ASG reachs the desired capacity by ensuring a minimum, and maxium instances. There's no cost for using ASG only the instacnes it launchs. <font class="highlight-y">Launch template describe the instacne configuration, and it includes everything to run an instances.</font> It includes AMI, instance type, Key pairs, sercurity group, and other perameters. All used to launch EC2 instances. For monitoring ASG sends data to CloudWatch every minute. Use CloudWatch alarms to monitor metrics. Can use Scaling Policy based on the alarms to scale in or out.
### Scaling Options
They're several ways to scale ASG. They're four main options. Options(Maintain, Manaul, Schedule, Dynamic, and Predictive). 
- Maintain: maintains the number fo instances running at all time. 
- Manual: is the most basic uses minimum, maxium, or fixed instances to scale. 
- Schedule: increases, or decreases capacity based on time and date
- Dynamic: scales based on changing demand based on system changes like resources or metric.
- Perdictive: use ML to change capacity in advance of daily and weekly traffic patterns.
### Lifecycle Hooks
Lifecycle Hooks are activated when an instance is in a wait state. On scaling in or out(creating or termenating) the instance the Lifecycle Hooks put in a wait state(Pending: wait or Terminating: wait). Then the hook runs it's action. The instance stays in it's wait state until the Hook completes it's action or it times out. Once the Lifecycle Hook is done it enters in its "In Service" mode or gets "Terminated".
#AWS #AWS-compute #aws-developer-associate 