## Note: this is a simple fork from [Docker Official Image](https://github.com/docker-library/docker) with the [Ubuntu 18.04 image](https://hub.docker.com/_/ubuntu) for testing purposes and was tested only on x86_64.

### To build:

```bash
cd 19.03 && docker build --tag docker:19.03.8-ubuntu-18.04 .

cd dind && docker build --tag docker:dind-19.03.8-ubuntu-18.04 .
```

### To test:

```bash
docker run --privileged --name dind --rm -d docker:dind-19.03.8-ubuntu-18.04
docker exec -it dind bash

# inside the DinD container:

docker run --rm -it ubuntu:18.04

# inside the container inside DinD (Inception...):

apt update
apt install -y git apt-utils python3-pip python3.8-venv 

python3.8 -m venv test

source test/bin/activate

pip install git+https://github.com/will8211/unimatrix.git

unimatrix -c blue -s 97
```
