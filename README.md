### DOCKER

## File name should be strictly Dockerfile

```bash
FROM python:3.8   #python 3.8 is taking from dockerhub repo
COPY . /app
WORKDIR /app
RUN pip install -r requirements.txt
CMD ["python", "app.py"]
```

## Commands:

- To build a image
```bash
docker build -t myhelloapp .
```
- To view the image that was created
```bash
docker images
```

- To run the docker image on the container
```bash
docker run -d -p 5000:5000 myhelloapp
```
- To check the containers
```bash
docker ps
```

- To stop the containers running
```bash
docker stop container_id
```