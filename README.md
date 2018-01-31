# Docker

```bash
$ cd
$ git clone https://github.com/pkmital/CycleGAN.git
$ cd CycleGAN
$ docker build -t cyclegan .
$ docker run -it -p 8888:8888 -p 6006:6006 -v /$(pwd):/notebooks --name tf cyclegan /bin/bash
```

If you need to relaunch the docker image again, you can write:

```bash
$ cd
$ cd CycleGAN
$ docker start -i tf
```

If you want to use a GPU version, and have a Linux machine, and have an NVIDIA GPU, you can use nvidia-docker (this only works for Linux machines! for non-Linux machines that want to use GPU, please follow the expanded directions below, or the quickstart pip installation above):

```bash
$ wget -P /tmp https://github.com/NVIDIA/nvidia-docker/releases/download/v1.0.0-rc.3/nvidia-docker_1.0.0.rc.3-1_amd64.deb
$ sudo dpkg -i /tmp/nvidia-docker*.deb && rm /tmp/nvidia-docker*.deb
$ nvidia-docker build -t cyclegan-gpu -f Dockerfile-gpu .
$ nvidia-docker run -it -p 8888:8888 -p 6006:6006 -v /$(pwd):/notebooks --name tf cyclegan-gpu /bin/bash
$ nvidia-docker start -i tf
```
