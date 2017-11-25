# Task Definitions for Amazon ECS
This repository holds [task definitions](#what-is-a-task-definition), small blueprint files that tell [Amazon EC2 Container Service (Amazon ECS)](https://aws.amazon.com/ecs) how to deploy containers on a managed cluster of Amazon EC2 instances. Task definitions are a core component of using Amazon ECS to run containerized applications.

The task definitions in this repository are for popular applications whose code images are publicly available, well-documented, and maintained.

## Directory
 * [nginx](/nginx)
 * [Wildfly](/wildfly)
 * [Tomcat](/tomcat)
 * [Gunicorn](/gunicorn)
 * [Kibana](/kibana)
 * [Jetty](/jetty)

## Getting Started
To run task definitions in this repository you must:
1. Have an active AWS account. If you don't have an active AWS account, you can sign up [here](https://portal.aws.amazon.com/billing/signup#/start).
2. Have a running Amazon ECS cluster. You can learn how to start using Amazon ECS [here](https://aws.amazon.com/ecs/getting-started/).

Once you have an active account and a running cluster, follow [these steps](http://docs.aws.amazon.com/AmazonECS/latest/developerguide/create-task-definition.html) to build your task definition.

You can then run the Task Definition as a [Task](http://docs.aws.amazon.com/AmazonECS/latest/developerguide/scheduling_tasks.html) or [Service](http://docs.aws.amazon.com/AmazonECS/latest/developerguide/ecs_services.html).

### What is a Task Definition?
A task definition is a set of instructions that tells Amazon ECS how to run Docker containers. Task definitions are written in [JSON](http://www.json.org/) or manually configured through the AWS Management Console. Some of the parameters you can specify in a task definition include:

* Which Docker images to use with the containers in your task.
* How much CPU and memory to use with each container.
* The Docker networking mode to use for the containers in your task.

Please see the [Amazon ECS Documentation](http://docs.aws.amazon.com/AmazonECS/latest/developerguide/task_definitions.html) for detailed information.

### Getting Help
* [Amazon ECS Documentation](http://docs.aws.amazon.com/AmazonECS/latest/developerguide/Welcome.html)
* [Amazon ECS Developer Forum](https://forums.aws.amazon.com/forum.jspa?forumID=187)
* [Stack Overflow](https://stackoverflow.com/questions/tagged/amazon-ecs)
* [AWS Support](https://aws.amazon.com/premiumsupport/)

### About Amazon ECS
Amazon EC2 Container Service (Amazon ECS) is a container management service that supports Docker containers and allows you to easily run applications on a managed cluster of Amazon EC2 instances. Amazon ECS eliminates the need for you to install, operate, and scale your own cluster management infrastructure. Learn more [here](https://aws.amazon.com/ecs).
