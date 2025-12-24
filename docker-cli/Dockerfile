# Use a public base image from Docker Hub
FROM alpinelinux/docker-cli:latest-aarch64

# Upgrade apk files
RUN apk update && apk upgrade

# Copy the local file into the container
COPY .ashrc /root
