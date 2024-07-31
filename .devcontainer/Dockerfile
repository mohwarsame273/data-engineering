FROM mcr.microsoft.com/devcontainers/base:alpine

# Install system dependencies
RUN sudo apk add --no-cache \
    python3 \
    py3-pip \
    py3-virtualenv \
    openjdk11 \
    npm \
    gradle \
    maven \
    py3-numpy \
    py3-pandas \
    py3-matplotlib \
    py3-scipy \
    && sudo npm install -g npm@latest

# Install Python development tools
RUN sudo apk add --no-cache \
    py3-flake8 \
    py3-autopep8 \
    py3-yapf \
    py3-mypy \
    py3-pycodestyle \
    py3-pytest \
    py3-pylint

# Upgrade pip and install required Python packages
COPY requirements.txt /tmp/pip-tmp/
RUN pip3 install --upgrade pip \
    && pip3 --disable-pip-version-check --no-cache-dir install -r /tmp/pip-tmp/requirements.txt \
    && rm -rf /tmp/pip-tmp

# Set up environment variables
ENV PYTHONUNBUFFERED=1

# Set the default shell to bash
SHELL ["/bin/bash", "-c"]
