# Mu-boo Cub Mug 
(Working Project Title - Fun cute spin alluding to work with LattePanda Mu)

Minimalist USB 4/Thunderbolt, WiFi 6/BT, Battery-powered carrier expansion for the LattePanda Mu compute module.

## Purpose
The goal of this project is to design a highly portable, remote access/streaming x86 ~~computer~~ "server" that fits in your pocket. A x86 device for moderate-weight workloads when suitable ARM-based alternatives are lacking. Examples include but not limited to; Gaming, Emulation, Engineering applications such as CAD and CAM, Portable Software Development Environment for running some IDEs, Cybersecurity tools/distros (although Kali has some good ARM stuff), Scientific Research and Enginnering Field Data Analysis, and more....

With the increasing popularity of MR headsets like the Apple Vision Pro, or Oculus Quest, last but not least larger phones/tablets, access to a display and some input method are unending. Yet, these headsets and android/iOS devices, leave some applications inaccessible due to their dependence on x86 CPU architecture. This includes a catalog of older software, like gaming titles, emulation and custom client software, that may take years or never get optimizated to emulate on ARM, god willing run natively. 

The Mu-boo Cub Mug aims to provide access to these applications/software without the need for additional screens or redundant hardware. Minimalism, and (hopefully) sleek will be key. Less ports, generally means less chips, which means less power draw, size, weight and complexity. The design intent is for the device to operate without physical connections for a minimum of two hours, allowing users to access these applications and the raw power of x86, through remote access/streaming, via a Smartphone or VR/MR/AR headset, including emerging glasses displays.

The target formfactor will be the size of a large external USB battery pack, featuring the moderately powerful x86 Intel N100 CPU, WiFi6, a few buttons for power on/off, performance mode selection, WiFi on/off, and two USB-C ports (one for device connectivity and one for power). Additional ports and connectivity can be managed through inexpensive and user-friendly USB hubs, or Bluetooth connectivity. The device will be USB4 compliant, supporting eGPUs and other Thunderbolt devices.

It's possible the device could also function simultaneously as a portable router via something like proxmox with a open-source router guest and another desktop enviroment guest

## Conception and why the LattePanda Mu. 
In todays world there are screens aplenty. I see them everywhere, paper/posters/whiteboards have been replaced by displays. Not to mention our homes, but many work places, even schools, have an external monitor (or two), for their workforces/students to use with laptops. Board/meeting rooms have big screen TVs or projectors, and there is a fairly good screen in almost everyones pocket. So, why do i need to carry another screen for when i just need the familar desktop enviroment of windows/linux/MacOS. iOS and android alternatives apps just aren't the same, and while the world tires to push to find the perfect finger friendly work space, Windows, MacOS and Linux still hold a strong foothold when it comes to getting most stuff done.

This concept begins for me in late 2022 when I got a Oculus Quest 2, and be it gaming in VR, or thanks to Virtual Desktop, PCVR and flatscreen, my Quest Headset had replaced my monitor for all gaming quickly (shout out to VorpX too for being able to convert flatscreen games to stereo 3D). Yes, the Quest 2 is not the best quality, or fastest refresh rate (fingers cross Quest 4 = HDR) compared to the latest and greastest gaming monitors. But, with Virtual Desktop being wireless only, I had a setup so i can game in [insert] room, chair, bed, and even began experimenting, "if the moons align", on the go. (In all fairness, using something like Moonlight for many years). Unfortunately, due to a few reasons, it hadn't occur to me to work via my VR headset till over a year later, using something like Immersed, or now Virtual Desktop, which recently added 2(+*) display capability.

