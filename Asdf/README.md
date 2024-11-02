# How to set up asdf in Ubuntu EC2 server

## Set up procedure

1. Installing packages

   ```bash
   sudo apt update
   sudo apt install -y git curl
   ```

2. Cloning asdf-vm repository

   ```bash
   git clone https://github.com/asdf-vm/asdf.git ~/.asdf --branch v0.12.0
   ```

3. Updating bashrc

   ```bash
   echo '. "$HOME/.asdf/asdf.sh"' >> ~/.bashrc
   echo '. "$HOME/.asdf/completions/asdf.bash"' >> ~/.bashrc
   source ~/.bashrc
   ```

## How to use asdf-vm

### How to install python

```bash
# Installing C compiler necessary for python
sudo apt install build-essential zlib1g-dev libssl-dev libbz2-dev libreadline-dev libsqlite3-dev liblzma-dev tk-dev

asdf plugin add python
asdf install python 3.9.20
asdf local python 3.9.20
```

### How to install Java

```bash
asdf plugin add java
asdf install java adoptopenjdk-17.0.8+7
asdf local java adoptopenjdk-11.0.20+8
```

### Other commands

```bash
#Listing all plugins
asdf plugin list all

#Listing all versions
asdf list all python
asdf list all java

#Listing all installed versions
asdf list python
asdf list java
```