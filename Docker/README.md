# How to set up docker engine in Ubuntu EC2 server

## Set up procedure

1. Installing packages

   ```bash
   sudo apt update
   sudo apt install ca-certificates curl gnupg
   ```

2. Add docker repository in APT

   1. Downloading public GPG of docker in order to enable APT to validate package reliability.

      ```bash
      sudo install -m 0755 -d /etc/apt/keyrings
      sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
      sudo chmod a+r /etc/apt/keyrings/docker.asc
      ```

   2. Adding public repository of docker into APT in order to install docker package.

      ```
      echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
      ```

   3. Updating APT repository
   
      ```bash
      sudo apt update
      ```

3. Creating docker group
   
   ```bash
   sudo groupadd docker
   sudo usermod -aG docker $USER
   ```

4. Installing docker engine

   ```bash
   sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
   ```

5. Adding the current user into docker group in order to use docker command without sudo

   ```bash
   sudo usermod -aG docker ${USER}
   newgrp docker
   ```

