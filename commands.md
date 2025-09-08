# Commands to know ****

# Build the Docker image
docker build -t bens-node-app .

# Run the container (basic)
docker run -p 8080:8080 bens-node-app

# Run with volume mapping for live development
docker run -p 8080:8080 -v $(pwd):/app -v /app/node_modules bens-node-app

# Run in detached mode (background)
docker run -d -p 8080:8080 --name bens-node-container bens-node-app

# View running containers
docker ps

# View logs
docker logs bens-node-container

# Stop container
docker stop bens-node-container

# Remove container
docker rm bens-node-container

# Remove image
docker rmi bens-node-app

# Rebuild after changes
docker build --no-cache -t bens-node-app .

# Cleanup old images
docker image prune -f