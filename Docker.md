docker -v
sudo aa-status
sudo ls -la /var/run/docker.sock
systemctl status docker

docker container rm 3e657ae9bd16
docker container ls -a
docker container pause 832
docker container unpause 832
docker container stop 832
docker container inspect ff521fa58db3
docker container prune
docker container ls
docker logs c2ba

docker images
docker pull mysql
docker search mysql
docker image history 100229ba687e
docker image inspect 100229ba687e
docker image remove mysql
