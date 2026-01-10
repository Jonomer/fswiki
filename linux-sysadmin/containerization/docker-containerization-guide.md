# Docker Containerization Guide

## Summary

Docker containerization enables packaging applications and their dependencies into lightweight, portable containers that run consistently across different environments. This comprehensive guide covers Docker fundamentals, container creation, orchestration basics, and best practices for production deployments. You'll learn how to containerize applications, manage Docker images, implement multi-container applications, and optimize container performance for real-world scenarios.

## Prerequisites

- Basic Linux command-line knowledge
- Understanding of application architecture
- Familiarity with package managers and dependencies
- Access to a Linux system or Docker Desktop for Windows/Mac

## Content

### What is Docker?

Docker is an open-source platform that automates application deployment using containerization. Containers package an application with all its dependencies (libraries, binaries, configuration files) into a single unit that can run consistently on any system with Docker installed.

**Key Concepts:**

- **Container**: Lightweight, standalone executable package
- **Image**: Read-only template used to create containers
- **Dockerfile**: Text file with instructions to build an image
- **Registry**: Repository for storing and sharing images (Docker Hub, etc.)
- **Docker Engine**: Runtime that builds and runs containers

**Benefits:**

1. **Consistency**: Same behavior across development, testing, and production
2. **Isolation**: Applications run in isolated environments
3. **Portability**: Run anywhere Docker is installed
4. **Resource Efficiency**: Lower overhead than virtual machines
5. **Scalability**: Easy horizontal scaling of containers

### Docker vs Virtual Machines

| Feature | Docker Containers | Virtual Machines |
|---------|------------------|------------------|
| **OS** | Shares host OS kernel | Full guest OS per VM |
| **Size** | Megabytes | Gigabytes |
| **Startup Time** | Seconds | Minutes |
| **Resource Usage** | Lower overhead | Higher overhead |
| **Isolation** | Process-level | Hardware-level |

### Core Docker Components

#### Docker Engine

The core runtime that manages containers, images, networks, and volumes.

#### Docker CLI

Command-line interface for interacting with Docker Engine.

#### Docker Compose

Tool for defining and running multi-container Docker applications.

#### Docker Registry

Service for storing and distributing Docker images (public or private).

### Getting Started with Docker

#### Installation

**Linux (Ubuntu/Debian):**
```bash
# Update package index
sudo apt-get update

# Install prerequisites
sudo apt-get install ca-certificates curl gnupg

# Add Docker's official GPG key
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

# Set up repository
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

# Install Docker Engine
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

# Verify installation
sudo docker run hello-world
```

