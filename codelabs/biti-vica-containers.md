summary: BITI VICA - Containers
id: biti-vica-containers
categories: linux, virtualization, containers
tags: biti, vica, containers
status: Published
authors: Daniel Drack

# BITI VICA - Containers

<!-- ------------------------ -->

## Before We Begin

Welcome to Containers :-)

### What You’ll Learn

- Basics of Containers

### What You'll Need

- a notebook
- access to the internet
- a thirst for knowledge, a clear mind and an insatiable urge to learn

### Further Reading

- [KodeKloud](https://kodekloud.com/)
- [Linux Foundation LFS151x](https://training.linuxfoundation.org/training/introduction-to-cloud-infrastructure-technologies/)

# Let's create a markdown file with a simple Docker demo for serving a static website using Nginx.

tutorial_content = """
# Docker Demo: Serving a Static Website with Nginx

This tutorial guides you through the process of containerizing and serving a static website using Nginx inside a Docker container. We'll start by creating a simple, nice-looking demo page, then we'll build a Docker image that serves this page using Nginx.

## Prerequisites

- Docker installed on your machine. If you haven't installed Docker yet, follow the installation instructions for your platform on the [Docker official website](https://docs.docker.com/get-docker/).

## Step 1: Create a Demo Web Page

First, create a directory for your project and navigate into it:

```bash
mkdir nginx-static-site
cd nginx-static-site
```

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Welcome to My Static Site</title>
    <style>
      body { font-family: Arial, sans-serif; text-align: center; padding: 50px; }
        h1 { color: #333366; }
        p { color: #666; font-size: 1.2em; }
    </style>
</head>
<body>
  <h1>Welcome to My Static Site</h1>
    <p>This is a simple static website served by Nginx inside a Docker container.</p>
</body>
</html>
```

```dockerfile
# Use the Nginx image from Docker Hub as the base image
FROM nginx:alpine

# Copy the static website files to the Nginx server
COPY index.html /usr/share/nginx/html/index.html

# Expose port 80
EXPOSE 80

# Start Nginx when the container launches
CMD ["nginx", "-g", "daemon off;"]
```

```bash
docker build -t yourname/nginx-static-site .
docker run -d -p 8080
```