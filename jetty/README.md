# Jetty
Eclipse Jetty is a Web server and javax.servlet container, plus support for HTTP/2, WebSocket, OSGi, JMX, JNDI, JAAS and many other integrations.

Eclipse Jetty 9 (as well as 7 and 8) is dual licensed under the Apache License 2.0 and Eclipse Public License 1.0. Eclipse Jetty is free for commercial use and distribution under the terms of either license, with exceptions listed in the NOTICE file.
Learn more: [https://www.eclipse.org/jetty/licenses.html](https://www.eclipse.org/jetty/licenses.html)

## Using this` Task Definition
This task definition pulls the official Jetty image from [DockerHub](https://hub.docker.com/_/jetty/) and boots the servlet engine without any deployed application. This means, you'll receive a HTTP 404 error if you access Jetty on port 8080. 

### Steps to Run:
* Have an active [AWS account](https://portal.aws.amazon.com/billing/signup#/start).
* Create an [Amazon ECS cluster](http://docs.aws.amazon.com/AmazonECS/latest/developerguide/create_cluster.html).
* This task definition is a template that can then be pasted into the AWS console JSON input area or saved to a file and used with the AWS CLI. You can easily replace the existing Docker image in this task definition with your own.
* Run the task definition as a [Task](http://docs.aws.amazon.com/AmazonECS/latest/developerguide/scheduling_tasks.html) or [Service](http://docs.aws.amazon.com/AmazonECS/latest/developerguide/ecs_services.html).

#### ECS CLI Commands
`aws ecs register-task-definition --cli-input-json file://<path_to_json_file>/jetty.json`

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