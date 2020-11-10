# Lab

I have a homelab at home where I run my virual machines such as my development server.
Before this semester this was running a setup where all the severs where accessible from my home network devices and vice versa.
But this isn't really secure because when a hacker can compromise one of my servers they have full access to my home network.
I wanted to fix this.


## Plan

I want to create a second network on my esxi server which is not connected directly to my home network.
I will add a firewall which will be connected to my home network and also the lab network.
This firewall will get a dmz from the home network router.
I also want to add a ids to detect when there is an intruder on the network.

## Firewall

### pfSense
At first I just installed pfSense because I already have some experience with it because of CSa and CSb.
I started setting everything up added rules which prevented communication between my lan and wan network except my pihole.
I also tried to setup a vpn for remote access.
But after tinkering around I found out pfSense only supported openvpn.
I have multiple wireguard servers which I use.
So I wanted to use wireguard on my firewall.
I found packages to install this on pfSense.

But after trying to get it to work which failed I found OPNSense which included wireguard and also has some other nice extra features.

![not running service](images/wgnotworking.png)

### OPNSense

I have set up my OPNsense by using the iso from their site.
The setup is almost exactly the same as pfSense because OPNsense is a fork of pfSense.
Firstly I wanted to try and get the wireguard to work because that's the biggest reason to switching to OPNsense.
At first I tried but the service didn't want to start after some time I found out I was doing something wrong with my ip's.
So I deleted everything of wireguard and started again from scratch.
I set up the server and then generated a peer on my phone. After that I added the peer settings to my OPNsense.
I started the wireguard server and it was running!
I added all the needed rules.
![wg rules 1](images/wgrules1.png)
![wg rules 2](images/wgrules2.png)
![wg rules 3](images/wgrules3.png)
After adding those rules I configured my peer to connect to the public ip of my home router and added a port forward to the homelab firewall(After all is working this will be the dmz instead of port forwards).
After configuring everything I turned on my phones data and connected to the vpn.
I tried to communicate with the kali that was running inside the firewall lan network and it worked!
I have a connection and it also shows up in the interfaces.
![wg working](images/wgconnection.png)
![wg interfaces](images/wginterfaces.png)

## Configuration control and backup

Because I don't want to lose my changes when something goes wrong and also track what I am changing I wanted to use github to manage my configuration.
OPNsense has a plugin to get this to work. I installed it generated a ssh key for this use and added it to my github.
After setting up the repo and adding all the credentials it worked! the whole config is saved in 1 .xml file
![backup succesful](images/backup.png)

And offcourse after working in this sometime I had to change the theme to dark mode.
![dark mode](images/darkmode.png)

## Intrusion detection
Because this will be a set of servers accessible from the outside I want to have a intrusion detection system.
OPNsense has multiple plugins for differnt rule sets like: Proofpoint ET Pro ruleset, PT Research ruleset, IDS Snort VRT ruleset.
So I had to do some research on those rulesets which will be a good one for my scenario.
After some searching I registered for ET Pro ruleset and installed it.
After installing it and enabeling it I needed to restart and it works.
Immediatly having some blocks which arent really harmfull but not needed from spotify.
![ips block](images/ipsblock.png)

I will later on see if I can expand this intrusion detection by some of my own rules.

## HAproxy
because I use my lab inviroment sometimes for multiple servers I need to have some kind of loadbalancing/reverse proxy for when I want to use multiple servers on http or https.
I have in the past tried both HAproxy and nginx and I am going to use Haproxy as a solution to this.
OPNsense has a plugin for HAproxy so the setup isn't that hard.

## Acme
One of the great advantages to having a firewall with HAproxy is that you can centeralize your certificate generation and usage.
On all my servers that I open up to the outside I want to be able to add a valid certificate.
I can do this by using letsencrypt and acme.
But before I set this up for my servers and HAproxy I want to set it up for the firewall itself.
But I only will generate the certificate and install it but I wont enable access to the firewall from outside of the network.


