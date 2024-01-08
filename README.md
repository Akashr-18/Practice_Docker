## File name should be strictly Dockerfile

FROM python:3.8   #python 3.8 is taking from dockerhub repo
COPY . /app
WORKDIR /app
RUN pip install -r requirements.txt
CMD ["python", "app.py"]

## Commands:

#To build a image
docker build -t myhelloapp .
#To view the image that was created
docker images

#To run the docker image on the container
docker run -p 5000:5000 myhelloapp
#To check the containers
docker ps

#To stop the containers running
docker stop container_id