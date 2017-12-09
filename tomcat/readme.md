# Apache Tomcat
The Apache Tomcat® software is an open source implementation of the Java Servlet, JavaServer Pages, Java Expression Language and Java WebSocket technologies. 
The sources and documentation are distributed under the 2-clause BSD-like license.
Learn more: http://tomcat.apache.org/

The Apache Tomcat software is developed in an open and participatory environment and released under the Apache License version 2. 

## Using this Task Definition
This task definition pulls the maintained tomcat image from [DockerHub](https://hub.docker.com/_/tomcat/).

### Steps to Run:
* Have an active [AWS account](https://portal.aws.amazon.com/billing/signup#/start).
* Create an [Amazon ECS cluster](http://docs.aws.amazon.com/AmazonECS/latest/developerguide/create_cluster.html).
* This task definition is a template that can then be pasted into the AWS console JSON input area or saved to a file and used with the AWS CLI.
* Run the task definition as a [Task](http://docs.aws.amazon.com/AmazonECS/latest/developerguide/scheduling_tasks.html) or [Service](http://docs.aws.amazon.com/AmazonECS/latest/developerguide/ecs_services.html).

#### ECS CLI Commands

To register the task definition, download the json file from this repo and save at some loction on the local disk on your machine. Then run the below command from the command line. You wil need to have the aws cli already configured in order to run this command. Please follow the instructions to setup AWS CLI are [here](http://docs.aws.amazon.com/cli/latest/userguide/installing.html).

Note - This task definition assumes that you have a CloudWatch Log Group named 'tomcat-container-logs' already created. If you want to write to a different Log Group, then change the task definition accordingly. 

`aws ecs register-task-definition --cli-input-json file://<path_to_json_file>/tomcat-task-def.json`


To run one instance of this task on an existing ECS Cluster:

`aws ecs run-task --cluster <YOUR_CLUSTER_NAME> --task-definition tomcat-webserver:1 --count 1`

Replace the <YOUR_CLUSTER_NAME> with the actual name of your ECS cluster. Also, if you have changed the name of the task, then change the same in the above command accordingly.

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
