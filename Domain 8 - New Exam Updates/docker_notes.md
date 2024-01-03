# Basic Docker commands

```sh
docker images
docker ps
docker run -dt -p 80:80 nginx
docker stop <name>
docker ps -a
docker container stop $(docker container ls -aq)
docker container remove strange_bassi
docker rmi <container_id> # To remove image
```

# some network related command

```sh
netstat -ntlp
curl -I 128.199.15.89:80

# to create files of size
dd if=/dev/zero of=/root/file1.txt bs=1M count=100 

# to look the size
du -sh /root/file1.txt 
```


# Tagging the image

```sh
docker build -t demo:v1 .
docker tag 4c0f1374cc4d demo:v2
docker tag ubuntu:latest myubunt:v1
```
# Committing the container

```sh
docker container commit mybusybox busybox-modified-01
```
# Looking at layers number of layers
```sh
docker image history ubuntu
```
# moving the docker image around
```sh
docker save busybox > busybox.tar
docker load < busybox.tar
```
nano Dockerfile

```sh
FROM ubuntu
RUN apt-get update
RUN apt-get -y install nginx
CMD ["nginx", "-g", "daemon off;"]
```