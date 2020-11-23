![p4wnp1](/images/p4wnp1.jpg){: width="400px" align="right"}
# P4wnp1
P4wnP1 A.L.O.A. by MaMe82 is a framework which turns a Rapsberry Pi Zero W into a flexible, low-cost platform for pentesting, red teaming and physical engagements ... or into "A Little Offensive Appliance".

## Payloads
For the payloads of the p4wnp1 you can check my (and Rick Theeuwes) [github repository](https://github.com/Riqky/Payloads).

## Hardware manipulation
One great thing about p4wnp1 is that u can manipulate it to send different manufacture id's, product id's and product names.
This way when a company secured their systems to only accept certain keyboard you can change this value and be able to still run a HID attack.
You can search for the correct id's on [device hunt](https://devicehunt.com/all-usb-vendors).
After that just change it in usb settings on the p4wnp1.
![Hardware manipulation](/images/hardware.png)

## Lecture
I am planning to do a lecture about p4wnp1 and the payloads I have made.

## Dropbox
I have modified the p4wnp1 so that I can also use it as dropbox since it is a real small form factor.
More information about how I modified the p4wnp1 to be a dropbox you can read [here](/results/dropbox#p4wnp1)

## Covert channel
As an extra challenge I wanted to use covert shell to create a shell and interact with it even when the pc is not connnected to any internet connection.

I made a script that runs a covert shell by connecting the pc to the p4wnp1 this process keeps connecting receiving and sending data and after that deleting all the evidence and connection. In the next image you see the powershell that can  be easily hidden but is showing for testing purposes. The connection with the p4wnp1 is slow but not tracable. The p4wnp1 creates an screen session which I can open and interact with when I am connected to the p4wnp1 this can also be done with an vpn connection to the p4wnp1. The p4wnp1 only needs to be in range of the target to keep the covert channel connected.

![Covert channel shell](/images/covertshell.png){: width="63%" float="left"}
![p4wnp1 result](/images/p4wnp1result.jpg){: width="36%" float="right"}

The covert channel looks for wireless adapater (does not matter if connected or not) and uses it to communicate with the p4wnp1 in a covert matter.
[*source covert channel*](https://p4wnp1.readthedocs.io/en/latest/Payload-Subfolder/Wifi-Covert-Channel/)

This covert channel can be used to make a persistent shell without anyone detecting.

## Rubber ducky
All the payloads created on p4wnp1 can be converted to ducky script.
The Rubber ducky is a HID attack device that looks like a normal usb.
![rubber ducky](/images/rubberducky.jpg)
