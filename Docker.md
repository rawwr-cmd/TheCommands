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
## docker exec -it 99700 redis-cli (example)
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


