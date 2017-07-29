![Sample image of  nodes with data](./nodes.png)

# Docker Swarm Visualizer

*** note ***
_This only works with Docker Swarm Mode in Docker Engine 1.12.0 and later. It
does not work with the separate Docker Swarm project_

This project is a fork of [dockersamples/docker-swarm-visualizer](https://github.com/dockersamples/docker-swarm-visualizer),
using `node:4.*-alpine` as a base image so we could get far smaller image
(370MB to 170MB).
It also removes dev dependencies from the docker image, so we could get even
more smaller image (170MB to 70MB)

## Usage

To run in a docker swarm:

```
$ docker service create \
  --name=viz \
  --publish=8080:8080/tcp \
  --constraint=node.role==manager \
  --mount=type=bind,src=/var/run/docker.sock,dst=/var/run/docker.sock \
  herloct/swarm-visualizer
```

Please refer to [dockersamples/docker-swarm-visualizer](https://github.com/dockersamples/docker-swarm-visualizer)
for more detailed information.
