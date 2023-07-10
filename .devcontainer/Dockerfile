# Use Debian as a base image
FROM debian:bullseye-slim

# Install necessary tools
RUN apt-get update && apt-get install -y \
    curl \
    build-essential \
    apt-transport-https \
    ca-certificates \
    unzip \
    software-properties-common \
    wget

# Install Python
RUN apt-get install -y python3 python3-pip

# Install .NET Core SDK
RUN wget https://packages.microsoft.com/config/debian/11/packages-microsoft-prod.deb -O packages-microsoft-prod.deb && \
    dpkg -i packages-microsoft-prod.deb && \
    rm packages-microsoft-prod.deb && \
    apt-get update && \
    apt-get install -y dotnet-sdk-7.0

# Clean up
RUN rm -rf /var/lib/apt/lists/*
