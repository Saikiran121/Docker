01. Why we use Docker?
    - When you install software the traditional way, you often face a cycle of downloading installers, running them, hitting errors, troubleshooting
      and repeating until it finally works. 
    
    - This happens because every computer has different settings, dependencies, and environments, which can cause unexpected problems.

    - For example if we want to install an software/application we go through 
      a. Download Installer
      b. Run Installer
      c. Get an Error during Installation
      d. Troubleshoot Issue
      e. Rerun Installer
      f. Get another error
    - And the cycle continues until we successfully install the software/application.

    - Docker solves this problem by packing software and everything it needs (like libraries and settings) into a single container. This container
      will run the same way on any computer, server or cloud no matter whats installed on that system. This means
      a. No more “it works on my machine, but not on yours” issues.
      b. No need to manually install dependencies or troubleshoot environment problems.
      c. You can start, stop, and remove software easily, without affecting your main system


02. Example: Installing Redis with Docker

    a. Without Docker
        - You would have to download Redis, install it, configure it, and fix any errors that come up, which can be time-consuming and frustrating.

    b. With Docker
        - You can install and run Redis with just one simple command, and it will work the same way every time.

    c. How Simple is it?
        - You can install and run Redis with just one simple command, and it will work the same way every time.
            # docker run --name my-redis -p 6379:6379 -d redis

        - This command tells Docker to download the Redis image and run it in a container named my-redis.
        - Redis will be available on port 6379, ready to use.
        - No manual installation, no dependency issues, no troubleshooting required.


03. What is DOcker?
    - Docker is a tool that makes it easy to run and manage applications in a way that works the same everywhere. It does this by putting your 
      application and everything it needs (like code, libraries, and settings) into a package called container.


04. What is Container?
    - Think of a Container like a box, Inside the box is your app and all its parts. No matter where you take the box your laptop, server or 
      the cloud, the app inside will always work the same way, without problems caused by missing files or different computer setups.


05. What is Docker Image?
    - A Docker Image is like a Blueprint or package that contains everything needed to run a software application inside a Docker Container.
      It Includes:
      a. The application code
      b. System libraries and tools
      c. Settings and dependencies
    
    - This package is read-only and cannot be changed once created. When you run an Image, Docker creates a Container from it, which is the
      running instance of that Image.


06. Docker Architecture
    - Docker is built on a client-server architecture, which means it has different parts that work together to make running and managing
      containers easy and efficient

    - Main Components of Docker Architecture

      a. Docker Client
            - This is what you interact with, usually through the command line (like when you type docker run). The client sends your command
              to the Docker Daemon.
    
      b. Docker Daemon (dockerd)
            - This is the background service (the brain of docker) running on your computer. It listens for commands from the client and does 
              all the heavy lifting. building running and managing containers and images.
    
      c. Docker Images
            - These are the blueprints or templates for your containers. An image contains everything needed to run an application code,
              libraries and settings.
    
      d. Docker Containers
            - These are the running instances created from Docker Images. Each container is an isolated environment where your application runs.
    
      e. Docker Registry
            - This is like a big warehouse where Docker images are stored and shared. The most popular registry is Docker Hub.
              When you run a command to start a container, Docker pulls the image from the registry if it’s not already on your computer.
    
      f. Docker Networks
            - These allow your containers to communicate with each other or with the outside world in a secure and organized way
    
      g. Docker Volumes
            - These are used to store data outside of containers, so your data isn’t lost when containers are stopped or deleted
    
    - How It All Works Together (Simple Flow)
        a. You type a Docker command (like docker run redis) in your terminal (the client).
        b. The Docker client sends this command to the Docker Daemon.
        c. The Daemon checks for the image (e.g., Redis). If it’s not on your system, it pulls it from the Docker Registry.
        d. The Daemon creates and starts a container from the image.
        e. Your application runs inside the container, isolated from the rest of your system.

