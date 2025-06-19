01. List Only Running Containers
    - docker ps
      This command shows only containers that are currently running. The output includes details like container ID, image, command, status, ports, and name


02. List All Containers (Running and Stopped)
    - docker ps -a
      This command lists all containers both running and stopped. You can see which ones are active and which have exited by checking the "STATUS" column. For example, "Up 2 minutes" means running, while "Exited (0) 5 minutes ago" means stopped
      docker run busybox ping google.com


03. List Only Stopped Containers
    - docker ps -a --filter "status=exited"
      This shows only containers that have stopped (exited)


04. Run a Container from an Image
    - docker run hello-world
      Starts a container using the hello-world image. If the image isn’t on your computer, Docker downloads it and runs it. The Container 
      prints the message and then stops.


05. Give Your Container a Name
    - docker run --name mycontainer ubuntu
      Runs an Ubuntu container and gives it the name mycontainer instead of a random name. This makes it easier to manage


06. Run a Container in the Background (Detached Mode)
    - docker run -d nginx
      Runs an Nginx web server in the background. You get your terminal back right away, and the container keeps running


07. Run a Container with Port Mapping
    - docker run -p 8080:80 nginx
      Runs an Nginx container and maps its internal port 80 to your computer’s port 8080. You can access the web server by visiting localhost:8080 in your browser.


08. Run a Container Interactively (Get a Shell Inside)
    - docker run -it ubuntu /bin/bash
      Starts an Ubuntu container and opens a terminal shell inside it, so you can run commands as if you were using a regular Linux system


09. Override the Default Command
    - docker run ubuntu echo "Hello from Docker"
      Runs an Ubuntu container and, instead of starting the default program, runs the echo "Hello from Docker" command inside the container


10. Create a Container (But Don’t Start It Yet)
    - docker create hello-world
      This command prepares a new container from the hello-world image, but does not start it.
      Think of it like building a car in the factory but not turning it on yet.
      You get a container ID (like 91ee7db...), which you can use to start or manage the container later.


11. Start a Container
    - docker start <container_id>
      This command turns on (starts) a container that was created earlier but is currently stopped.


12. Start a Container and See Its Output
    - docker start -a <container_id>
      The -a (attach) option shows the output of the container in your terminal as it runs.
      Useful for containers that print something and then stop (like hello-world).


13. Stop a Running Container
    - docker stop <container_id or name>
      This command safely stops a container that is running.
      It’s like turning off the engine of a car that’s already on.


14. Run a Container (Create + Start in One Step)
    - docker run hello-world
      This is a shortcut that creates and starts a new container in one step.
      It’s like building the car and immediately driving it.


15. Remove the stopped container:
    - docker rm <container_id_or_name>
      This deletes the stopped container from your system


16. Remove All Stopped Containers at Once
    - docker container prune
      This command will delete all containers that are not running (you may be asked for confirmation)


17. View Logs
    - docker logs <container_name_or_id>


18. See logs in real-time (as they happen)
    - docker logs -f <container_name_or_id>


19. Show only the last N lines
    - docker logs --tail 50 <container_name_or_id>


20. Show logs with timestamps
    - docker logs -t <container_name_or_id>


21. See logs from a specific time
    - docker logs --since 1h <container_name_or_id>


22. Execute command inside a running container
    - docker exec -it <container_name_or_id> <command>
      docker exec -it mycontainer sh

