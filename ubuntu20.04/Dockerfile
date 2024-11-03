FROM ubuntu:20.04

ARG DEBIAN_FRONTEND=noninteractive

ENV TZ Asia/Seoul
ENV PYTHONIOENCODING UTF-8
ENV LC_CTYPE C.UTF-8

WORKDIR /root

RUN apt update && apt install -y netcat
RUN apt install vim git gcc ssh curl wget gdb sudo zsh tmux python3 python3-pip libffi-dev build-essential libssl-dev libc6-i386 libc6-dbg gcc-multilib make -y

RUN dpkg --add-architecture i386
RUN apt update
RUN apt install libc6:i386 -y

RUN python3 -m pip install --upgrade pip
RUN pip3 install unicorn
RUN pip3 install keystone-engine
RUN pip3 install pwntools
RUN pip3 install ropgadget
RUN apt install libcapstone-dev -y

RUN git clone https://github.com/hugsy/gef ./gef
RUN echo source ~/gef/gef.py >> ~/.gdbinit

RUN wget https://cache.ruby-lang.org/pub/ruby/3.1/ruby-3.1.0.tar.gz && \
    tar -xzvf ruby-3.1.0.tar.gz && \
    cd ruby-3.1.0 && \
    ./configure && \
    make && \
    make install && \
    cd .. && \
    rm -rf ruby-3.1.0 ruby-3.1.0.tar.gz
RUN gem install one_gadget seccomp-tools
