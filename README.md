# PwnDocker

## About
Ubuntu Environment Docker File for pwnable ctf player

Various tools are installed in each environment to help with pwnable analysis.

(etc. GDB, pyhon, pwntools, tmux, ropgadget, ruby, one_gadget, seccomp-tools)

## Build
```bash
# example of building ubuntu18.04

git clone https://github.com/kmm2003/PwnDocker.git

cd ./PwnDocker

./build 18.04 # ex) ./build [version]

```

- Easy to build using "build".
- warning!) Please use the root account for the build process!


## Start Shell
```bash
pwndocker 18.04 # ex) pwndocker [version]
```

- Run the built container with the "pwndocker" command.


## **Copy files from host to container**
```bash
# pwnpush [version] [host_file] [container_path]
ex) pwnpush 18.04 ./prob /root
```
- Move file to the ubuntu environment as above and start analysis!

## **Copy files from container to host**
```bash
# pwnpull [version] [container_file] [host_path]
ex) pwnpull 18.04 /root/prob .
```

## Extracting the libc file from the CTF Docker
```bash
# Build CTF Docker
docker build --no-cache --tag ctf:latest .

# pwnlibc test [binary file path in container]
ex) pwnlibc ctf /home/ctf/vuln
```
