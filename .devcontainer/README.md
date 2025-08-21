# Dev Container for React Development

This directory contains the configuration for a VS Code Dev Container that provides a consistent development environment for the React project.

## What's Included

### Container Features
- **Node.js 24** (matches your .tool-versions specification)
- **Git** and **GitHub CLI**
- **Pre-installed React development tools**
- **VS Code extensions** for React development
- **Port forwarding** for common React dev servers (3000, 5173, 8080)

### VS Code Extensions Automatically Installed
- **Prettier** - Code formatting
- **ESLint** - Code linting
- **Tailwind CSS** - CSS framework support
- **Auto Rename Tag** - Automatic HTML/JSX tag renaming
- **Path Intellisense** - File path autocompletion
- **React Snippets** - Useful React code snippets
- **Live Server** - Static server for quick previews

### Development Tools
- **Vite** - Fast build tool
- **Create React App** - Traditional React setup tool
- **Nodemon** - Auto-restart for Node.js apps
- **Serve** - Static file serving

## How to Use

### Option 1: Using Docker Compose (Recommended)
1. Install the "Dev Containers" extension in VS Code
2. Open the project in VS Code
3. Press `Ctrl+Shift+P` and select "Dev Containers: Reopen in Container"
4. Wait for the container to build and start
5. Your React project will be ready to go!

### Option 2: Using Pre-built Image
If you prefer to use Microsoft's pre-built Node.js image:
1. Edit `.devcontainer/devcontainer.json`
2. Comment out the Docker Compose lines:
   ```json
   // "dockerComposeFile": "docker-compose.yml",
   // "service": "react-dev",
   // "workspaceFolder": "/workspace",
   ```
3. Uncomment the image line:
   ```json
   "image": "mcr.microsoft.com/devcontainers/javascript-node:1-24-bullseye",
   ```

## What Happens When Container Starts
- Automatically runs `npm install` in the React project
- Sets up port forwarding for development servers
- Configures VS Code with optimal settings for React development
- Installs helpful extensions

## Development Workflow
1. Start the container
2. Open a terminal in VS Code
3. Navigate to `my-react-app` directory
4. Run `npm run dev` to start the development server
5. Access your app at `http://localhost:5173`

## Ports
- **3000** - Create React App default port
- **5173** - Vite development server default port  
- **8080** - Alternative development server port

## Customization
Feel free to modify the configuration files to suit your specific needs:
- `devcontainer.json` - Main configuration
- `Dockerfile` - Custom container setup
- `docker-compose.yml` - Multi-service setup
