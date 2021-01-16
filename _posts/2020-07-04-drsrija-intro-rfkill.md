---
title: "My Introduction to Wi-Fi 'Hard block' and 'rfkill'"
date: 2020-07-04T15:34:30 +05:30
categories:
  - tech
  - networking
tags:
  - Wi-Fi Hard Block
  - rfkill
Author:
  - Dr Srija Katta
---

  While I was adjusting the brightness of my laptop (Dell-Vostro-14,3000 Series with Ubuntu) my internet suddenly got disconnected.  I checked router and Wi-Fi connection, they were perfectly fine,  I noticed Wi-Fi symbol disappeared from the drop-down menu, even the settings showed no options to turn it 'on'  and the notification said '**No Wi-Fi Adapter Found**' as shown in the screen shot below : 



![pic 1](https://user-images.githubusercontent.com/42797168/86515763-07b5f500-be39-11ea-8de8-df6503c4a7f6.png)

Surmising an issue in the Wi-Fi driver, I removed the exisiting Wi-Fi packages using  ```apt```  &  ```purge``` tools and then re-installed them, but couldn't find any change!!

I then checked the list of pci buses on my system using ```lspci``` command and  realised  “Network Bus" was missing. 

With my collegue’s intervention I came across ```rfkill```tool..

```rfkill``` - is a tool that gives an interface to know the status, activate and deactivate the radio transmittors in a computer.
It is mainly associated with wireless tramsittors in the system like 'Wi-Fi' , 'Bluetooth' and Mobile Broadband Devices[ref1][ref2]

When these devices are deactivated they fall into **'soft block'** ( a state in which the device can be re-activated using software) **or**  **'hard block'** ( a state in which the device cannot be re-activated using a software )[ref1]

Using the command ```rfkill list```  I found that the wireless LAN was **hard blocked** and as understood hard block cannot be unblocked using software...

As mentioned in the beginning of my writeup,  I remembered I was adjusting the brightness using keyboard buttons (Function +F12) supposing this action might have blocked Wi-FI I tried it again but no luck...

Then I tried '**Function(Fn)+ Prtscr**' ( ‘PrtScr’ has a transmittor symbol on it)  and finally it worked!!!

 Looking back at my initial action I might accidentally stroked ‘PrtScr’ key (which is right beside F12) while holding 'Function (Fn)' key

It is important to be vigilant of the actions and keyboard strokes you give while using the keyboard otherwise we may end up triggering changes in hardware setup!!!!


Disclaimer : The Information provided above shoukd notbe used for any lifesaving or critical purposes, no claim to accuracy or fitness and this article dosenot form a product commitment. No Warranties or liablities apply to the author



Author : Dr Srija Katta



[ref1]: https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/6/html/power_management_guide/rfkill

[ref2]: https://linux.die.net/man/1/rfkill 

