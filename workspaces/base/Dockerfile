FROM ubuntu:24.04

# Install Desktop Environment packages
RUN apt update && apt upgrade -y && DEBIAN_FRONTEND="noninteractive" apt install -y --no-install-recommends \
        dbus-x11 \
        firefox \
        git \
        locales \
        pavucontrol \
        pulseaudio \
        pulseaudio-utils \
        sudo \
        x11-xserver-utils \
        xfce4 \
        xfce4-goodies \
        xfce4-pulseaudio-plugin \
        xorgxrdp \
        xrdp \
        xubuntu-icon-theme \
    && rm -rf /var/lib/apt/lists/*

# Neovim install
RUN apt update && apt upgrade -y && apt install -y software-properties-common && add-apt-repository ppa:neovim-ppa/unstable -y && apt-get install -y neovim
    
### Neovim setup
RUN apt-get install -y git curl make cmake gcc ripgrep fzf fd-find
RUN git clone https://github.com/LazyVim/starter ~/.config/nvim
RUN rm -rf ~/.config/nvim/.git

# Set "ubuntu" user's password
RUN echo "ubuntu:password" | chpasswd