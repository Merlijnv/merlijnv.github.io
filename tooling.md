# Tooling
Here I am going to talk about which tooling I used and how I set up / created my hacking environments and tools.

## Kali
For my main kali / hacking machine I made a kali vm on my server at home using esxi just so I can configure everything myself in the vm and therefore use more resources. Furthermore, when I'm working on p4wnp1/dropbox, I can easily create an endpoint for the reverse shell. I have my own wireguard server running so I always have access to my server, even at school. I also linked the wifi chip in my server to the kali vm so that I can use it for wifi hacking.

In this environment I have installed kali full op with another [gobuster] (https://github.com/OJ/gobuster). this is a directory and dns fuzzer that I prefer.

## P4wnp1
I have a raspberry pi zero w where I 3d printed a case for and on which I run [P4wnp1 aloa](https://github.com/RoganDawes/P4wnP1_aloa) so I can use it as a hid hacking tool but also as a dropbox. I have written several payloads for this that you can read more about below. I also have an explanation of how I made the P4wnp1 function as a dropbox. [read more](p4wnp1)

## Raspberry pi 4
I also have a mobile kali running on my raspberry pi 4 that I can use if I want to have multiple screens.