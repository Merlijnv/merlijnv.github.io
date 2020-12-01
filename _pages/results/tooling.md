# Tooling
Here I am going to talk about which tooling I used and how I set up / created my hacking environments and tools.

- [Kali](#kali)
  * [Extra tools](#extra-tools)
  * [Terminal (ZSH)](#terminal--zsh-)
    + [Plugins](#plugins)
- [P4wnp1](#p4wnp1)
- [Raspberry pi 4](#raspberry-pi-4)
- [Dropbox](#dropbox)
- [Packet Squirrel](#packet-squirrel)
- [Wifi Pineapple](#wifi-pineapple)


## Kali
For my main kali / hacking machine, I made a kali VM on my server at home using ESXi just so I can configure everything myself in the VM and therefore use more resources. Furthermore, when I'm working on p4wnp1/dropbox, I can easily create an endpoint for the reverse shell. I have my self-hosted wireguard server running so I always have access to my server, even at school. I also linked the wifi chip in my server to the kali VM so that I can use it for wifi hacking.

### Extra tools
In this environment, I have installed kali full. But I also installed some extra tools that are not included.
- [gobuster](https://github.com/OJ/gobuster). this is a directory and DNS fuzzer that I prefer.
- [evil-winrm](https://github.com/Hackplayers/evil-winrm). The ultimate Windows Remote Management shell for hacking/pentesting.
- [git-dumper](https://github.com/arthaud/git-dumper). A tool to dump a git repository from a website.
- [pwntools](https://github.com/Gallopsled/pwntools). Pwntools is a CTF framework and exploit development library.
- [angr](https://github.com/angr/angr). angr is a platform-agnostic binary analysis framework.

### Terminal (ZSH)
Instead of using bash as terminal I am using zsh.
The Z shell is a Unix shell that can be used as an interactive login shell and as a command interpreter for shell scripting. Zsh is an extended Bourne shell with many improvements.
As addition to ZSH I also installed [oh-my-zsh](https://ohmyz.sh/).
This is a delightful, open source, community-driven framework for managing your Zsh configuration. It comes bundled with thousands of helpful functions, helpers, plugins, themes.
Those plugins and themes can be very usefull and productive.

The theme can give u alot of information. Like this extravagant example below.
![extravagant zsh](/images/extravagant.png)

Mine doesn't look this extra vagant. I use the [Powerlevel10K theme](https://github.com/romkatv/powerlevel10k). When using things like a git repository I will see info about the repository in that folder with unstaged changes and not pushed commits. This is realy helpful and also works for other things like python. I can also add my vpn ip to this when connected to vpn like htb.
![terminal theme](/images/terminaltheme.png)
![vpn ip](/images/vpnip.png)

#### Plugins
I am using multiple plugins that are realy productive and useful:
- **dircycle** When using cd or any other command where you need to select a dir you can cycle trough all the dir's by using tab.
- **safe-paste** When pasing a piece of code all enters will be ignored so that the code wont execute before you want it to.
- **sudo** When u fuck up like everyones do and forget to type sudo before your last command or your current command you can press esc twice to get sudo in front of your command.
- **zsh-autosuggestions** Does auto suggestion based on previously used commands.
- **zsh-syntax-highlighting** Highlights know commands and makes them red if they are not known
- **k** k is a zsh script / plugin to make directory listings more readable, adding a bit of color and some git status information on files and directories.
- **autojump** a faster way to navigate your filesystem by just typing j with the dir name. It works by maintaining a database of the directories you use the most from the command line.
![dircycle](/images/dircycle.png){: width="100%" style="border: 3px solid #2f690a"}
*example dircycle*
![syntax](/images/syntax.png){: width="100%" style="border: 3px solid #2f690a"}
*example syntax highlighting*
![k](/images/k.png){: width="100%" style="border: 3px solid #2f690a"}
*example k*
![autojump](/images/jump.png){: width="100%" style="border: 3px solid #2f690a"}
*example autojump*


## P4wnp1
![Rasberry pi 4 usb c gadget](/images/p4wnp1case.png){: width="36%" style="float:right; margin-top: -20px"}

I have a raspberry pi zero w where I 3d printed a case for and on which I run [P4wnp1 aloa](https://github.com/RoganDawes/P4wnP1_aloa) so I can use it as a hid hacking tool but also as a dropbox. I have written several payloads for this that you can read more about below. I also have an explanation of how I made the P4wnp1 function as a dropbox.
[read more](/results/p4wnp1)


## Raspberry pi 4
I also have a mobile kali running on my raspberry pi 4 that I can use if I want to have multiple screens.
Because I have a MacBook pro with those amazing USB c ports I can use the raspberry pi 4 USB c port to connect to it without any internet connection near.
This I accomplish by turning the raspberry pi 4 into a USB c gadget.
The raspberry pi 4 will be powered through the USB c port but also will be having an internet connection over that same port.
This was a little bit of a hassle because some of the needed components changed in the newest Kali Linux iso.
But after some time I got it to work.
I use Termius for the ssh connection and RealVNC for remote desktop control.
This way I can use the raspberry pi without the need of struggling by connecting with a network every place I am.
By using this I have a powerful hacking device on my MacBook Pro that I can also do some wifi hacking on by utilizing the raspberry pi 4 wifi chipset.
![Rasberry pi 4 usb c gadget](/images/rpi4c.jpg)
[*source usb c gadget*](https://www.hardill.me.uk/wordpress/2019/11/02/pi4-usb-c-gadget/)

## Dropbox
So I use my raspberry pi zero w and my raspberry pi 4 as a dropbox.
But how do I get this to work, what improvements did I add and how do I use this dropbox.
You can read more about this dropbox [here](/results/dropbox).

## Packet Squirrel
The Packet Squirrel by Hak5 is a stealthy pocket-sized man-in-the-middle. This Ethernet multi-tool is designed to give you covert remote access. Provides you with painless packet captures. This has secure VPN connections with the flip of a switch. 

Because I am the ICT guy at our scouting I was interested how secure our network is. We have a camera system that is connected to the network. I wanted to try if I could capture the camera packets of those camera's without anyone noticing it.

I got the Packet Squirrel connected it to one of the ethernet cables and added one cable where the cable was previously put in. I connected a usb thumb drive to the Packet Squirrel to save all the loot to.
![PacketSquirrel](/images/packetsquirrel.jpg){: height="500px"}
![PacketSquirrel zoomed in](/images/packetsquirrel2.jpg){: height="500px"}

At first I wanted to try to capture the rtsp packages but because we just got a new network the camera system couldn't connect to their static ip because we got now ip ranges.
Because of this I did get a tcpdump of the security camera system requesting it's static ip.
![Static IP TCP Dump](/images/statictcpdump.png)

I will do some more testing at scouting

## Wifi Pineapple
The Pineapple Tetra is a so-called Rogue AccessPoint or a tool that hackers and penetration testers use to check the WiFi network. The Pineapple Tetra can be used for various purposes such as:
- Reconnaissance
- Man-in-the-Middle
- Tracking
- Logging
- Report
- …and much more

I have done some work with the pineapple a couple semesters in advance but that was mainly looking what it was and what it could do but not advanced trying out of those features.

### C2
I used the cloud c2 environment I have set up earlier for the packet squirrel but this time I moved it to a digital ocean vps.
This way I can use the wifi pineapple and access it's features even offsite.
![cloud c2 wifi pineapple](/images/c2pineapple.png)

### testing out

I have the pineapple running and connected with a internet cable.
I let the pineap associate and I saw RDC comming by which is our scouting wifi name.
In my phone I saw the wifi also popping up as open network.
After tapping it on my phone I saw my phone popping up as client.
![clients](/images/clients.png)

### traffic capture

I can install dwall which captures all http requests and images.
This works really well but doesn't capture https traffic.
Which doesn't do alot because the percentage of encryption enabled in Chrome’s loaded webpages in October 2019 has reached 95%.
so I would only capture 5% off all the traffic.
![dwall](/images/dwall.png)

#### ssl split

I tried out sslsplit to check if I can capture https data.
But after generating a certificate and all it keeps getting a error on the victim.
This is because the certificate is not valid for that domain.
This is not great because this then only works for clients that don't check certificates.
![ssl split](/images/sslsplit.png)

### wpa2 enterprise

I saw a new option on the wifi pineappple since I last tried it which really interested me.
There was an option to generate a wpa2 enterprise certificate and after that possibly spoof such a access point.
![wpa2 enterprise](/images/wpa2enterprise.png)
I wanted to try this out at school but only with my own phone.
So I configured everything generated a certificate and whitelisted my phone mac adress.
I made sure only my own phone would be effected.

I did some recon and found the fontys ssid.
I cloned the access point so that this config would be used for the pineap.
After some reading I found out wherefore the downgrade attack option was.