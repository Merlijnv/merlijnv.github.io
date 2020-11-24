# My contribution

In the Intersct project I mostly helped others with the pentests which they where doing and helping them by mentioning new attack vectors they didn't see.
I also did some work on fixing the air scrubber project and pentesting one of the smart screens.
Besides that I worked on making the airscrubber project transferable to the stakeholder.


## Air scrubber
On the airscrubber I fixed the docker that should be in the repository but that was missing from the group that delivered the project. The stakeholder didn't get the project running in the beginning.
I made a gitlab ci cd that made it possible to automatically generate the images of the services when we bring out a update.
This way the stakeholder has 1 simple file that he can use to deploy all the services in a docker environment and all the building will be done automatically even when another group continues in the future.
I also fixed the hardcoded code that should be dynamic like backend ip and credentials of docker.

## Smart screen
I tested 1 of the smart screen the one with the least features.
I tried to use rs232 which I got to work but didn't have any impact to be a cyber attack.
I also did a scan on the network and found only 1 open port which was the management api which we declared safe on the other screen.
besides that I also tried all the peripherals but no success.
This version of the board also doesn't have update OTA so that attack vector was also not possible.

I also helped with the other smart screen but more in a passive matter by helping to get thing to work and searching new attack vectors.

## Smart watch

I did work on pentesting my own smartwatch here I didn't have much success.
I tried to intersept the bluetooth and wifi connection.
I also tried hijacking the bluetooth connection with the smartwatch and with the phone.
This didn't have much success.