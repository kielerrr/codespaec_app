# Base image
FROM mcr.microsoft.com/devcontainers/python:3.10

# Install Node.js and npm
RUN curl -fsSL https://deb.nodesource.com/setup_16.x | bash - \
    && apt-get install -y nodejs \
    && npm install -g npm@latest

# Install Docker Compose
RUN apt-get update && apt-get install -y docker-compose

# Set working directory
WORKDIR /workspaces/codespaec_app

# Expose ports
EXPOSE 8000 5173