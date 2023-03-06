# Context

- `docker context list`

  Take note of the entry that has an asterisk (\*) next to it designates the current context.

- `docker version`

  Returns the docker information

- `docker image inspect`

  See the labels applied to any image

- `docker image build`

  Runs the build

  Using `docker image build` is functionally the same as using `docker build`.

- `docker image build --no-cache`

  Disables the cache for a build

- `docker image build --build-arg email=me@example.com`

  If we wanted to change a argumnt passed in the Dockerfile we could simply re-run the build, and provide a new value for the ARG via the --build-arg command line argument

- `docker container run` or `docker run`

  - Installing Ubuntu: `docker container run --rm -ti docker.io/ubuntu:latest /bin/bash`

  - Installing Fedora: `docker container run --rm -ti docker.io/fedora:latest /bin/bash`

  - Installing Alpine Linux: `docker container run --rm -ti docker.io/alpine:latest /bin/sh`

- `docker container ls`

  Verify containers running.

  Using `docker container ls` is functionally equivalent to using `docker container list`, `docker container ps`, or `docker ps`

- `docker container stop <CONTAINER ID>`

  Using the container ID from the previous output, you can stop the running container

  Using `docker container stop` is also functionally equivalent to using `docker stop`

- `docker system df`

  Docker objects accumulate over time, so with heavy usage you can eventually exhaust the available storage. You can confirm that this is the issue with this command.

  (https://stackoverflow.com/questions/48668660/docker-no-space-left-on-device-macos)

- `docker system prune`
  
  Prune everything

- `docker image prune`

  Only prune images

- `docker login`

  Log in to the Docker Hub registry

  The command `docker login` is functionally the same command as docker `login docker.io`

  If you were trying to log in to something other than the Docker Hub registry, you could supply the hostname on the command line: `docker login someregistry.example.com`

- `docker logout`

  Log out of a registry

# Example projects

- [Simulate Bitbucket pipeline](https://confluence.atlassian.com/bbkb/debug-pipelines-locally-with-docker-1167698072.html)

  - `docker build --memory=1g --memory-swap=1g -t account/imagename:tag -f parrot.dockerfile .`

  - `docker run -it --memory=4g --memory-swap=4g --memory-swappiness=0 --cpus=4 --entrypoint=/bin/bash account/imagename:tag`