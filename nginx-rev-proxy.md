## Install NGINX Reverse Proxy on Ubuntu 18.04 for Dynmap

### Requirements
- A Minecraft server with the Dynmap plugin installed and running.
- A VPS with Ubuntu 18.04.
- A domain.


### Step 1: Point your domain to your VPS IP address

These steps may vary for each domain registrar, this tutorial will explain how to point your domain to your VPS IP via CloudFlare.




### Step 2: Install NGINX

Run these commands to update your system and install NGINX:

```
sudo apt update
sudo apt-get -y install nginx
```

### Step 3: Add Certbot PPA

You'll need to add the Certbot PPA to your list of repositories. To do so, run the following commands on the command line on the machine:

```
sudo apt-get install software-properties-common
sudo add-apt-repository universe
sudo add-apt-repository ppa:certbot/certbot
sudo apt-get update
```

### Step 4: Install Certbot

Run this command on the command line on the machine to install Certbot:

```
sudo apt-get -y install certbot python3-certbot-nginx
```

### Step 5: Download proxy script

Run this command to download the proxy script and start it, follow the on-screen commands:

```
wget https://raw.githubusercontent.com/TehloWasTaken/side-scripts/master/proxy.sh && bash proxy.sh
```

### Step 6: Restart NGINX

Run this command to restart NGINX:

```
sudo service nginx restart
```
