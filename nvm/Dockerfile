# Dockerfile for base system for front end containers
FROM ubuntu
RUN apt-get update
RUN apt-get install -qy build-essential libssl-dev git man curl
RUN useradd -ms /bin/bash stack

USER stack
ENV HOME /home/stack
ENV NODE_VER v6.4.0

# install nvm
RUN curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.31.4/install.sh | bash
RUN echo 'export NVM_DIR="$HOME/.nvm"' >> $HOME/.profile
RUN echo '[ -s "$NVM_DIR/nvm.sh" ] && . "$NVM_DIR/nvm.sh"' >> $HOME/.profile

# install a default install of node
RUN ["/bin/bash", "-c", ". $HOME/.profile && nvm install $NODE_VER && nvm alias default $NODE_VER"]

USER root
CMD ["bash"]
