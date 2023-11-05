FROM arm32v7/ubuntu:20.04

ARG DEBIAN_FRONTEND=noninteractive

ENV TZ Asia/Seoul
ENV PYTHONIOENCODING UTF-8
ENV LC_CTYPE C.UTF-8

WORKDIR /root

RUN apt update && apt install -y netcat

RUN yes | unminimize
RUN dpkg --add-architecture armhf
RUN apt-get update
RUN apt-get upgrade
RUN apt install vim git gcc ssh curl wget zsh tmux -y
RUN apt-get install -qy strace ltrace gdb build-essential python3 python3-pip libssl-dev libffi-dev cargo pkg-config cmake
#RUN curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh

#RUN python3 -m pip install --upgrade pip setuptools
#RUN python3 -m pip install cffi
#RUN python3 -m pip install --upgrade pip
#RUN python3 -m pip install cryptography==2.1.1
#RUN pip3 install "git+https://github.com/unicorn-engine/unicorn@e76b2db434382f59661471faae02b022a3ee5a30#subdirectory=bindings/python/"

RUN python3 -m pip install ropper 
#RUN python3 -m pip install setuptools_rust
#RUN python3 -m pip install pwntools

RUN git clone https://github.com/hugsy/gef ./gef
RUN echo source ~/gef/gef.py >> ~/.gdbinit

RUN wget https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | zsh || true
RUN mkdir -p "$HOME/.zsh"
RUN git clone https://github.com/sindresorhus/pure.git "$HOME/.zsh/pure"
RUN echo "fpath+=("$HOME/.zsh/pure")\nautoload -U promptinit; promptinit\nprompt pure" >> ~/.zshrc

RUN git clone https://github.com/zsh-users/zsh-syntax-highlighting.git
RUN echo "source ./zsh-syntax-highlighting/zsh-syntax-highlighting.zsh" >> ~/.zshrc

RUN git clone https://github.com/zsh-users/zsh-autosuggestions ~/.zsh/zsh-autosuggestions
RUN echo "source ~/.zsh/zsh-autosuggestions/zsh-autosuggestions.zsh" >> ~/.zshrc
RUN echo "ZSH_AUTOSUGGEST_HIGHLIGHT_STYLE='fg=111'" >> ~/.zshrc

RUN ln -s /lib/ld-linux-arm.so.3 /lib/ld-linux.so.3

WORKDIR /root
