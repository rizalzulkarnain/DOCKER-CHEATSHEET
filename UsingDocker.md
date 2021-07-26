# Build Docker

development `docker build -t <filename> .`
production `docker build -t <filename> -f Dockerfile.prod .`

# Delete Image and Container Docker

list `docker images`
delete image `docker image prune`
delete container `docker container prune`
remove image `docker image rm <filename>:<name_tag>`

# Docker Tag

add tag `docker build -t <filename>:<name_tag>`
remove tag `docker image remove <filename>:<name_tag>`
change tag `docker tag <IMAGE ID> <filename>:<name_tag>`

# Docker Running

list container running `docker ps`
run development: `docker run <filename>`
run background development `docker run -d <filename>`\
run background with name `docker run --name <name_what_you_want> -d <filename>`
run background with name&port `docker run -d -p 3001:3000 --name <name_what_you_want> <filename>`
run production: `docker-compose -f docker-compose.prod.yml build`

# Docker Push to DockerHub

docker tag local `docker tag <IMAGE ID (3 char)/image_name> <name_respository>/<filename>:<name_tag>`
login `docker login`
push to docker hub `docker push <repository_name>/<filename>`

# Docker Saving dan Loaded another Machine

docker save `docker image save -o <filename>.tar <filename>:<name_tag>`
example: docker image -o react-app.tar react-app:1.0

docker load `docker load -i <filename>.tar`
example: docker load -i react-app.tar

# Docker Logs

logs `docker logs <Container_ID/image_name>`

# Executing in Docker

docker exec list `docker exec <name_container> ls`
docker exec sh `docker exec -it <name_container> sh`

# Docker Stop&Start

stop docker running `docker stop <container_ID>`
start docker `docker start <container_ID>`

# Docker
