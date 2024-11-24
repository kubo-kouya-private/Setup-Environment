# How to set up ubuntu desktop

## Set up procedure

1. Updating packages
   
   ```bash
   sudo apt update -y
   ```

2. Installing packages for desktop environment

   ```bash
   sudo apt install xfce4 xfce4-goodies
   ```

3. Installing and enabling xrdp, which is necesssary to connect ubuntu server by RDP

   ```bash
   sudo apt install xrdp
   sudo systemctl enable xrdp
   sudo systemctl start xrdp
   ```

4. Configuring desktop session
   
   ```bash
   echo "xfce4-session" > ~/.xsession
   ```
5. sudo adduser xrdp ssl-cert

6. Configuring password

   ```bash
   sudo passwd ubuntu
   ```
