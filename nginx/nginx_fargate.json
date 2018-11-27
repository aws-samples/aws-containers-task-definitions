{
  "requiresCompatibilities": [
    "FARGATE"
  ],
  "containerDefinitions": [
    {
      "name": "nginx",
      "image": "nginx:latest",
      "memory": 256,
      "cpu": 256,
      "essential": true,
      "portMappings": [
        {
          "containerPort": 80,
          "protocol": "tcp"
        }
      ],
      "logConfiguration":{
            "logDriver":"awslogs",
            "options":{
               "awslogs-group":"awslogs-nginx-ecs",
               "awslogs-region":"us-east-1",
               "awslogs-stream-prefix":"ecs"
            }
      }
    }
  ],
  "volumes": [],
  "networkMode": "awsvpc",
  "placementConstraints": [],
  "family": "nginx",
  "memory": "512",
  "cpu": "256"
}
