# dockerhubimages

1.  Create the image
2.  Publish the image to docker hub
3.  Github actions

#### Imaprtent note

1.  In github need to add the environment variable docker userName and token.
2.  Docker hub token need to generate in docker hub under the myaccount -> security

```bash
# In github/workflow have the all the github action steps like branch, push to docker, docker credentials tags and context
```

### Ec2 Instance connect with github accetion

```bash
# create ec2 instance
# connect with ec2 instance cmd or putty etc
# Run below steps 1 to 8 install docker in ec2
# 1.sudo apt-get update
# 2.sudo apt-get install docker.io -y
# 3.sudo systemctl start docker
# 4.sudo docker run hello-world
# 5.docker ps
# 6.sudo chmod 666 /var/run/docker.sock
# 7.sudo systemctl enable docker
# 8.docker --version

# goto git hub actions https://github.com/prmalakoti/nodeaAutoDockerbuild/settings/actions/runners/new?arch=x64&os=linux
# run the all the commands from above stpes
# sudo ./svc.sh install
# sudo ./svc.sh start
# check the status : sudo ./svc.sh status
# stop the service : sudo ./svc.sh stop
# more info: https://docs.github.com/en/actions/hosting-your-own-runners/managing-self-hosted-runners/configuring-the-self-hosted-runner-application-as-a-service
```

### Push Docker image to docker hub

```bash
#create repo in hub.docker
1. docker push prashantmalakoti701/api-rate-limit
2. docker login -u prashantmalakoti701
3. docker images
4. docker tag apiratelimit-server(local image name) prashantmalakoti701/api-rate-limit(hub created repo name)
5. docker push prashantmalakoti701/api-rate-limit
```


 # Docker Summary

1. dockerignore
  `A file that lists files and folders to exclude from the Docker build context, speeding up builds and keeping images smaller.`

2. Dockerfile
`A text file with step-by-step instructions to build a Docker image for your app. It sets the base image, copies code, installs dependencies, and defines how to run the app inside a container.`

3.  Docker commands:

```
0. docker init
1. bash docker build -t image-name . — Build an image with a tag
2. docker run -p 4001:4000 image-name — Run a container, mapping ports
3. docker images — List all images
4. docker ps — List running containers
5. docker stop container_id / docker kill container_id — Stop a container
6. docker rm container_id — Remove a container
7.docker rmi image_id — Remove an image
```

4. docker-compose.yml
`A YAML config file for Docker Compose to define and manage multiple containers as services. It configures image building, networking, ports, volumes, environment variables, and service dependencies.`

5. Common Docker Compose commands:

```bash
1. docker-compose build — Build all services defined in compose file
2. docker-compose up -d [service] — Start containers in detached mode
3. docker-compose down — Stop and remove containers, networks
4. docker volume ls — List Docker volumes
```
