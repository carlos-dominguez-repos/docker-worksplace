# [Github Worflow]: runs-on: ubuntu-latest
FROM ubuntu:latest

# Set non-interactive mode
# By setting DEBIAN_FRONTEND to noninteractive, you are essentially telling the package manager to use a non-interactive mode, 
# preventing it from prompting for any input and using default configurations.
ENV DEBIAN_FRONTEND=noninteractive

# Install general binaries
RUN apt-get update && apt-get install -y wget unzip curl git ca-certificates gnupg
# && rm -rf /var/lib/apt/lists/*

# Deprecated way to install NodeJS
# RUN curl -sL https://deb.nodesource.com/setup_18.x | bash - \
#     && apt -y install nodejs

# [Github Worflow]: - name: Setup nodejs 14
# New way to install nodejs
RUN set -uex; \
    apt-get update; \
    mkdir -p /etc/apt/keyrings; \
    curl -fsSL https://deb.nodesource.com/gpgkey/nodesource-repo.gpg.key \
     | gpg --dearmor -o /etc/apt/keyrings/nodesource.gpg; \
    NODE_MAJOR=18; \
    echo "deb [signed-by=/etc/apt/keyrings/nodesource.gpg] https://deb.nodesource.com/node_$NODE_MAJOR.x nodistro main" \
     > /etc/apt/sources.list.d/nodesource.list; \
    apt-get update; \
    apt-get install nodejs -y;
    
CMD ["tail", "-f", "/dev/null"]