**Windows/Mac:**
Download and install Docker Desktop from [docker.com](https://www.docker.com/products/docker-desktop).

### Dockerfile Best Practices

#### Basic Dockerfile Structure

```dockerfile
# Base image
FROM node:18-alpine

# Set working directory
WORKDIR /app

# Copy package files
COPY package*.json ./

# Install dependencies
RUN npm ci --only=production

# Copy application code
COPY . .

# Expose port
EXPOSE 3000

# Define entry point
CMD ["node", "server.js"]
```

#### Optimization Techniques

**1. Use Multi-Stage Builds**
```dockerfile
# Build stage
FROM node:18 AS builder
WORKDIR /app
COPY package*.json ./
RUN npm ci
COPY . .
RUN npm run build

# Production stage
FROM node:18-alpine
WORKDIR /app
COPY package*.json ./
RUN npm ci --only=production
COPY --from=builder /app/dist ./dist
EXPOSE 3000
CMD ["node", "dist/server.js"]
```

**2. Layer Caching**
```dockerfile
# Bad: Changes to code invalidate dependency layer
COPY . .
RUN npm install

# Good: Dependencies cached separately
COPY package*.json ./
RUN npm install
COPY . .
```

**3. Use .dockerignore**
```
node_modules
npm-debug.log
.git
.gitignore
README.md
.env
.nyc_output
coverage
```

**4. Minimize Image Size**
- Use Alpine Linux base images
- Remove unnecessary packages after installation
- Use multi-stage builds
- Avoid installing development tools in production images

### Docker Commands

#### Image Management

```bash
# List images
docker images

# Pull image from registry
docker pull nginx:latest

# Build image from Dockerfile
docker build -t myapp:latest .

# Remove image
docker rmi myapp:latest

# Tag image
docker tag myapp:latest myregistry.com/myapp:v1.0
```

#### Container Management

```bash
# Run container
docker run -d -p 8080:80 --name mynginx nginx

# List running containers
docker ps

# List all containers
docker ps -a

# Stop container
docker stop mynginx

# Start stopped container
docker start mynginx

# Remove container
docker rm mynginx

# View container logs
docker logs mynginx

# Execute command in running container
docker exec -it mynginx /bin/bash
```

#### Advanced Options

```bash
# Run with environment variables
docker run -e DATABASE_URL=postgres://... myapp

# Mount volumes
docker run -v /host/path:/container/path myapp

# Run in detached mode with restart policy
docker run -d --restart unless-stopped myapp

# Set resource limits
docker run --memory="512m" --cpus="1.0" myapp
```

### Docker Compose

Docker Compose allows defining multi-container applications in a YAML file.

#### docker-compose.yml Example

```yaml
version: '3.8'

services:
  web:
    build: .
    ports:
      - "3000:3000"
    environment:
      - DATABASE_URL=postgres://db:5432/myapp
    depends_on:
      - db
    volumes:
      - ./src:/app/src
    restart: unless-stopped

  db:
    image: postgres:15-alpine
    environment:
      - POSTGRES_DB=myapp
      - POSTGRES_USER=user
      - POSTGRES_PASSWORD=password
    volumes:
      - postgres_data:/var/lib/postgresql/data
    ports:
      - "5432:5432"

  redis:
    image: redis:7-alpine
    ports:
      - "6379:6379"

volumes:
  postgres_data:
```

#### Compose Commands

```bash
# Start services
docker-compose up -d

# Stop services
docker-compose down

# View logs
docker-compose logs -f web

# Rebuild and restart
docker-compose up -d --build

# Scale service
docker-compose up -d --scale web=3
```

## Examples

### Example 1: Containerizing a Node.js Application

Complete example of containerizing a Node.js web application:

**Dockerfile:**
```dockerfile
FROM node:18-alpine AS builder

WORKDIR /app

# Copy package files
COPY package*.json ./

# Install all dependencies (including dev)
RUN npm ci

# Copy source code
COPY . .

# Build application
RUN npm run build

# Production stage
FROM node:18-alpine

WORKDIR /app

# Copy package files
COPY package*.json ./

# Install only production dependencies
RUN npm ci --only=production

# Copy built application from builder stage
COPY --from=builder /app/dist ./dist

# Create non-root user
RUN addgroup -g 1001 -S nodejs && \
    adduser -S nodejs -u 1001

USER nodejs

EXPOSE 3000

# Health check
HEALTHCHECK --interval=30s --timeout=3s --start-period=5s --retries=3 \
  CMD node healthcheck.js

CMD ["node", "dist/server.js"]
```

**docker-compose.yml:**
```yaml
version: '3.8'

services:
  app:
    build:
      context: .
      dockerfile: Dockerfile
    ports:
      - "3000:3000"
    environment:
      - NODE_ENV=production
      - DATABASE_URL=${DATABASE_URL}
    depends_on:
      - postgres
    restart: unless-stopped
    networks:
      - app-network

  postgres:
    image: postgres:15-alpine
    environment:
      POSTGRES_DB: myapp
      POSTGRES_USER: user
      POSTGRES_PASSWORD: ${DB_PASSWORD}
    volumes:
      - postgres_data:/var/lib/postgresql/data
    networks:
      - app-network

networks:
  app-network:
    driver: bridge

volumes:
  postgres_data:
```

**Explanation:**
This example demonstrates a production-ready Node.js containerization with multi-stage build, non-root user for security, health checks, and proper network isolation.

### Example 2: Python Flask Application

```dockerfile
FROM python:3.11-slim

WORKDIR /app

# Install system dependencies
RUN apt-get update && apt-get install -y \
    gcc \
    && rm -rf /var/lib/apt/lists/*

# Copy requirements
COPY requirements.txt .

# Install Python dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Copy application code
COPY . .

# Create non-root user
RUN useradd -m -u 1000 appuser && chown -R appuser:appuser /app
USER appuser

EXPOSE 5000

CMD ["gunicorn", "--bind", "0.0.0.0:5000", "--workers", "4", "app:app"]
```

**Explanation:**
Python application with optimized base image, proper user permissions, and production-ready Gunicorn server configuration.

### Example 3: Docker Networking

Creating custom networks for container communication:

```bash
# Create custom network
docker network create --driver bridge app-network

# Run containers on custom network
docker run -d --name web --network app-network nginx
docker run -d --name db --network app-network postgres

# Containers can communicate using service names
# Web container can access: http://db:5432
```

**Explanation:**
Custom networks enable secure container-to-container communication using service names, with isolation from other containers.

## Troubleshooting

### Issue: Container Exits Immediately

**Symptoms:**
- Container starts and immediately stops
- `docker ps -a` shows container with exit code

**Solution:**
1. Check container logs: `docker logs <container-id>`
2. Verify CMD/ENTRYPOINT in Dockerfile
3. Ensure process runs in foreground (not as daemon)
4. Check if application crashes on startup
5. Test with interactive mode: `docker run -it <image> /bin/bash`

### Issue: Port Already in Use

**Symptoms:**
- Error: "bind: address already in use"
- Cannot start container on specified port

**Solution:**
```bash
# Find process using port
sudo lsof -i :8080
# or
sudo netstat -tulpn | grep :8080

# Stop conflicting container
docker stop <container-name>

# Or use different host port
docker run -p 8081:80 nginx
```

### Issue: Out of Disk Space

**Symptoms:**
- Errors during image builds
- Cannot pull new images
- Disk usage warnings

**Solution:**
```bash
# Clean up unused resources
docker system prune -a

# Remove unused volumes
docker volume prune

# Remove old images
docker image prune -a

# Check disk usage
docker system df
```

### Issue: Container Cannot Access Host Resources

**Symptoms:**
- Container cannot connect to host services
- Network connectivity issues

**Solution:**
```bash
# Use host network mode (Linux only)
docker run --network host myapp

# Access host from container using host.docker.internal (Mac/Windows)
# Or use --add-host for Linux
docker run --add-host=host.docker.internal:host-gateway myapp
```

## Best Practices

### 1. Security Best Practices

- Run containers as non-root user
- Use minimal base images (Alpine Linux)
- Scan images for vulnerabilities
- Keep base images updated
- Use secrets management (not environment variables for sensitive data)
- Implement proper network isolation
- Limit container capabilities (`--cap-drop`, `--cap-add`)

### 2. Performance Optimization

- Use multi-stage builds to reduce image size
- Leverage layer caching effectively
- Use `.dockerignore` to exclude unnecessary files
- Optimize RUN commands (combine when possible)
- Use specific image tags (not `latest` in production)

### 3. Container Lifecycle Management

- Implement health checks
- Use proper restart policies
- Set resource limits (CPU, memory)
- Monitor container metrics
- Implement graceful shutdown handling

### 4. Development Workflow

- Use volumes for code mounting during development
- Keep Dockerfiles in version control
- Use docker-compose for local development
- Maintain separate compose files for dev/prod

### 5. Production Deployment

- Use orchestration tools (Kubernetes, Docker Swarm)
- Implement proper logging and monitoring
- Use container registries for image storage
- Automate builds with CI/CD pipelines
- Implement blue-green or canary deployments

## Conclusion

Docker containerization revolutionizes application deployment by providing consistency, portability, and efficiency. By following best practices in Dockerfile creation, container management, and security, you can build robust, scalable containerized applications.

**Key Takeaways:**
- Containers provide consistent runtime environments
- Multi-stage builds optimize image size
- Docker Compose simplifies multi-container applications
- Security and resource management are critical in production
- Proper networking enables secure container communication

**Next Steps:**
- Containerize your existing applications
- Set up Docker Compose for local development
- Explore container orchestration (Kubernetes)
- Implement CI/CD pipelines for automated builds
- Learn about container security scanning

**Related Topics to Explore:**
- Kubernetes Orchestration
- Container Security Scanning
- Docker Networking Deep Dive
- CI/CD Pipeline Integration
- Microservices Architecture

## References

- [Docker Official Documentation](https://docs.docker.com/) - Complete Docker reference
- [Dockerfile Best Practices](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/) - Official best practices guide
- [Docker Compose Documentation](https://docs.docker.com/compose/) - Multi-container application guide
- [OWASP Docker Security](https://cheatsheetseries.owasp.org/cheatsheets/Docker_Security_Cheat_Sheet.html) - Security best practices
- [Container Image Security](https://docs.docker.com/engine/security/) - Docker security documentation

## Related Articles

- [Kubernetes Orchestration Guide](../containerization/kubernetes-basics.md) - _Coming soon_
- [Container Security Best Practices](../security-hardening/container-security.md) - _Coming soon_
- [CI/CD Pipeline Setup](../../software-development/devops/cicd-pipeline-setup.md) - _Coming soon_

---

**Last Updated:** January 2024

**Author:** FS Wiki Community

