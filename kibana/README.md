# Kibana
Kibana is an open source plugin for Elasticsearch which can be used to visualize Elasticsearch data and navigate the Elastic Stack. Core Kibana ships with histograms, line graphs, pie charts, sunbursts, and more.

The sources and documentation are distributed under the Apache License, Version 2.0.
Learn more: [https://www.elastic.co/products/kibana](https://www.elastic.co/products/kibana)

## Using this Task Definition
This task definition pulls the maintained Kibana image from [DockerHub](https://hub.docker.com/_/kibana/).

### Steps to Run:
* Have an active [AWS account](https://portal.aws.amazon.com/billing/signup#/start).
* Create an [Amazon ECS cluster](http://docs.aws.amazon.com/AmazonECS/latest/developerguide/create_cluster.html).
* This task definition is a template that can then be pasted into the AWS console JSON input area or saved to a file and used with the AWS CLI. It is imortant to replace the <ES-URL>-part of this task template with an actual Elasticsearch-URL.
* Run the task definition as a [Task](http://docs.aws.amazon.com/AmazonECS/latest/developerguide/scheduling_tasks.html) or [Service](http://docs.aws.amazon.com/AmazonECS/latest/developerguide/ecs_services.html).

#### ECS CLI Commands
`aws ecs register-task-definition --cli-input-json file://<path_to_json_file>/kibana.json`

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