Come last year, I switched to Samsung Fold (from iPhone), and started using Samsung DeX (amazing function) for almost half my work, especially, as i have had to be a more remote this year. Also, due to having to be more remote, and my experiementing with streaming Quest 2 outside the house, i started using Moonlight Streaming for gaming in places where Quest 2 wouldn't work, aka Transit. Unfortunately/fortunately, two things happened on a single day, which birthed the need for the a device like the Mu-boo Cub Mug (it's a redicious name... but that's why its stuck so far). 1st, it was going to be a fully packed day 14 hour day out, and it began with me trying to get some Star Wars Jedi: Suvivor in. But the Celluar Networks we're having it. Then several hours later, i was an a enviroment where there was lots of activity, and i need to get some work done while i was waiting, but having a hard time focusing with the commotion. It got me thinking, i wish i had my Oculus to just Remote into my home office and focus on massive 2 virtual monitors. But i remembered the terrible network conditions from eariler in the day. I hate carrying more then i need, i've done it too many times, and i started to think, there has got to be a very time Windows PC i can easily carry in my pocket. like a phone, i donb't even need a keyyboard or monitor. I got my smartphone and i'll just carry the VR headset around. Spent an hour that day searching for this device, and nothing. But planted the idea of a smaller more portable solution to my desktop rig or even a gaming laptop. Over the next 2 months i did start to use my Quest more and more remotely for work, but there was hickups. A PC freeze, random reboot without VR desktop loading (suspect brown out), my home network crashed once, family has low end internet, and/or on many occasions of network sliggishness. One month, i ran out of data on my plan. Generally, if i lower to 900p on Moonlight, it will run smoothly. That's fine for games, where it's designed to be seen at varing distances based on screen size. Monitor, are generally 2 feet-ish. But in VR, where i'll usually do work, the screen is cm's from your eyes, if it's not 1080p it aweful, and thats for only one monitor! Higher resolution means high chance of "hiccups". If i had my PC/Server with me, in my pocket, all these "hicups" would be easily addressed or not at all.

At this point, i have this desire for a new mini-pc, but i really want it portable, and USB-PD powered (I mean most of them don't run near 100W and we've had 240W official since 2022). Finally, last month, it smacked me in the face. I was helping setup AV team at a confrence, and I actually saw a bunch of ppl using handhald PCs like the Asus Ally and Steamdeck. IMO, i (almost*) have one, thats a better system, i just need to remote access.... and that's where my problems blew up. There were hours of downtime during the confrence, and in the hotel, i had next to no cell signal. Even if i could access the WiFi, which is another scare in itself, bandwidth would be set to bareminimal, yet alone reduced with the swoths of ppl. Why couldn't my beautiful folding phone be my "steamdeck"... it could if only.... and that's where the Lattepanda Mu comes in. During the confrence, i was so annoyed, so I had hoped i missed a product, or something new was announced. That's when i caught the Mu, and because of the card size module nature of it, i was like, with this i can easil prototpe my idea. I don't have to worry the majorityy of complex PSB issues with a modern x86 processor. The infor and coumentation is open, and the ppl at LattePanda seem to want to help bring my idea to life with being open to discuss possible BIOS needs. And due to the smaller then a credit card size, i can design to how i want it. I don't want a 5kg weight in my pocket, but it don't need to be an Apple feather, either. Also, i can add the USB power method i want. Additionally, build and maybe with the community make a unique project, many people can enjoy. 

While this is an idea i had. I think would like to open this project to anyone whom is interest, and potentially contribute their time, effort or wish for the compleition so they can use the files to build their own.

**__*****Everything Below this point is still preliminary, and subject to modification and changes*****__**

## Priorities, Choices and Challenges
#### Priority 1: Battery 
* Based on Mu web info, TDP is between 6W to 35W. Let's preliminarily plan out 3 power modes, 6W, 18W, 35W.
> testing to verify this will be needed, as review of N100 mini-pc showed idle of 9W and workload of 22W.
* Aim is for the approx. 2.5 hours of use @ 22W = 55Wh.  4 x Standard 18650 Li-Ion cells to start, aim for 3Ah per cell.
  > > Investigate 21700 cell cost compared to 18650
