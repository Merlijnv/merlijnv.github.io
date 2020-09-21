# dropbox
I have 2 raspberry pi's that I use for red teaming. One of them is p4wnp1 that is a HID hacking tool that is running kali linux on a raspberry pi zero.
I also have a raspberry pi 4 that I use as a dropbox. I will decribe how I got this to work and how I set everything up.

## command and control server
To get this whole thing to work I need a command and control server.
This server can be used by the dropbox to connect to it.
It is necessary that this server is always reachable otherwise the dropbox can't be connected to so will be useless.
This server can be a digital ocean server but because I have a server at home that is alway running I will use it for now.

One of the key components of a dropbox is to get a connection remotely after dropping it somewhere.
This can be accomplished by a reverse ssh connection or a reverse vpn connection.

## P4wnp1


### Revserse vpn gateway

## Raspberry pi 4
I already have kali linux for arm installed on my raspberry pi 4 but this is not enough for using it as a dropbox.
To set this up you want it to be able to be dropped somewhere easy and fast and connect to it remotely after dropping it.

[pi4 dropbox](dropboxpi4.jpg)


## Autossh

## Improvements



# Usages
