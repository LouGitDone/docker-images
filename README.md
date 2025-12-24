# Steps for create 
mkdir firstdocker
cd firstdocker/
nano index.html
nano Dockerfile

# Building webserver in local folder
docker build -t my-nginx-image:1.0 .
docker ps
docker images

# Run image
docker run -p 8080:80 --name my-web-container my-nginx-image:1.0

# Stop image
docker stop 4d884c8db882

# Remove container
docker ps -a
docker rm c6a055556127703d4671b03ab1b4e4cc6afd43131b1de06f3bde6e901453558a

# Run container interactively
docker run -it --name firstdocker my-nginx-image:1.0 ash

# Commit changes to docker after interactive
docker commit firstdocker my-nginx-image:1.0

# Push to Dockerhub
docker login
docker tag my-nginx-image:1.0 loufrankel/my-nginx-image
docker push loufrankel/my-nginx-image

# Remove unused images
docker image prune
docker rmi lou:latest
docker image prune -a
docker build -t my-nginx-image:1.0 .
# docker-images
# docker-images
