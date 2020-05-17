## Install NGINX Reverse Proxy on Ubuntu 18.04 for Dynmap

### Requirements
- A Minecraft server with the Dynmap plugin installed and running.
- A VPS with Ubuntu 18.04.
- A domain.


### Step 1: Point your domain to your VPS IP address

These steps may vary for each domain registrar, this tutorial will explain how to point your domain to your VPS IP via CloudFlare.

- Navigate to CloudFlare.com and login
- Choose the domain you want to have your map on
- Select "DNS" from the menu at the top of the screen
- Click "Add Record"
- Set "Type" to "A"
- Set "Name" to whatever you want your subdomain to be (Eg: map)
- Set "IPv4 address" to the IP Address of your VPS
- Click "Save"

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

### Step 7: Completion

To verify that everything is working, visit your map subdomain (Eg: map.yoursite.com). You should be able to view your Dynmap without using your server's IP and Dynmap port.
