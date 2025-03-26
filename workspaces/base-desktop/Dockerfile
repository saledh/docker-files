FROM saledh/workspace:base

# System Update and upgrade
RUN apt update && apt upgrade -y

# Install desktop environment
RUN DEBIAN_FRONTEND=noninteractive apt install -y lubuntu-desktop

# Install XRDP
RUN apt install -y xrdp && \
    adduser xrdp ssl-cert # By default Xrdp uses the /etc/ssl/private/ssl-cert-snakeoil.key file that is readable only by members of the “ssl-cert” group

RUN add-apt-repository ppa:aslatter/ppa -y && \
    apt install alacritty

# Expose port 3389 for RDP connection
EXPOSE 3389

CMD ["service", "xrdp", "start", "&&", "sh"]
