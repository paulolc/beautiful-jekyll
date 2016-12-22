---

layout: post

title:  "IoT(wifi) module for MakeBlock's mBot"

date:   2016-11-20 23:39:01 +0100

categories: robots electronics documentation

---



# Easily make an mBot IoT Communicator module for $3!

## Introduction

This howto will explain how to easily and cheaply, make a Communicator for mBot to connect it to the network via WiFi.  in addition to the 
Bluetooth and 2.4GHz already available by MakeBlock.



## Materials

- WeMos D1 mini (or compatible) (ESP8266 E12 breakout board)
- wires
- 2x Leds
- 2x 470Ω resistors
- 2x 8 pin header female connector
- 1x 3 pin header male connector
- 1x 4 pin header male connector

(Not included in the price: jumper wires, breadboard, soldering iron, solder)

## Upload esp-link firmware to the WeMos board

1. Download esp-link firmware binary images from [esp-link github](https://github.com/jeelabs/esp-link/releases). (I've used the current stable release version  [esp-link-v2.2.3](https://github.com/jeelabs/esp-link/releases/tag/v2.2.3))
1. Uncompress the esp-link firmware binary images to a folder of your choosing.
1. There are several tools to flash firmware images on the esp8266. I've used the [nodemcu-flasher](https://github.com/nodemcu/nodemcu-flasher). 
1. Connect the WeMos to the PC and prepare the image to flash according to instructions there. 



1. On the 'Config' tab Specify all the esp-link firmware image parts and their respective memory offsets like the picture below. (Mark the left-side checkboxes!)

[![](imgs/esp-link_firmware_flasher_small.png)](imgs/mCore+WeMos.png)

6.  and Flash!

[![](imgs/nodemcu-flasher_small.gif)](imgs/nodemcu-flasher.gif)


## Connect the WeMos to the mBot Communicator interface pins

Use the jumper wires and the breadboard to test the connection.

[![](imgs/mbot_iot-breadboard_small.jpg)](imgs/mbot_iot-breadboard.jpg)
[![](imgs/mCore+WeMos_small.png)](imgs/mCore+WeMos.png)

## Let's play with the mBot led strip




## Redirect the computer serial port to the network (optional)

To program the default firmware that comes with the mBot you can send commands to mBot serial port that is available

To be able to use the mBlock IDE to program the default firmware that comes with the mBot, using this IoT Communicator you need 
to redirect the computer serial port to the ip address and port of the WeMos. 

If you don't want to use the mBlock IDE, it's even easier! 



On Windows you can do this using the HW VSP3 software.




can be used to achieve this.  _"(...)HW VSP is a software driver that adds a virtual serial port (e.g. COM5) to 
the operating system and redirects the data from this port via a TCP/IP network(...)"_ 



http://new.hwg.cz/files/download/sw/version/hw-vsp3-single_3-1-2.exe

## Verify that it works















MakeBlock's mBot is a very interesting and relatively cheap educational hackable robot. It comes with a caster plus two wheels
powered by two regular small dc motors. The chassis is metal based and quite sturdy and the controller board is the MakeBlock's 
mCore, an Arduino compatible board with a good set of sensors and actuators onboard such as, a luminosity sensor, an IR emitter, 
an IR receiver, a button, and a buzzer. The mCore is also easily expandable using a unique and interesting RJ25 based 
pluggable system with four of these connectors available for expansion with the MakeBlock's "Me" electronic modules.

## "Firmata"?

## Look ma, no wires! It's the Communicators!

The mCore board 

It can be controlled wirelessly via either its Bluetooth or 2.4Ghz RF based communication modules. 



Unless you are interested in I bought the mBot variant with the Bluetooth one.




## How about WiFi?

Yes, how about wifi? Everything nowadays needs to be connected to the Internets, "IoT compatible" as they say. Well, in fact, MakeBlock 
already has a WiFi Communicator module, the [Me WiFi](http://learn.makeblock.com/en/me-wifi/). 

![Makeblock's Me Wifi Module](imgs/me-wifi.png)


### Me Wifi? Well, it's complicated...  :(
This module has several disadvantages:

|         |           |   |
| ------------- |:-------------:| -----:|
| It needs to be plugged into one of the mCore RJ25 ports so, you end up with one less port to expand mBot with.      | ![alt text](imgs/me-wifi-rj25.png) | |
| You need to explicitely write code and implement somekind of serial based communications protocol using the MakeBlock's provided MeWifi library to take advantage of the wireless capabilities of this module.  | ![alt text](imgs/me-wifi-code.png)      ||
| You cannot use the mBot's default firmware that allows it to be programmed "online" using mBlock... |  [TODO: mBlock pic with prohibition sign over it ]   ||
| ...Which also means that it's not possible to control it out of the box. That is, without any additional programming. | [TODO: mBot remote control with a prohibition sign over it ]  ||
| No obvious place to mount it on mBot's chassis | [TODO: mbot exploded pic with Me Wifi module and a question mark]      ||
| It's a bit expensive for me. (~$35 after shipping and tax) | [TODO: Me Wifi with some expensive symbology over]      ||



As you can see, even if you fully reprogram the mBot's firmware you'll loose some of the characteristics that make mBot a pretty good educational robot, its ability to be ready to play out-of-the-box. 


# Easy&Cheap DIY IoT Communicator

Another great characteristic of mBot is that it's easily hackable. The socket where you plug the bluetooth or the 2.4Ghz wireless communicator modules is a very simple and straightforward one. Having nothing more than the pins you would normally expect on a serial interface: power, rx/tx, reset and "data ready". 

Now, if only I had an easy way to connect a circuit to the network via WiFi... Wait! Of course, there's the ESP8266! What else? :)

I've been playing a lot lately with the ESP8266, sharing and experiencing myself the excitment around these little buggers that has been spread all across the internet. They are very, very cheap, easy to setup with pretty impressive specs for the price. There is now a huge community, documentation and material for it. What started by being a 


[TODO: Present the ESP8266]

The cheapest, more arduino friendly esp8266 breakout board I could find was the WeMos D1 mini. 

[TODO: Present the Wemos D1 mini]



[TODO: Present esp-link as IoT firmware]



So, the idea was set. 

serial interface circuit + wemos d1 mini + esp-link firmware + network to serial port redirector (optional)



## The "Let's see if it will work" test


<img src="imgs/mbot_iot-breadboard.jpg" alt="The breadboard test" height="200" >

## The stripboard circuit build

[TODO: the schematics pic ]

<img src="imgs/mbot-iot-fritzing.png" alt="The breadboard test" height="200" >


[TODO: the fritzing diagram ]
[TODO: the circuit being built pics ]
[TODO: the final version and mounted pics ]


## Upload the esp-link firmware

[TODO: instructions on how to upload the firmware ]


## Configure the serial, reset and led pins on esp-link

[TODO: instructions on how to configure the serial, reset and led pins on esp-link ]


## Play!!!

[TODO: mBlock + node.js + bash(!) + browser?   test programs]
