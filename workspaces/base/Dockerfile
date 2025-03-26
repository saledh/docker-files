FROM ubuntu:24.04

# System update and upgrade
RUN apt update && apt upgrade -y

# Create a user and add it to sudo group
RUN useradd -m user && \
    echo "user:password" | chpasswd && \
    usermod -aG sudo user

# Install general-purpose packages
RUN apt install -y \
    git \
    curl \
    wget \
    unzip \
    xclip \
    iproute2 \
    stow \
    gcc \
    make \
    cmake \
    ripgrep \
    fd-find \
    fzf

# Install zsh and set it as default shell (for "saledh" user)
RUN apt install -y zsh && chsh -s /bin/zsh user

# Install tmux
RUN apt install -y tmux

# Install alacritty and neovim (latest unstable)
RUN apt install -y software-properties-common && \
    add-apt-repository ppa:neovim-ppa/unstable -y && \
    apt install -y neovim

# Install JetBrains Nerd Font
RUN curl https://raw.githubusercontent.com/saledh/shell-scripts/refs/heads/main/nerd-fonts/install-font.sh | sh

# Download dotfiles
RUN git clone https://github.com/saledh/dotfiles.git /home/user/dotfiles
