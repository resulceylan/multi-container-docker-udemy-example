[Udemy Docker and Kubernates Course](https://www.udemy.com/course/docker-and-kubernetes-the-complete-guide/learn/lecture/11437358)

# Notes:

## Docker
- docker system prune => deletes all containers

- docker logs <container-id> => shows internal logs

- docker stop <id> => does some clean ups
- docker kill <id> => no clean ups, kills immediately

- docker exec -it <id> sh => starts an sh terminal inside docker. type _CMD+D_ to exit

- docker build -t <your-docker-id/project-name:version> => tag your docker image

- docker run -p incoming-port:inside-docker-port <image-name> => Opening a port happens at runtime.

## Docker compose
- everything you put under services tag is actually a type of container

- docker-compose up --build => builds all images

- docker-compose up -d => starts in background

- docker-compose down => stops all containers under docker-compose.yml

- docker-compose ps => like docker ps, shows stats of of all containers under docker-compose.yml

- for development we create Dockerfile.dev files. To create images from those files docker build -f Dockerfile.dev .  (-f (docker file name))

- While mapping volumes, when we say _-v $(pwd):/app_it means map all files under _/app_ to present working directory. If there are files or folders under /app which does not have correspondence (like node_modules) then you get an exception. In this case, we add _-v /app/node_modules_ (no ":"), which means "Don't try to map against anything"

- docker run -it <container-id> npm run test => runs tests for angular or react like apps inside docker.

- docker attach <container-id> => attaches to stdin/stdout primary process

