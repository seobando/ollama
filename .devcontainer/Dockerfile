# Use an official Python runtime as a parent image
FROM mcr.microsoft.com/devcontainers/python:3.10

# Set working directory
WORKDIR /app

# Install system dependencies
RUN apt-get update && apt-get install -y \
    git \
    curl \
    && rm -rf /var/lib/apt/lists/*

# Copy the Modelfile and other project files
COPY . .

# Install ollama (assuming you're using ollama for llama models)
RUN curl -L https://ollama.ai/download/ollama-linux-amd64 -o /usr/local/bin/ollama \
    && chmod +x /usr/local/bin/ollama

# Expose port for ollama
EXPOSE 11434

# Set environment variables
ENV PYTHONUNBUFFERED=1

# Command to run ollama
CMD ["ollama", "serve"] 