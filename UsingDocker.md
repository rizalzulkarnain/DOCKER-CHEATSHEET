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
run development: `docker run -it <filename>`
run background development `docker run -d <filename>`
run background with name `docker run --name <name_what_you_want> -d <filename>`
run background with name&port `docker run -d -p 3001:3000 --name <name_what_you_want> <filename>`
run production:`docker-compose -f docker-compose.prod.yml build`

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

# Docker Executing

list container active `docker ps`
docker exec list `docker exec <name_container/container_id> ls`
docker exec shell `docker exec -it <name_container/container_id> sh`
docker exec shell as root `docker exec -it -u root <name_container/container_id> sh`

# Docker Stop&Start Container

stop docker running `docker stop <container_ID>`
start docker `docker start <container_ID>`

# Docker Remove Container

remove `docker rm <container_ID>`
remove force `docker rm -f <container_ID>`

# Docker Volume

create volume `docker volume create app-data`
inspect volume `docker volume inspect app-data`
run docker with volume `docker run -d -p 4000:3000 -v <name_volume_what_you_want>:/app/data <filename>`
---- or -----------
run docker with volume `docker run -d -p 4000:3000 -v $(pwd):/app <filename>`

# Remove WorkSpace

remove all container `docker container rm -f $(docker container ls -aq)`
remove all image `docker image rm -f $(docker image ls -q)`

# Docker Compose

build `docker-compose build`
run `docker-compose up`
run background `docker-compose up -d`
stop `docker-compose down`
run&build production background `docker-compose -f docker-compose.prod.yml -d --build`

# Docker Compose Network

list network `docker network ls`
logs `docker-compose logs`

# Docker Machine

---Digital Ocean---
create `docker create \`
`--driver digitalocean \`
`--digitalocean-access-token <TOKEN>`
`--engine-install-url "https://releases.rancher.com/install-docker/19.03.9.sh" \ name;`
`<your_filename>`
list server running `docker-machine ls`
using ssh `docker-machine ssh <filename>`

# Docker Env

check `docker-machine env <filename>`
`eval $(docker-machine env <filename>)`

activate `docker-machine activate <filename>`
