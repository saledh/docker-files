FROM saledh/workspace:base

# System update and upgrade
RUN apt update && apt upgrade -y

# Install maven
RUN apt install -y maven

# Install jabba
RUN curl -sL https://github.com/shyiko/jabba/raw/master/install.sh | bash && . ~/.jabba/jabba.sh
