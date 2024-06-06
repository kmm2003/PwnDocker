FROM ubuntu:24.04

ENV TZ Asia/Seoul
ENV PYTHONIOENCODING UTF-8
ENV LC_CTYPE C.UTF-8
ARG DEBIAN_FRONTEND=noninteractive

WORKDIR /root

RUN dpkg --add-architecture i386
RUN apt update && apt upgrade -y
RUN apt-get update && apt-get install -y netcat-openbsd
RUN apt-get dist-upgrade

RUN apt install python3 python3-dev python3-pip python3-venv -y
RUN apt install git curl wget vim zsh gdb make tmux -y
RUN apt install libffi-dev build-essential libssl-dev libc6-i386 libc6-dbg gcc-multilib -y

RUN apt-get install libcapstone-dev -y
RUN apt-get install libc6:i386 -y
RUN apt install ruby-full -y
RUN apt install ruby-dev -y

RUN gem install one_gadget

# Create a virtual environment and activate it
RUN python3 -m venv /root/venv
ENV PATH="/root/venv/bin:$PATH"

RUN pip install --upgrade pip
RUN pip install unicorn
RUN pip install keystone-engine
RUN pip install pathlib2
RUN pip install pwntools
RUN pip install capstone ropper
RUN pip install ropgadget

RUN apt install file -y
RUN git clone https://github.com/hugsy/gef /root/gef
RUN echo "source /root/gef/gef.py" >> ~/.gdbinit

RUN apt install net-tools openssh-server -y
