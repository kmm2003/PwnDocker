FROM ubuntu:22.04

ENV TZ Asia/Seoul
ENV PYTHONIOENCODING UTF-8
ENV LC_CTYPE C.UTF-8
ARG DEBIAN_FRONTEND=noninteractive #no interactive

WORKDIR /root

RUN dpkg --add-architecture i386
RUN apt update && apt upgrade -y
RUN apt-get update && apt-get install -y netcat
RUN apt-get dist-upgrade

RUN apt install python3 python3-dev python3-pip -y
RUN apt install git curl wget vim zsh gdb make tmux -y
RUN apt install libffi-dev build-essential libssl-dev libc6-i386 libc6-dbg gcc-multilib -y

RUN apt-get install libcapstone-dev -y
RUN apt-get install libc6:i386 -y
RUN apt install ruby-full -y
RUN apt install ruby-dev -y

RUN gem install one_gadget

RUN pip3 install unicorn
RUN pip3 install keystone-engine
RUN pip3 install pathlib2
RUN pip3 install pwntools #only using python3
RUN pip3 install capstone ropper
RUN pip3 install ropgadget

RUN apt install file -y
RUN git clone https://github.com/hugsy/gef ./gef
RUN echo source ~/gef/gef.py >> ~/.gdbinit

RUN apt install net-tools openssh-server -y
