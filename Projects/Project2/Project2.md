### **Project 2**

---

#### Container Platforms Selected
- **Docker**
  - In order to install Docker on your system, you need to first launch your VM and open a new terminal
  - Then, use the following commands to set up the docker repository. (**NOTE**, this does not install docker yet, only gets it ready)
    - sudo apt-get update
    - Use "sudo apt-get install" to install each of the following: apt-transport-https, ca-certificates, curl, gnupg, lsb-release
    - Add the Docker's GPG Key: curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
    - Next, type the command to setup the "stable" repository: echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu 
    $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null  (**All One Line**)
  - The Next step is to actually install the Docker Engine into your VM. 
    - Type another sudo apt-get update
    - Then insert the command, "sudo apt-get install docker-ce docker-ce-cli containerd.io" to install docker
    - Verify that docker is installed correctly by running the following program, "sudo docker run hello-world"
    - If it prints correctly, then you've done it!
  
- **Podman** 
  - First you need to navigate to your terminal in Ubuntu and enter the follwing commmands to get the setup started
    - sudo apt-get -y update
    - sudo apt-get -y install podman

#### Pulling a container image
- **Docker**
  - Using "sudo docker images" will let you view the images you have in the registry. 
  - Then use the command sudo docker image pull hello-world and it will store it to your machine
  - To view all images on docker use "sudo docker image ls*
  - ![image](https://user-images.githubusercontent.com/59904812/136669326-b7d74743-2930-4e03-a488-3ad3c251d059.png)

- **Podman**
  - Using "sudo podman pull (name of image)" will pull an image from the registry and display it to you. You could also use  podman build --pull=true
  - To view all images on podman you can use the same command as docker, "sudo podman image ls" or list

#### Running a container
  - First, containers are basically runnable instances of an image and it's obivous that it is running when ther is an active process inside of it. Initialzing a container or "Init containers" deal with initializing and preparing the actual environment you run the container on. Once you container is initialized, then it can run the actual enviornment. Once set it up, the other acutally runs the application.
  - To run and enter shell on docker, you will need the follwing steps.
    1. It may be important to note your container ID or name. Using "docker ps" you can get Container ID, Name, Status, Ports, Commands, and Images. 
    2. Use "docker exec -it <container name> /bin/bash to create a bash shell in your container.
    3. Then use "docker exec -it <container name> <command to execute>" to execute a command. 
  
  - To run and enter shell in podman, use the following steps.
    1. To run an image in podman, you can easily use "podman run image (command)", you can also use this for docker. 
  - To detach from the containers you can use -d (This runs the containers in the background and prints a new container ID) You can also use "Ctrl+p, then use Ctrl+q" (docker run -d IMAGE)

#### Logs & Status
  - To view the status and other information of a running container use the command, "sudo docker ps -a"
  - To view the logs of the container, use "docker logs <container_id> (Which you can get from the ps -a command)*
  - To view logs on podman use, "podman logs" command
  - To view the status of podman containersyou can use the same as docker, "podman ps"
  
 #### Stopping Containers
  - To pause a container use, "pause docker" or "pause podman"
  - To restart a container, use "docker restart" or podman restart"
  - To resume a container use the "docker unpause <container_name>" or "podman unpause <container_name>"
  - To stop and kill containers, use docker stop, and docker kill. This is the same with the podman containers as well. 
