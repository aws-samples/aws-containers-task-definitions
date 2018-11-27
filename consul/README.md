# Consul

Consul is a tool used for service discovery and configuration. It runs in a server mode or client mode.  In an ECS cluster it is recommended to run 1, 3 or 5 server instances depending on high availability requirements as well as the cluster size.  The 1 server mode configuration means the server is a single point of failure.  It may be sufficient for development environments.  For environments where availability is key 3 servers are recommended.  Very large clusters may require 5 servers to run in the ECS cluster.  
The server and client tasks need to run individually on each node.  There should not be a server and client tasks running on the same node within the ECS cluster.  
For example, in a 10 node cluster you would run 3 server tasks and 7 client tasks.

## Using these Task Definitions
These task definitions pull the maintained Consul image from [GitHub](https://github.com/hashicorp/consul).  
There are 2 Task Definitions; one for Consul server and one for Consul client.  
The Task Definitions also create CloudWatch logs.  The region specified in the Task Definition for CloudWatch logs is us-east-2.  The value can be changed to be used in different AWS regions.  
There are some Task Definition [constraints](http://docs.aws.amazon.com/AmazonECS/latest/developerguide/task-placement-constraints.html) required in order to make sure only one of the Consul server or client is deployed on each ECS node.

### Steps to Run:
* Have an active [AWS account](https://portal.aws.amazon.com/billing/signup#/start).
* Create an [Amazon ECS cluster](http://docs.aws.amazon.com/AmazonECS/latest/developerguide/create_cluster.html).
* Tag the instances in the cluster with:  
`key=consul value=member`
* These task definitions are templates that can then be pasted into the AWS console JSON input area or saved to a file and used with the AWS CLI.  To create the Task Definitions using CLI run the following commands.  
For Consul server:  
`aws ecs register-task-definition --cli-input-json file://<path_to_json_file>/ConsulServer.json`  
For Consul client:  
`aws ecs register-task-definition --cli-input-json file://<path_to_json_file>/ConsulClient.json`

* Run the task definition as a [Task](http://docs.aws.amazon.com/AmazonECS/latest/developerguide/scheduling_tasks.html) or [Service](http://docs.aws.amazon.com/AmazonECS/latest/developerguide/ecs_services.html).  There are some [constraints](http://docs.aws.amazon.com/AmazonECS/latest/developerguide/task-placement-constraints.html) that need to be set to run these tasks as the Consul server and client should not run on the same host.  
_Consul server:_  
For the "Task Placement" option choose: "One Task Per Host"  
_Consul client:_  
For the "Task Placement" option choose: "Custom"  
In the "Constraint" choose "DistinctInstance".  Add another constraint and for the second constraint choose "MemberOf" and for the expression add `not(task:group == task:consulServer)`

## More Info
#### What is a Task Definition?
A task definition is required to run Docker containers in Amazon ECS. Some of the parameters you can specify in a task definition include:

* Which Docker images to use with the containers in your task.
* How much CPU and memory to use with each container.
* The Docker networking mode to use for the containers in your task.

Please see the [Amazon ECS Documentation](http://docs.aws.amazon.com/AmazonECS/latest/developerguide/task_definitions.html) for more information on writing and running Task Definitions.

#### About Amazon ECS
Amazon EC2 Container Service (Amazon ECS) is a container management service that supports Docker containers and allows you to easily run applications on a managed cluster of Amazon EC2 instances. Amazon ECS eliminates the need for you to install, operate, and scale your own cluster management infrastructure. Learn more [here](https://aws.amazon.com/ecs).

#### Getting Help
* [Amazon ECS Documentation](http://docs.aws.amazon.com/AmazonECS/latest/developerguide/Welcome.html)
* [Amazon ECS Developer Forum](https://forums.aws.amazon.com/forum.jspa?forumID=187)
* [Stack Overflow](https://stackoverflow.com/questions/tagged/amazon-ecs)
* [AWS Support](https://aws.amazon.com/premiumsupport/)
