# Tooling

Hier ga ik vertellen over welke tooling ik heb gebruikt en hoe ik mijn hacking environments en tools heb ingesteld/gemaakt.

## Kali
Voor mijn main kali/hacking machine heb ik op mijn server thuis door middel van esxi een kali vm gemaakt dit omdat ik zelf alles kan instellen in de vm en dus ook meer resources gebruiken. Verder kan ik hiermee wanneer ik bezig ga met p4wnp1 makkelijk een endpoint maken voor de reverseshell. Ik heb mijn eigen wireguard server draaiende waardoor ik altijd toegang heb tot mijn server, ook op school. Verder heb ik de wifi chip in mijn server gekoppeld aan de kali vm waardoor ik deze kan gebruiken voor wifi hacking.

In deze environment heb ik kali full op geinstalleerd met nog [gobuster](https://github.com/OJ/gobuster). dit is een directory en dns fuzzer die ik fijner en sneller vindt.

## P4wnp1
Ik heb een raspberry pi zero w waar ik een case voor 3d heb geprint waar ik [P4wnp1 aloa](https://github.com/RoganDawes/P4wnP1_aloa) op draai waardoor ik deze kan gebruiken als hid hacking tool maar ook als dropbox. hiervoor heb ik meerdere payloads voor geschreven waar je nog verder over kan lezen. Verder heb ik ook een uitleg hoe ik de P4wnp1 als dropbox heb laten functioneren. [read more](p4wnp1)

### Payloads
Voor de payloads van de p4wnp1 kan je op mijn (en Rick Theeuwes) [github repository](https://github.com/Riqky/Payloads) kijken.

## Raspberry pi 4
Verder heb ik ook nog een mobile kali op mijn raspberry pi 4 draaien die ik kan gebruiken als ik meerdere beeldschermen wil hebben.