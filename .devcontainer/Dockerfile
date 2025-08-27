FROM node:24-trixie

# Install some dependencies such as curl and sudo.
# Also set up passwordless sudo for the ubuntu user.
RUN apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get install -y \
      curl \
      sudo \
      apt-transport-https 

# Add our onCreateCommand script.
ADD on-create.sh /on-create.sh


# The devcontainer feature provides /usr/local/share/docker-init.sh
# which will handle most of the steps of setting up Docker.
# We can't put this in the entrypoint as it gets overridden, so
# we call it in the on-create script.
ENTRYPOINT ["bash"]