> * Fully Charged (4.2V per cell): 4V2 × 4 = 16V8
> * Nominal Voltage (3.7V per cell): 3V7 × 4 = 14V8
> * End-of-Discharge (3.0V per cell): 3V0 × 4 = 12V
> * Current = Power/Voltage = 22W/14.8 = 1.49A
> * Duration = Capcity/Current = 3A/1.49A = 2.01 Hours
* The desire is for the battery life to be passed through to the OS, so the user can see the remaining battery when using Remote Access/Streaming. As of current, I'm not sure if the battery management IC to pass this information to BIOS, which is then accessible to windows, or directl accessible to windows via I2C. If the Former, i'm hoping LattePanda can work with me to develop this capacity within the bios. 

#### Prioirty 2: Size
* Mu: 69.6 x 60mm (Credit Card: 54 x 85.6mm)
* 18650 cell, D18mm x L65mm, 21700 cell, D21mm x L70mm
* Preliminary:  4 x 21mm battery width (single row, side-by-side, all 4 cells) + 2 x 1mm enclosure wall thickness + 2 x 1mm wiggle = 88mm wide. 

#### Challenge: Possible Requests and Discussions with LattePanda BIOS Team
1) In order for OS to have battery info/status, does it need to be passed through BIOS, and can they provide bios with that capabiltiy. 
2) Request for binding HSIO0-3, as a PCIe3.0 x4, as well as HSIO8-11 for two seperate PCIe3.0 x4 connections. additionally, having HSIO6 for PCIe3.0 x1.
3) Undervolting and power modes

#### Challenge: High speed traces

#### Challenge: implementation of remote access/streaming.
I'm currently aware of two method to establish a wireless connection Mu-boo Cub Mug, and another device. 
* connecting to a external router, and 3rd device, which is counter to the project purpose.
* connecting to the WiFi card on the Mu-boo Cub Mug. which has its own obstacles and issues.
The two route for the later would:
1) using windows network config to share a connection, typically this would be done through windows setting and creating a bridge between ethernet port and wireless adapter. However, there will not be an ethernet adapter, and thus the wireless adapter would need to be set to ad-hoc to turn it into an access point. It is well documented that the reliability of both those ways is not great. As well as Intel adapters being terrible for ad-hoc mode. Additionally, B-Link has/had a usb wireless adapter specifically designed to connect with the Quest via WiFi, but this adapter was problematic with Virtual Desktop users. In fact, the minimum requirements are for a PC/Laptop to be connected to a router via a physical wired connection.
2) but since, your still connecting wirelessly to a router, that where the second route would come in. Using the virtualization capability of the N100 chip, with something like Proxmox to run two guess OS, one an Open Source router like OpenSNS and Windows.

Unfortunately, a small hiccup would be if you connect a quest wireless to the Mu-boo Cub Mug, neither would have a connection to the internet. I suspect this could be accomplished in windows, but know it can be done in an open-source router where you bridge the wifi to another wifi device. ideally, you'll want to connect the 2.4Ghz band the internet, leaving the 5GHz or 6GHz band dedicated to only your streaming devices. 

This is where another potential issue crops up. limited resources of core and ram. you basically have 3 OS (proxmox, openSNS and windows) running similtaneously. Ideally, I would like to investigate and try to solve these issues and "hiccups" on Windows, without having to use virtualization. but this would likely take more time, and I would assign it as a V1.1 task. 

