# PwnDocker

## About

ubuntu environment docker file for ctf player with pwnable

Various tools are installed in each environment to help with pwnable analysis.

(etc. GDB, pyhon, pwntools, tmux, ropgadget, ruby, one_gadget, seccomp-tools)

## Build

```python
# example of building ubuntu18.04

git clone https://github.com/kmm2003/PwnDocker.git

cd ubuntu18.04

docker build --tag ubuntu:18.04 .
```

- Build your own version of docker environment.

## Create container

- If you are using a build environment for the first time, create containers and run the shell in the same order as above.

```python
└─# docker images                                  
REPOSITORY   TAG       IMAGE ID       CREATED         SIZE
ubuntu       18.04     f3035e24529b   22 hours ago    1.09GB
```

```python
docker run -it --network=host f3035e24529b bash
```

## Execute shell

- If it's not your first time using it

```python
└─# docker ps -a                                   
CONTAINER ID   IMAGE          COMMAND   CREATED        STATUS                      PORTS     NAMES
b67eae440493   f3035e24529b   "bash"    22 hours ago   Exited (139) 15 hours ago             kind_elion
```

```python
docker start kind_elion

docker attach kind_elion
```

- Find the name of the container with the command "docker ps -a" and run the start → attach command.

## **Transfer files from host to container**

```python
# docker cp [filename] [container_name]:[container_path]
ex) docker cp ./prob kind_elion:/root
```

- Move the self file to the ubuntu environment as above and start analysis!