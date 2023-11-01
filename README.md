# PwnDocker

## About
ubuntu environment docker file for ctf player with pwnable

Various tools are installed in each environment to help with pwnable analysis.

(etc. GDB, pyhon, pwntools, tmux, ropgadget, ruby, one_gadget, seccomp-tools)


## Build
```python
# example of building ubuntu18.04

git clone https://github.com/kmm2003/PwnDocker.git

cd ./PwnDocker

./build 18.04 # ex) ./build [version]

```

- Easy to build using "build".
- warning!) Please use the root account for the build process!


## Used
```python
pwndocker 18.04 # ex) pwndocker [version]
```

- Run the built container with the "pwndocker" command.


## **Transfer files from host to container**
```python
# docker cp [filename] [container_name]:[container_path]
ex) docker cp ./prob 18.04:/root
```

## **Transfer files from container to host**
```python
# docker cp [container_name]:[container_filepath] [filename]
ex) docker cp 18.04:/root/targetfile ./targetfile
```

- Move the self file to the ubuntu environment as above and start analysis!
