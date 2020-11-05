# dingdong

Connecting your old fashioned door-bell (9V AC) with Homematic CCU2 (or other). The door bell usually is activated via a 9V AC transformer (see poto).

## What it does
If your door-bell rings your Homematic CCU2 is called, running a program for e.g. triggering a push-notification or switching on light.
    
## How it works

A typical door-bell works like this: A switch connects transformator with the bell. 
You'll need to cut this connection and put a small module in between. See pictire 'trafo.png'.
No worries, the door-bell will keep working, even if this module is broken :-D
    
The button press of door-bell is detected by measuing the current. It triggers a routine sending a HTTP request to CCU2 running a program.
The program on CCU2 can send a push-notification to your mobile or switch on the light or whatever.

## What you'll need
- Arduino, NodeMCU (ESP8266), USB to micro-USB, USB-charger
- A bit of electronic components: 2R (1W), 1kR, 22kR, 10uF, 10kR, NPN transistor like BC548, PCB or breadboard, a bit of wires.
See 'board ding dong.png' how it looks.

## Preperations for CCU2
Set up a program on you CCU2 which then will be called:
Details here: https://www.homematic-inside.de/software/xml-api
- You'll find the program-ID by calling (replace the IP) http://192.168.XXX.XXX/config/xmlapi/programlist.cgi
- Add your program-ID to the code
