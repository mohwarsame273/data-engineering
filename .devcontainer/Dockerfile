FROM python:3.9

# Install system dependencies
RUN apt-get update && apt-get install -y \
    default-jdk \
    && rm -rf /var/lib/apt/lists/*

# Set up the working directory
WORKDIR /workspace

# Install Python dependencies
COPY requirements.txt /tmp/
RUN pip install --upgrade pip && pip install -r /tmp/requirements.txt

# Set up environment variables
ENV PYTHONUNBUFFERED 1