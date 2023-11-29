# [Github Worflow]: runs-on: ubuntu-latest
FROM ubuntu:latest

# Set non-interactive mode
# By setting DEBIAN_FRONTEND to noninteractive, you are essentially telling the package manager to use a non-interactive mode, 
# preventing it from prompting for any input and using default configurations.
ENV DEBIAN_FRONTEND=noninteractive

# Update package lists and install dependencies
RUN apt-get update && \
    apt-get install -y wget

# Download and install Python 3.10.12
RUN apt-get install -y python3

# Download and install pip for Python 3.10
WORKDIR /usr/src
RUN wget https://bootstrap.pypa.io/get-pip.py && \
    python3 get-pip.py && \
    rm get-pip.py

# Project directory
WORKDIR /home/workspace

CMD ["tail", "-f", "/dev/null"]