#### Choice: Reason I choose USB 4 over OCuLink, considering gaming is a pillar of need. (This maybe more to reassure myself).
Without a doubt, as showing in multiple reviews and analysis (i'll link any i find below), OCuLink wins in the eGPU department. BUT... this is not soley developed around gaming/eGPU. The top goals of the project is around portability, not absolute, but reasonable, in terms of size, weight, duration. Let's see a side by side feature comparison.
"Paper" Feature | USB 4 | OCuLink-2
--- | --- | ---
Standardization Body |	USB-IF (USB Implementers Forum)	| PCI-SIG (PCI Special Interest Group)
**Primary Use Case**	| "Universal connectivity (data, video, power)" i.e. consumers |	Internal storage and enterprise connections
Max Data Transfer Rate (don't forget this doesn't take into account protocol overhead, which is the real killer) |	Up to 5GB/s (40Gbps, limited to 4GB/s)	| Up to 16GB/s (i.e. PCIe 4.0 x8 lanes max, but we're limited to 4GB/s PCIe3.0)
**Protocol Support**	| USB, PCIe, DisplayPort	| PCIe (x1, x2, x4, x8 lanes) 
Backward Compatibility |	USB 3.2, USB 2.0, Thunderbolt 3	| PCIe (PCIe 3.0 and 4.0 backward compatibility)
**Power Delivery** |	Up to 100W (USB Power Delivery)	| No direct power delivery
**Connector Type**	| USB Type-C |	OCuLink-specific connectors
**Hot Plugging** | Yes | No (well, apparently yes, but need specialized controllers)
Latency |	Low, optimized for peripheral connections |	Very low, optimized for high-speed storage interfaces
Cable Length | Shouldn't be connecting either with longer then 1 meter cable. Longer the cable the more error and performance hit you'd take.

Other factors to consider are where will System bottleneck(s) be? The N100 is an e-core only chip, and on average, it's CPU tests are around 1/2 performance of other CPU of the same year/generation. Frame per second (FPS) is typically CPU dependent (and the link speed between it with GPU), whereas resolution is more GPU dependent. Not to mention the limit of 8GB of RAM. Unfortunately, the USB protocol will also introduce overhead into the system, further limiting FPS, So you might say, "Well Reaver, all the more reaosn to use OCuLink". In the table above, i've bold the aspects, indicating where USB 4 stands out. USB is ubiquitous, backwards compatible, tested/tried/rugged (components, hardware, software), and it's capable of not only data transfer/Tunnelling PCIe, but video output (wish input/capture was standardized), as well as bi-directional power delivery....  "One port to rule them all". Given that due to the N100 design we're max bandwidth wouldnt see an increase, USB onl limited b overhead, and the USB-C connector is smaller, and due to it's ubiqutiousness, there are more options avaialble, like right angle. So, with the exisiting lower performace and potential other bottlenecks, this project is NOT intended or expected to play anything new well, or do anything super mission critical. From a gaming perspective, if anything, it's meant as a compromise and reason to play some of the old catelogue of games you have that you haven't gotten to. Another aspect I think will get complicated is a lack of Hot Plugging. 

Ideally, I would incorpoate both USB4 and OCuLink. Hell, i even thought of using a PCIe switch of various types. 

[One XPlayer X1 w/ OneXGPU](https://www.xda-developers.com/oculink-egpu-hands-on/)

[N100 performance referrence, No eGPU](https://www.notebookcheck.net/Intel-N100-performance-debut-Beelink-Mini-S12-Pro-mini-PC-review.758950.0.html)

[LattePanda Mu review](https://www.cnx-software.com/2024/06/10/lattepanda-mu-review-intel-n100-compute-module-windows-11-carrier-boards-pcie-slots/)

Note: Another factor that could affect performance, in addition to protocol overhead, is error correction techniques, which might be more effective for PCIe, especially at these bit rates. But that's another topic for another investigation.


## Hardware / Spec
#### Mechanical
* SO-DIMM socket
* Screw stand-offs + screws
* USB-C connectors
#### Pinout
If PCB layout allows I would like to have have GPIOs, UART and an unused I2C bus accessible via removable compartment on the enclosure.
#### LEDs
* Power on
#### Buttons
* Power tact switch
* 3 stage slider to adjust performance mode.
#### Ports
* 2x USB-C, both will be charging capable. 
> This is the current plan. Since there are many USB-A devicces out there, I am/have considered adding one USB2.0 Type-A port, if PCB and phsysical space will allow. 
#### Storage
* M.2 2230 NVMe SSD via HSIO2/3 (PCIe 3.0 x1, 1.97 GB/s, half the USB4 transfer rate as limited by the system )
> * Ideally PCIe x4 (HSIO0-3)
> > * Hoping either PCIe BIOS (coming soon), or can discuss with Lattepanda BIOS team, if HSIO0/1 can be grouped with HSIO2/3 to form a PCIe 3.0x4 port. (Since all the lanes belong to the same controller, i'm hopeful.)
> > * If stuck with only a PCIe x2 port, an NVMe will still 4 times faster then SATA3 SSD, even if it's limited to it's full speed. 
#### Connectivity
* USB 4 Controller Intel JHL8540 Maple Ridge via HSIO 8-11 (PCIe 3.0 x4)
> * ASM4242 is an alternative, but doesn't seem avaiable
> * fall-back OCuLink
* M.2 E Key 2230 WLAN network card via HSIO6 (PCIe 3.0 x1, 0.985 GB/s)
> * Intel® Wi-Fi 6E AX210
> > * There is a history of issues with Virtual Desktop when using windows and Intel WiFi cards in AP mode. May need to use Broadcomm chipset.
> * having WiFi module soldered directly onto board would be better for space saving, but adds more complication to design. Would consider in a final build. 
> * Investigate if can use TCP (Technology Computer Port)
#### Main Battery (Based on N100 mini-pc review 22W while running The Witcher 3)
* 4 x Standard 18650 Li-Ion cells, range for 2Ah to 3.5Ah. 
> * If 4x Li-po (nominal 14V4), at approx 22W x 2.5Hours = 55Wh. Avg V = ( peak + discharged )/2 = ( 16V8 + 12V )/2 = 14V4. mAh = ( Energy (Wh) x 1000 )/ nominal V = 3819mAh. Add 1.2 efficeny losses, relaiabity and battery longetivity = 3819mAh * 1.2 = approx 4500mAh.
- Battery Management IC, TBD, based on communication with community and possible LattePanda
#### Power
* USB-PD IC
* Buck converter. Aim for as self contained as possible, perhaps a module for V1. (Specially choose 14V8 nomial battery as to avoid using Boost, which are less efficent.) 
#### RTC
* battery socket (CR1220 3V)
#### protection
* Reverse Current and surge/over voltage protection

## Stages
1) Research and discuss with LattePanda Team passing battery status to OS Level.
2) Getting Reference Manual from Intel
3) use included carrier board to get familar with BIOS and do some baseline performance testing.
> Installing Windows natively
> > Benchs i can use to compare with other results online using N100
> Intalling Windows via proxmox
> > Installing open-source router
> > Benching windows to compare with native
3) Using carrier to prototype battery pack.
4) PCB Design 
Enclosure designing

## Timeline


## Varients
* V2 = Higher mAh battery, (20,000 mAH target). Maybe add camera (play around with Hello Windows) and/or LiDRa, or something to take advantage of those likely 5 unused USB 2.0 ports. (I've always want to have a spectrometer in my pocket... hummm)
* V-Alpha = Add mobile dGPU, such as GeForce RTX4060 Laptop chip (35-115W) or Radeon RX 7600M (90W)
* V-Beta* = "MuTop", a PC case (akin to the smallest ITX ones) with a standard GFX card.
> * 1x PCIe3.0 x4 slot 
> * 1x M.2 2280 x4 NVMe SSD
> * 1x WiFi
> * USB-PD 240W, I suspect any GPU that has a TDP greater then 200W will be bottlenecked by N100 system. 
> **Note**: *only if by 100+ requests for it
> 
> CWWK Mini PC has something like this called the Magic PC, and claim to have an x8 slot (Intel Doc No.:759603, Sec 19.4, figure.18, would suggest this is NOT possible. According to document, their are 3 seperate PCIe Controllers, two of which have a max of 4 lanes. CWWK's website only shows customs PCBs being attacked to the port, so they could be using their own implementation).
* V-Detla = Portable Cluster

- Alt applications,Kiosk units, router

- DDI/TCP -> seems to refer to Intel TCSS, "USB-C sub-system supports USB3, DPoC (DisplayPort over Type-C) protocols. The USB-C sub-system can also be configured as native DisplayPort or HDMI interfaces"


