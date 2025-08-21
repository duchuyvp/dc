# Use the official Node.js image as base
FROM node:24-bullseye-slim

# Install additional tools that might be useful for React development
RUN apt-get update && apt-get install -y \
    git \
    curl \
    wget \
    vim \
    nano \
    && rm -rf /var/lib/apt/lists/*

# Set the working directory
WORKDIR /workspace

# Create a non-root user
RUN useradd -m -s /bin/bash devuser && \
    chown -R devuser:devuser /workspace

# Switch to non-root user
USER devuser

# Set up shell for better development experience
RUN echo 'alias ll="ls -la"' >> ~/.bashrc && \
    echo 'alias la="ls -la"' >> ~/.bashrc

# Install global npm packages commonly used in React development
RUN npm install -g \
    create-vite \
    create-react-app \
    serve \
    nodemon

CMD ["/bin/bash"]
