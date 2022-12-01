## docker -v
## docker --help
## docker version (to see the info ab virtual machine)
## sudo aa-status
## sudo ls -la /var/run/docker.sock
## systemctl status docker

## docker container rm 3e657ae9bd16
## docker rm 2af
## docker container ls -a
## docker container ls
## docker ps (list all the running container)
## docker ps -a
## docker container pause 832
## docker container unpause 832
## docker container start 832
## docker create imageName (creating a container)
## docker start containerIdOrName
## docker start -a 832 (adding 'a' will watch the output coming from container) 
## docker stop 832
## docker restart 832 (Restart one or more containers)
## docker container stop 832
## docker container inspect ff521fa58db3
## docker container prune
## docker system prune -a
## docker system prune 
## docker container ls
## docker logs c2ba


## docker images
## docker run imageName (creating and running container from an image)
## docker run busybox echo hi (these commands are available in the busybox)
## docker run busybox ls  (these commands are available in the busybox)
## docker run busybox ping google.com (these commands are available in the busybox)
## docker pull mysql
## docker search mysql
## docker image history 100229ba687e
## docker image inspect 100229ba687e
## docker image remove mysql
## docker run -d -p 5001:8080 in28min/hello-world-rest-api:0.0.1.RELEASE
