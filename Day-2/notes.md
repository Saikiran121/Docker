01. docker run
    - The docker run command is how you create and start a new container from a Docker image. It's the main way to launch applications with
      Docker.


02. What Happens When You Use docker run?
    a. Check for the Image
        - Docker looks for the image you specified (like redis or ubuntu) on your computer.
        - If the image isn't found, Docker downloads it from an online registry (like DockerHub).
    
    b. Create the Container
        - Docker takes the image (which is like a blueprint) and creates a new container from it.
        - The container is a running, isolated environment based on that image
    
    c. Set Up the Environment  
        - Docker applies any options you gave (like port mapping, container name, or running in the background)
        - For example, -p 6379:6379 maps ports, --name my-redis gives your container a name, and -d runs it in the background.

    d. Run the Command
        - Docker starts the main program inside the container. For Redis, it starts the Redis server. For Ubuntu, it might start a shell if you ask 
          it to.
    
    e. Container is Running
        - Your application is now running inside the container.
        - If you used attached mode (default), you see the output in your terminal and can interact with it
        - If you used detached mode (-d), the container runs in the background and you get your terminal back


03. Overriding Default Commands in Docker
    - If the Docker image sets a default command with CMD, you can replace it by simply adding your own command at the end of the docker run
      command.
    - Eaxmple: docker run busybox echo hello
               docker run busybox ls


04. Docker Container Lifecycle 
    - A Docker container goes through several stages from creation to removal. Understanding these stages helps you manage containers better and
      know what’s happening at each step.
    
    a. Created
        - The container is set up from an Image but hasn't started running. Its like a car built in a factory but not yet driven.
    
    b. Running
        - The Container is now working, running the app or process you asked for. This is like driving the car on the road.
    
    c. Paused
        - The Container and its processes are frozen. It's like stopping the car at a red light, engine still on, but not moving.
          You can unpause it to continue.
    
    d. Stopped
        - The Container is turned off, the app stopped running, but the container still exists. Its like parking the car and turning off the engine.
    
    e. Deleted (Removed)
        - The container is completely removed from your system. Its like scrapping the car gone for good, freeing up space.


05. How to Get the Logs of a Docker Container
    - To see what’s happening inside a Docker container like error messages, outputs or status updates you can view its logs.

    - These logs show everything the application inside the container writes to standard output (stdout) and standard error (stderr)

    - Basic command to view logs: #docker logs <container-name/id>

    - Shows you all the messages and outputs from the container’s main process.

    - Works for both running and stopped containers


06. How to execute commands in a running container
    - The docker exec command lets you run any command inside a running container without stopping it. 

    - This is useful for checking, debugging, or managing the container when its running.

    - Basic Syntax
      docker exec [options] <container_name_or_id> <command>
      <container_name_or_id>: The name or ID of the running container where you want to run the command.
      <command>: The command you want to run inside that container.

    - Run a simple command inside a container
      docker exec mycontainer ls /app
      Lists files inside the /app folder of the running container named mycontainer.

    - Open an interactive shell inside a container
      docker exec -it mycontainer sh
      Starts a shell session inside the container so you can run commands interactively (like using a terminal inside the container).

    - Run a command in the background
      docker exec -d mycontainer touch /tmp/testfile
      Runs the command to create a file inside the container but doesn’t attach your terminal to it.





