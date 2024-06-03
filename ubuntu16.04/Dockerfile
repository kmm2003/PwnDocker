FROM ubuntu:16.04

ARG DEBIAN_FRONTEND=noninteractive

ENV TZ Asia/Seoul
ENV PYTHONIOENCODING UTF-8
ENV LC_CTYPE C.UTF-8

WORKDIR /root

RUN apt-get update && apt-get install apt-utils netcat -y
RUN apt-get update && apt-get install -y vim git gcc ssh curl wget gdb sudo zsh tmux python3 python3-dev python3-pip libffi-dev build-essential libssl-dev libc6-i386 libc6-dbg gcc-multilib make

RUN dpkg --add-architecture i386
RUN apt-get update
RUN apt-get install -y libc6:i386

RUN pip3 install -U pip==20.3.4
RUN pip3 install unicorn
RUN pip3 install keystone-engine
RUN pip3 install -U pwntools
RUN pip3 install capstone ropper
RUN pip3 install ropgadget
RUN apt-get install -y libcapstone-dev

RUN wget https://github.com/hugsy/gef/archive/refs/tags/2020.03.tar.gz
RUN tar -xzvf 2020.03.tar.gz
RUN echo "source ~/gef-2020.03/gef.py" >> ~/.gdbinit
