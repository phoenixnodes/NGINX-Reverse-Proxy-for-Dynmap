## Install NGINX Reverse Proxy on Ubuntu 18.04 for Dynmap

### Requirements
- A Minecraft server with the Dynmap plugin installed and running.
- A VPS with Ubuntu 18.04.


### Step 1: Install NGINX

Run these commands to update your system and install NGINX:

```
sudo apt update
sudo apt-get install nginx
```

### Step 2: Add Certbot PPA

You'll need to add the Certbot PPA to your list of repositories. To do so, run the following commands on the command line on the machine:

```
sudo apt-get update
sudo apt-get install software-properties-common
sudo add-apt-repository universe
sudo add-apt-repository ppa:certbot/certbot
sudo apt-get update
```

### Step 3: Install Certbot

Run this command on the command line on the machine to install Certbot:

```
sudo apt-get install certbot python3-certbot-nginx
```
