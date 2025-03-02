FROM debian:latest

RUN apt update -y && apt upgrade -y && \
    apt install build-essential -y && \
    apt install python3 -y && apt install python3-pip -y && \
    apt install python3.11-venv -y && \
    apt install vim -y && apt install git -y && \
    apt install curl -y && \
    curl -LsSf https://astral.sh/uv/install.sh | sh
#    source $HOME/.local/bin/env
