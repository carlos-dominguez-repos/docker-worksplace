# [Github Worflow]: runs-on: ubuntu-latest
FROM ubuntu:latest

# Install general binaries
RUN apt-get update && apt-get install -y wget unzip curl git ca-certificates gnupg vim
# && rm -rf /var/lib/apt/lists/*

# [Github Worflow]: - name: Setup nodejs 18
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

# [Github Worflow]: - name: Setup terraform 1.4.6
RUN wget --quiet https://releases.hashicorp.com/terraform/1.4.6/terraform_1.4.6_linux_amd64.zip \
    && unzip terraform_1.4.6_linux_amd64.zip \
    && mv terraform /usr/bin \
    && rm terraform_1.4.6_linux_amd64.zip

CMD ["tail", "-f", "/dev/null"]