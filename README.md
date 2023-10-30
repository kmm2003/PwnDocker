# PwnDocker Readme


## About
ubuntu environment docker file for ctf player with pwnable

Various tools are installed in each environment to help with pwnable analysis.

(etc. GDB, pyhon, pwntools, tmux, ropgadget, ruby, one_gadget, seccomp-tools)


## Build
```python
# example of building ubuntu18.04

git clone https://github.com/kmm2003/PwnDocker.git

./install 18.04 # ex) ./install [version]

```

- Install is easy to install using install.


## Used
```python
pwndocker 18.04 # ex) pwndocker [version]
```

- Run the built container with the pwndocker command.


## **Transfer files from host to container**
```python
# docker cp [filename] [container_name]:[container_path]
ex) docker cp ./prob kind_elion:/root
```

- Move the self file to the ubuntu environment as above and start analysis!
