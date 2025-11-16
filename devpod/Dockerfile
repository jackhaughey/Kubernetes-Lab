# .devcontainer/Dockerfile
FROM ubuntu:22.04

RUN apt-get update && apt-get install -y curl apt-transport-https gnupg \
    && curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | apt-key add - \
    && echo "deb https://apt.kubernetes.io/ kubernetes-xenial main" \
       > /etc/apt/sources.list.d/kubernetes.list \
    && apt-get update && apt-get install -y kubectl \
    && apt-get clean && rm -rf /var/lib/apt/lists/*

# Create devpod user
RUN useradd -m devpod && echo "devpod ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers

USER devpod
WORKDIR /home/devpod


CMD ["bash"]
