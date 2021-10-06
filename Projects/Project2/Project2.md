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
- **Podman**
  - Using "sudo podman pull (name of image)" will pull an image from the registry and display it to you. You could also use  podman build --pull=true
  - To view all images on podman you can use the same command as docker, "sudo podman image ls" or list
