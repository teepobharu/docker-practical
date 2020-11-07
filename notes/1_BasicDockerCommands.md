## Tips
docker run a...
- match ccclosest docker image ID
docker run --rm -d
- when stop auto remove the image

### VSCODE
- Plugins Docker
- Auto complete tag `FROM python:__`

# Basic Commands

## Build
```sh
docker build --tag repo:tag .
docker images 
docker image tag d583c3ac45fd myname/server:latest
# Stop Start


```
## Run
```sh
docker run -p 3000:80 -d --rm --name goalct goals:latest

# Attachment
## Attach to docker console.log will be printed and seen
docker run -p 8000:80 ID
docker start -a ID
## Detach mode
docker run -d 

docker attach ID
docker logs ID
docker logs --help
```

### Interactive
- Passed -it flag to get interact with input
```sh
docker run -it
docker start -a -i
```

# Clean up
```sh
# Images
docker rmi
docker image prune
# - remove all image w/o tags use -a to remove all
# Container
docker rm
```

# Copy files

```
docker cp <source> <container_name>:/path
# Local - Container
docker cp dummy/. boring_vaughan:/test
# Container - Local
docker cp boring_vaughan:/test dummy

```
- will create if not exists

# Dockerfile

Optimize for Caching 
- Only Allow node install to run when package file changes
- `COPY -> "."` indicate relative path from `WORKDIR`
```docker
FROM node:14

WORKDIR /app

COPY package.json /app

RUN npm install

COPY . .

EXPOSE 80

CMD ["node", "server.js"]
```