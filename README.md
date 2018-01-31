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
