## DOCKER

File name should be strictly <b>Dockerfile</b>

```bash
FROM python:3.8   #python 3.8 is taking from dockerhub repo
COPY . /app
WORKDIR /app
RUN pip install -r requirements.txt
CMD ["python", "app.py"]
```

In Terminal

```bash
docker build -t newimage .
docker run -d -p 5000:5000 newimage  #Detached mode. Type is Port
```

```bash
FROM ubuntu     
COPY . /tmp
WORKDIR /tmp
RUN echo "Hello World"
ENV myname akash       #Variable and value
ADD test.tar.gz /tmp   #ADD -> For unzipping files from local or internet(url) to tmp directory
```

In Terminal

```bash
docker build -t newimage .
docker run -it newcontainer newimage /bin/bash  #Interactive mode. Type is Bash
```

## Commands:

- To view the docker location, info and version
```bash
where docker
docker info
docker -v
```

- To view the image that was created
```bash
docker images
```

- To check the running containers
```bash
docker ps
```

- To check all the containers
```bash
docker ps -a
```

- To stop the containers running
```bash
docker stop container_id
```

## Ways to create an image
- Create image using Dockerfile
- Pull image from DockerHub
- Create image from Docker container itself.

- 1. To build a image (Using Dockerfile)
```bash
docker build -t myhelloapp .
```

- To run the docker image on the container (in detached mode)(Type: PORT)
```bash
docker run -d -p 5000:5000 myhelloapp
```

- Pushing the docker image to DockerHub
```bash
docker login
docker tag myhelloapp <username>/<reponame>
docker push <username>/<reponame>
```

- 2. Pulling the image from DockerHub (in interactive mode it provides terminal) (Type: Bash)
```bash
docker pull ubuntu
docker images
docker run -it ubuntu /bin/bash
```
Or we can directly run the image from DockerHub without pulling (Here anyways it will first check from the local DockerEngine and then goes for DockerHub) (Type: Bash)
```bash
docker run -it kalilinux/kali-rolling /bin/bash
```

- Running image directly from DockerHub (Type: Port)
```bash
docker run -p 8080:8080 jenkins/jenkins:lts
```

- 3. Create image from Docker container itself.
```bash
docker images #ubuntu is already there
docker run --name newcontainer -it ubuntu /bin/bash
docker ps -a
docker diff newcontainer
docker commit newcontainer newimage
docker images  #Now newimag will be created
```

- To delete the image (Use -f to forcefully delete the image)
```bash
docker rmi <imagename>
```
Or if tag is different from latest
```bash
docker rmi <imagename>:<tag>
```