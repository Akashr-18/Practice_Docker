## DOCKER

File name should be strictly <b>Dockerfile</b>

```bash
FROM python:3.8   #python 3.8 is taking from dockerhub repo
COPY . /app
WORKDIR /app
RUN pip install -r requirements.txt
CMD ["python", "app.py"]
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

- To build a image
```bash
docker build -t myhelloapp .
```

- To run the docker image on the container (in detached mode)
```bash
docker run -d -p 5000:5000 myhelloapp
```

- To stop the containers running
```bash
docker stop container_id
```

- Pushing the docker image to DockerHub
```bash
docker login
docker tag myhelloapp <username>/<reponame>
docker push <username>/<reponame>
```

## Ways to create an image
- Create image using Dockerfile
- Pull image from DockerHub
- Create image from Docker container itself.

- Pulling the image from DockerHub (in interactive mode it provides terminal) 
```bash
docker pull ubuntu
docker images
docker run -it ubuntu /bin/bash
```
Or we can directly run the image from DockerHub without pulling (Here anyways it will first check from the local DockerEngine and then goes for DockerHub)
```bash
docker run -it kalilinux/kali-rolling /bin/bash
```

- To delete the image (Use -f to forcefully delete the image)
```bash
docker rmi <imagename>
```
Or if tag is different from latest
```bash
docker rmi <imagename>:<tag>
```