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
## docker kill 832 (to force stop the container)
## docker restart 832 (Restart one or more containers)
## docker container stop 832
## docker container inspect ff521fa58db3
## docker container stats 4faca1ea914e3e4587d1d790948ec6cb8fa34f26e900c12632fd64d4722fd59a
## docker stats 42f170966ce613d2a16d7404495af7b3295e01aeb9142e1fa1762bbdc581f50
## docker container prune (WARNING! This will remove:
  - all stopped containers
  - all networks not used by at least one container
  - all dangling images
  - all dangling build cache)
## docker system prune -a (WARNING! This will remove:
  - all stopped containers
  - all networks not used by at least one container
  - all images without at least one container associated to them
  - all build cache)
## docker system prune 
## docker container ls
## docker logs c2ba
## docker exec -it <container_id> <command to execute> (execute an additional command in a container, -it: allow us to provide input to the container, to provide input, -i: stdin i.e stuff i type, -t: stdin and stdout comes out in a nicely formatted manner on the screen)
## docker exec -it 99700 redis-cli (example, works only when container is running)
## docker exec -it <container_id> sh (getting a command prompt, shell inside a container)
    -echo hi
    -export b=7
    -echo $b
    -redis-cli
#### ctrl + d  (to get out of the terminal)
## docker run -it busybox sh (starting with a shell)


# ----------------------------------------------------------------------

## docker images
## docker run imageName (creating/installing an image and running container from an image)
## docker run busybox echo hi (these commands are available in the busybox)
## docker run busybox ls  (these commands are available in the busybox)
## docker run busybox ping google.com (these commands are available in the busybox)
## docker pull mysql
## docker search mysql
## docker image history 100229ba687e
## docker image inspect 100229ba687e
## docker image remove mysql
## docker run -d -p 5001:8080 in28min/hello-world-rest-api:0.0.1.RELEASE

# ------------------------------------------
## docker system
## docker system df
## docker system info

# ------------------------------------------
 
## Building an image example

### Use an existing docker image as a base (base image)
FROM alpine

### Download and install a dependency from alpine because alpine has a package manager(apk)
### cached version used if we are running the second time without changing anything
RUN apk add --update redis
RUN apk add --update gcc

### Tell the image what to do when it starts as a container
CMD ["redis-server"]

## ---------------------------------------------------building an image-------------------------------------------
### docker build .
## docker run 9d86
## docker build -t dockerId/myrepo:(version) .
###  docker build -t chipmunkey/anynameofmychoice:latest .      (example)
###  docker build -t chipmunkey/hello-world-java:0.0.2.RELEASE . (. specifies the directory of files/folders to use for the build, t for tagging)
### docker run chipmunkey/anynameofmychoice                      (latest version of the image will be used by default)
### docker compose -f docker-compose.dev.yaml up -d
### docker compose -f docker-compose.dev.yaml ps
### docker compose -f docker-compose.dev.yaml stop
### docker compose -f docker-compose.dev.ymal exec react_project bash
