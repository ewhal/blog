+++
date = "2016-05-14T20:40:50+10:00"
draft = true
title = "internet radio raspi"

+++

# Raspberry Pi Internet Radio Project

## BackStory

For IFB102 we were asked to make a raspberry pi project with 3 major themes: Hardware, Software and Networking.
Now my initial idea was to make a [piratebox](https://piratebox.cc/) due to it being quick, simple and very useful.
After some consultation and thought I decided to go with a internet radio Raspberry Pi project.

## Components
1. Breadboard
2. 2 10K potentiometers
3. 16x2 lcd screen
4. 20 plug to socket leads
5. 7 buttons

## Planning
Now before this project I only had very minor experience with GPIO ports. 
The initial plan was to setup all the hardware, then write the scripts and website to allow for interaction.


## Hardware
I started out by soldering leads unto the potentiometers and soldering the pins onto the 16x2 lcd screen.
Once that was done I consulted a [GPIO](http://raspi.tv/2014/rpi-gpio-quick-reference-updated-for-raspberry-pi-b) reference sheet for the Raspberry Pi model b+.
![GPIO layout](http://www.raspberrypi-spy.co.uk/wp-content/uploads/2014/07/Raspberry-Pi-GPIO-Layout-Model-B-Plus-rotated.png)

Once that was done I then connected leads to random unused GPIO ports and to ground. 
These leads then were connected to the buttons.
Now the buttons are for IP address, stop, start, prev, next, volume down and volume up.
The IP address button is the easiest solution to the fact that during the presentation I won't know what IP address the raspberry pi has.
I'd usually assign it a subdomain of pantsu.cat and use dynamic DNS but the university network wouldn't allow that.

## Software
Now QUT provided all students with a basic LCD script. I customized it based on the pin layout and got it working.
![LCD screen](https://u.pantsu.cat/hvwoxd.jpg)
The provided LCD script did not have scrolling text so I modified it to make the text scroll across the screen.
![final](https://u.pantsu.cat/gcxnda.jpg)
The best solution was to design a script that would handle all input from the hardware and have it startup on boot.
Which is exactly what I did with mpdstate.py.

## Servers
MPD and icecast were initally installed and setup.
Configurations can be found in the git repo.

## Conclusion
Overall this was a very enjoyable and educational assignment. With it I managed to deepen my knowledge on hardware and electronics in general.
If you wish to use any of this project it is licensed under MIT and can be found [here](https://git.pantsu.cat/ewhal/raspi)

