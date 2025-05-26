# Docker-Networking-Containers
This is a basic networking with docker containers 

## STEPS
1. This pulls the ubuntu image from DockerHub
    ```
    docker run ubuntu
    ```
2. This lists the docker images present locally
    ```
    docker images
    ```
3. (Container 1) - This runs the `ubuntu image` interactively
    ```
    docker run -it ubuntu bash 
    ```
4. (In another tab) - This checks the `Process Status` of the images, in order to see running images, you can add `-a`
    ```
    docker ps
    ```
5. (Container 2) - This runs the `ubuntu image` interactively
    ```
    docker run -it ubuntu bash
    ```
6. (container 1) - This installs `sudo`
    ```
    apt install sudo -y
    ```
7. (container 2) - This installs `sudo`
    ```
    apt install sudo -y
    ```
8. (both) - This installs `openssh-server` for `ssh` connection
    ```
    apt install openssh-server -y
    ```
9. (both) - This checks `ssh` status
    ```
    service ssh status
    ```
10. (both) - This `starts` `ssh`
    ```
    service ssh start
    ```
11. (both) - This checks `ssh` status to verify if it has started successfully
    ```
    service ssh status
    ```
12. (both) - This installs `iproute2` so that we can get the `ip` of the container for `ssh`
    ```
    apt install iproute2 -y
    ```
13. (both) - This installs `vim` for creating a file. Used to create the `Publice Key`
    ```
    apt install vim -y
    ```
14. (both) - This generates new `ssh` keys, both `private` and `public`
    ```
    ssh-keygen
    ```
15. (both) - This changes directory to the `.ssh` folder where the keys are stored
    ```
    cd /root/.ssh
    ```
16. (container 1) and copy the public key - This shows the `Public Key`
    ```
    cat id_ed25519.pub
    ```
17. (container 2) and past container 1's pub key - This creates the `authorized_keys` file. Use `ESC` and `wq` to save the file.
    ```
    vim authorized_keys
    ```
18. (container 2) and copy the ip - This shows the `ip` of the container
    ```
    ip addr
    ```
19. (enter container 2 hostname and ip) or `ssh root@172.17.0.3` - This `ssh` into the container 2
    ```
    ssh d281d92fb1e2@172.17.0.3
    ```
