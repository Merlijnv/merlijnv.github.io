# dropbox
I have 2 raspberry pi's that I use for red teaming. One of them is p4wnp1 which is an HID hacking tool that is running Kali Linux on a raspberry pi zero.
I also have a raspberry pi 4 that I use as a dropbox. I will describe how I got this to work and how I set everything up.

## command and control server
To get this whole thing to work I need a command and control server.
This server can be used by the dropbox to connect to it.
This server must be always reachable otherwise the dropbox can't be connected to so will be useless.
This server can be a digital ocean server because I have a server at home I could also use that but for security reasons, I will use a digital ocean VPS.
I have created a droplet with the least resources because there isn't much required from this server.
![Digital Ocean](images/digitalocean.png)

One of the key components of a dropbox is to get a connection remotely after dropping it somewhere.
This can be accomplished by a reverse ssh connection or a reverse VPN connection.
For this to work 

## P4wnp1


### Revserse vpn gateway

## Raspberry pi 4
I already have Kali Linux for arm installed on my raspberry pi 4 but this is not enough for using it as a dropbox.
To set this up you want it to be able to be dropped somewhere easy and fast and connect to it remotely after dropping it.



### Autossh

## Improvements
I have attached a wireless USB adapter to have more range and wifi hacking possibilities.
I also handmade a small ethernet cable to make it more convenient when dropping it and making it less bulky.
There is an external battery to make it possible to drop in places where you can't use a wall socket.
![pi4 dropbox](images/dropboxpi4.jpg)



# Usages
