ECS is a container manager for Docker contianers. ECS can be used to schedule containers based on resources and availablity requirments. Thers's no cost for using ECS only the instances or target or configuration Task. You can use load balancer with ECS only the instances or tragets or configuration Task. You can use load balancer with ECS. AMI can be used that meet amazon's ECS AMI specification. Look up [Amazon ECS-optimized AMI - Amazon Elastic Container Service](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/ecs-optimized_AMI.html) for more details.
### ECS VS EKS
EKS is a container service for Kubernetes to mange and scale containers. EKSand ECS are both manged, highly available, highly scalable container platforms. ECS supports Docker containers, and EKS is for Kubernetes so its's easy to move to another deployments. ECS is simplier and easier than EKS, but EKS has more features. ECS can take advantage of AWS services while a Kubernetes platform handles things internally. ECS "Task" are containered instances and are a bit isolated. EKS "Pods" are continers that are arranged collectice that sharee access to each other. ECS has limited extensiblity, but EKS is extensible it has third party and community add-ons.
### Launch Type
ECS Launch Types are the type of infrastructure for the tasks and services are hosted on. They're two Launch Types Amazon EC2 and Amazon Fargate. Amazon EC2 provision instances, reponsibility of upgrading patching, and taking care of EC2 pool on youl You also hace to take of cluster optimization. You also have more control over the EC2 infrastructure. Fargate automactically provisions resources and provisions compute as needed. Fargate handles optimization, and because fo that control is limited since it's automated
### Tasks and Task Definations
are required to run a Docker container in ECS. Task Definition is a JSON formated text file that describes one ro more containers. Docker images are used to launch contianers. 
These are some of the parameters for Task Definition: 
- The Docker image for each container in your Task
- How much CPU and memory for each task
- The Launch Type to host on
- Logging configuration to use for Tasks
- If the task continues if the container fails or finishes
- The commands the container runs on start
- Any data volumes that the container uses
- The IAM role the task uses

### Cluster Auto Scaling
ECS resource type Capacity Provieder can be used Auto Scaling Groups. When using Capacity Provider with Auto Scaling groups ECS cluster can scale automatically using two features.
Managed Scaling: creates scaling policy on ASG, and scaling metric Capacity Provider.
Managed instacne termination protection enables containers to know when an instance is terminated in the ASG.
### ECS with Beanstalk
offers both single-containers and multi-container: 
-  Single-container platform can be used to deploy a Docker Image(using Dockerfile or Dockerrun.aws.json) and the EC2 isntance source code. Deploys one image per instacne.
- Multi-container use ECS to coordinate the deployment of multiple Dcoker images to a ECS cluster in Elastic Beanstalk enviroment. Elastic Beanstalk create the following. ECS clusters, EC2 continer instance, Load Balancer, and Taks and executions. Requires a configuration file "Dockerrun.aws.json"
### ECR
is a Docker container registry that stores, manges, and deploys Docker images. ECR host images in a highly available and scable way. Which allows you to reliably deploy continaers.

#AWS #aws-developer-associate #AWS-compute 
