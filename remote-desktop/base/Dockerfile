FROM ubuntu:24.04

# System update and upgrade
RUN apt update && apt upgrade -y

# Install desktop environment and XRDP
# By default Xrdp uses the /etc/ssl/private/ssl-cert-snakeoil.key file that is readable only by members of the “ssl-cert” group
RUN DEBIAN_FRONTEND=noninteractive apt install -y \
    lubuntu-desktop \
    xrdp && \
    adduser xrdp ssl-cert 

# Create a user and add to sudo group
RUN useradd -m user && \
    echo "user:password" | chpasswd && \
    usermod -aG sudo user

# Expose port 3389
EXPOSE 3389

# Start services
CMD ["service", "xrdp", "start", "&&", "bash"]
