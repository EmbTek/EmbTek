---
layout: post
title: Wifi Photobooth
subtitle: QT/C++ Project 
post_author: Artur Sparwasser
cover-img: /assets/img/booth_top_free.png
thumbnail-img: /assets/img/booth_top_free.png
share-img: /assets/img/booth_top_free.png
tags: [QT, C++, Connectivity]
---

## Features

![booth_features](/assets/img/booth_features.png){: .mx-auto.d-block :}

**Great that you are here! Lets have a look under the hood of our wifi powered Photobooth**



Since I am an embedded software developer, who previously was concentrating on writing very efiicient and high performant C code, my objective programming skills were very low too not given at all.
Learning C++ and writing a cool iOS app was my personal goal to broaden my programming horizons.

Using [QT](https://www.qt.io/) seemed to be a perfect fitting solution to get most of this project under one roof. I saw the possibility to compile the same GUI for various (desktop, iOS, Android, even embedded) targets, learn C++ and improving my previously webpage based booth.

As expected otherwise the things turned out to be not so easy as I thought. First I got into dead end during developing the iOS app. In first steps the GUI worked smoothly as qtQuick application elements and I was good hope till I needed to interact with iOS native "drivers" to be able to print or even send emails. Additionally debugging turned out to be a nightmare with my elderly MacBook Pro. Since I am a newbie to app development these reasons let me to rethink my plan.

**In my new goal I put a raspberryPi Model 3 into center of the show and here is the final and extendable application:**

![booth_overview](/assets/img/booth_overview.png){: .mx-auto.d-block :}

An [iSDIO](https://www.sdcard.org/developers/sd-standard-overview/sdio-isdio/wireless-lan-sd/) capable **wifi-SDcard** makes the whole thing possible. By using the onboard wifi module it is able to dial into an existing wifi network or even setup its own network. This feature allows us to access the data which is saved on the SD card. Since the raspberry, SDcard and our iPad are in the same network, we can connect the iPad via VNC to raspberry and have full control about the application. In final step the raspberry will start the QTapplication in booth mode. This will give a more integrated impression of our booth.

Basically the program is perfoming following steps to be able to present images:

1. Find most recent folder on SDcard 
2. Find most recent picture on SDcard
3. Fetch the newest picture and show it on pic1 place
4. Execute steps 1-2 and check with image which was downloaded at step 3
5. If they are not equal anymore there is a new picture available perform step 3 

Here are more datails on downloading the images and presenting them:

![both_download](/assets/img/booth_download.svg)

