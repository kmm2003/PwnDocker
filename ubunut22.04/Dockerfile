FROM ubuntu:22.04

ENV TZ Asia/Seoul
ENV PYTHONIOENCODING UTF-8
ENV LC_CTYPE C.UTF-8
ARG DEBIAN_FRONTEND=noninteractive #no interactive

WORKDIR root

#RUN sed -i 's/archive.ubuntu.com/mirror.kakao.com/g' /etc/apt/sources.list
RUN dpkg --add-architecture i386
RUN apt update && apt upgrade -y
RUN apt-get update && apt-get install -y netcat
RUN apt-get dist-upgrade

RUN apt install python3 python3-dev python3-pip -y
RUN apt install git curl wget vim zsh gdb make -y
RUN apt install libffi-dev build-essential libssl-dev libc6-i386 libc6-dbg gcc-multilib make tmux -y

RUN apt-get install libcapstone-dev -y
RUN apt-get install libc6:i386 -y
RUN apt install ruby-full -y
RUN apt install ruby-dev -y

RUN gem install one_gadget
RUN gem install seccomp-tools

RUN pip3 install unicorn
RUN pip3 install keystone-engine
RUN pip3 install pathlib2
RUN pip3 install pwntools #only using python3
RUN pip3 install capstone ropper
RUN pip3 install ropgadget

RUN git clone https://github.com/longld/peda.git ~/peda
RUN echo "source ~/peda/peda.py" >> ~/.gdbinit

RUN wget https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | zsh || true

RUN mkdir -p "$HOME/.zsh"
RUN git clone https://github.com/sindresorhus/pure.git "$HOME/.zsh/pure"
RUN echo "fpath+=("$HOME/.zsh/pure")\nautoload -U promptinit; promptinit\nprompt pure" >> ~/.zshrc

RUN git clone https://github.com/zsh-users/zsh-syntax-highlighting.git
RUN echo "source ./zsh-syntax-highlighting/zsh-syntax-highlighting.zsh" >> ~/.zshrc

RUN git clone https://github.com/zsh-users/zsh-autosuggestions ~/.zsh/zsh-autosuggestions
RUN echo "source ~/.zsh/zsh-autosuggestions/zsh-autosuggestions.zsh" >> ~/.zshrc
RUN echo "ZSH_AUTOSUGGEST_HIGHLIGHT_STYLE='fg=111'" >> ~/.zshrc

RUN apt install net-tools openssh-server -y
