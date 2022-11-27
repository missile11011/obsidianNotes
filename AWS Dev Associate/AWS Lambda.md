Aws Lambda lets you run code wihtout provisioning or manging servers. Serverless compute architechture where AWS handles the servers. Lambda Function contains your code and it's dependencies. Configuration when creating function. API provided for updated configuration data.
You set the amount of memory needed. AWS Lambda allowcates CPU Power based on memory with the same ratio as the General Purpose EC2. 

Functions can access the following:
- AWS services or non-AWS services
- AWS service running in VPC's (e.g. RedShift, Elasticache, RDS instances)
- Non-AWS services running on EC2 instances in an AWS VPC
To have a Lambda function to access resources inside a private VPC you need to setup additional VPC configuration that inclueds VPC subnet and security group IDs. There is a  maximum execution timeout the max is 15 minutes, and the default is 3 seconds. Lambda is a pay as it runs serviec, and terminates the function at timeout. Lambda takes and IAM role when it runs a function. Lambda has continuous scaling only scaling out. Lambda functions are serverless and independent. One function can trigger other functions so one event can trigger multiple functions.

Use Lambda if it falls in one of the use cases:
- Using Lambda functions with AWS serivces as event sources.
- On-demand Lambda function invocation over HTTPS using Amazon API gateway (costom REST API and endpoints)
- On-demand Lambda function invocation using custom applications ( mobile, web apps, clients ) and AWS SDK's, AWS Mobile SDK's, and AWS Mobile SDK's for Andriod.
- Scheduled events can be configured to run code on a scheduled basis through the AWS Lambda Console.

Configure other AWS servies to invoke a Lambda function or configure the lambda funtction to from a queue then invoke then function. There's two ways to run a Lambda function synchronously or asynchronously. Synchronous is when wait for each process to be done then rerturns output. Asynchronsous doesn't wait for function it just completes the action. 

To invoke synchronous with AWS CLI  
``` AWS CLI
$ aws lambda invoke --function-name my-function --payload '{ "key": "value" }' response.json { "ExecutedVersion": "$Lastes", "StatusCode": 200}
```

To invoke asynchronous with AWS CLI:
``` AWS CLI
$ aws lambda invoke --function-name my-function --invocation-type Event --payload '{ "key": "value" }' response.json
```

### Event Source Mappping
Event Source Mapppingis an event driven service and response to changes to data. You can use event source mapping to proccess items in a queue or stream. Event source mapping procceses items in order and use batches to keep the data recived before it processes it. Error handling is basic if there's an error the function is retries until the it succeeds or it times out. 

### Lambda Versions / Aliases
Lambda versions is self-explanitory you can have multiple versions of the your function. For example you can have a version for development and testing while it doesn't affect the production version. The versions contain the following information.
- The function code and all associated dependencies
- The Lambda runtime that executes it
- All the functions settings, including env variales
- A unique Amazon Resource Name (ARN) to identify it
You can only edit the $latest version of the function. Once the chnages are made you can publish the function which creates a new version of it. The versions can't be changed. For Lambda Aliases you need a qualified ARN.

Lambda aliases are pointers that point to a specific function. It also enables blue/green deployment by using weights. Blue green deployment deploys gradually transfers user traffic from a previous version to a new release. Aliases has its own ARN and it can't refrence another aliases.

### Concurrency
Lambda function invokes a new instacne and if the first is still not complete it opens an other instance side by side. The functions cumulative concurrency (the number of instance running) is Region based. Burst concurrency limits varie. Lambda functions needs a IAM role with permission to SNS/SQS.
- Resevered concurrency sets the number of executions the will be available for the function. Reserver up to the unreserved account value and to throttle set reserved to zero.
- Provisioned concurrency 
#AWS #AWS-compute #aws-developer-associate 