FROM jenkins/jenkins:lts

USER root

# Install Git, Docker CLI, Python
RUN apt-get update && \
    apt-get install -y git docker.io python3 python3-pip && \
    rm -rf /var/lib/apt/lists/*

USER jenkins
