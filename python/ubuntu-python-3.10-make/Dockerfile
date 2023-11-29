# [Github Worflow]: runs-on: ubuntu-latest
FROM ubuntu:latest

# Set non-interactive mode
# By setting DEBIAN_FRONTEND to noninteractive, you are essentially telling the package manager to use a non-interactive mode, 
# preventing it from prompting for any input and using default configurations.
ENV DEBIAN_FRONTEND=noninteractive

# Update package lists and install dependencies
RUN apt-get update && \
    apt-get install -y build-essential libssl-dev libffi-dev zlib1g-dev wget

# Download and install Python 3.10
WORKDIR /usr/src
RUN wget https://www.python.org/ftp/python/3.10.12/Python-3.10.12.tgz && \
    tar -xzf Python-3.10.12.tgz && \
    rm Python-3.10.12.tgz && \
    cd Python-3.10.12 && \
    ./configure && \
    make && \
    make install && \
    cd / && \
    rm -r /usr/src/Python-3.10.12

# Download and install pip for Python 3.10
WORKDIR /usr/src
RUN wget https://bootstrap.pypa.io/get-pip.py && \
    python3 get-pip.py && \
    rm get-pip.py

# Clean up
RUN apt-get autoremove -y && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Project directory
WORKDIR /home/workspace

CMD ["tail", "-f", "/dev/null"]