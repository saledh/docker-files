FROM saledh/workspace:base

RUN apt update && apt upgrade -y && apt install -y maven

RUN curl -sL https://github.com/shyiko/jabba/raw/master/install.sh | bash && . ~/.jabba/jabba.sh
