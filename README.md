# Mu-boo Cub Mug 
(Working Project Title - Fun cute spin alluding to work with LattePanda Mu)

Minimalist USB 4/Thunderbolt, WiFi 6/BT, Battery-powered carrier expansion for the LattePanda Mu compute module.

## Purpose
The goal of this project is to design a highly portable, remote access/streaming x86 computer that fits in your pocket. A x86 computer for certain moderate-weight workloads lacking suitable ARM-based alternatives. Examples include but not limited to; Gaming, Emulation, Engineering applications such as CAD and CAM, Portable Software Development Environment for running some IDEs, Cybersecurity tools/distros (although Kali has some good ARM stuff), Scientific Research and Enginnering Field Data Analysis, and more....

With the increasing popularity of MR headsets like the Apple Vision Pro, Oculus Quest, last but not least larger phones/tablets, access to a display and some input method are unending. Yet, these headsets and android/iOS devices, leave some applications inaccessible due to their dependence on x86 CPU architecture. This includes a catalog of older software, like gaming titles, emulation and custom client software, that may take years or never get optimizated to emulate on ARM, god willing run natively. 

The Mu-boo Cub Mug aims to provide access to these applications/software without the need for additional screens or redundant hardware. Minimalism, and hopefully sleek, will be key. Less ports, generally means less chips, which means less power draw, size, weight and complexit. The design intent is for the device to operate without physical connections for a minimum of two hours, allowing users to access these applications and the raw power of x86, through remote access/streaming, using a Smartphone or VR/MR/AR headset, including emerging glasses displays.

The target form factor will be the size of a large external USB battery pack, featuring a moderately powerful x86 Intel N100 CPU, WiFi, a few buttons (power, performance mode, WiFi), and two USB-C ports (one for device connectivity and one for power). Additional ports and connectivity can be managed through inexpensive and user-friendly USB hubs, or Bluetooth connectivity. The device will be USB4 compliant, supporting eGPUs and other Thunderbolt devices.

## Conception
In todays world there are screens aplenty. I see them everywhere, paper/posters/whiteboards have been replaced by displays. Not to mention our homes, but many work places, even schools, have an external monitor (or two), for their workforces/students to use with laptops. Board/meeting rooms have big screen TVs or projectors, and there is a fairly good screen in almost everyones pocket. So, why do i need to carry another screen for windows/linux/MacOS, iOS and android alternatives just aren't the same, and sometimes i just want that desktop enviroment.

This concept begins for me in late 2022 when I got a Oculus Quest 2, and be it gaming in VR, or thanks to Virtual Desktop, PCVR and  flatscreen, my Quest Headset had replaced my monitor for all gaming (shout out to VorpX too for being able to convert flatscreen games to stereo 3D). Yes, it's not the best quality, or fastest (fingers cross Quest 4 = HDR), but with Virtual Desktop being wireless only, I had a setup so i can game in [insert] room, chair, bed, and even began experimenting, "if the moons align", on the go. (In all fairness, using something like Moonlight for many years). Unfortunatel, due to a few reasons, it hadn't occur to me to work via my VR headset till over a year later, using something like Immersed, or now Virtual Desktop, which recently added 2+ display capability.

Come last year,  I switched to Samsung Fold (from iPhone), and started using Samsung DeX (amazing function) for almost half my work, especially, as i have had to be a more remote this year. This is how apple's ecosstem continuity must feel, not having a Macbook. It was great early on when I was in a rush and couldn't bring much with me. But, when i started to prepare and bring my laptop, it felt like it was weighting me down, espeically as i wasn't needing it constantly. but when i didn't bring it, i needed it. One night back at home after playing diablo IV, that thought about streaming my Desktop to my VR for work came back to mind, and i also started playing with moonlight and other remote desktop apps. It was so fluid and great at times, when i had cell signal, not to mention data plan to boot, or family with Ggigbit internet. But half the time, cell singal was consistent, and hotel/public wifi isn't going to provide high bandwidth, even forgetting ifi security. 

So the spark of the idea came to light, but rather then having to put it together, i figured with all the Mixed Reality headset coming out developer or company must have come up with the concept..... well 3 months later, and here we are. 

## Priorities, Choices and Challenges
#### Priority 1: Battery 
* Based on Mu web info, TDP is between 6W to 35W. Let's preliminarily plan out 3 power modes, 6W, 18W, 35W.
> * testing to verify this will be needed, as review of N100 mini-pc showed idle of 9W and workload of 22W.
* I'll aim for the approx. 2.5 hours of use @ 22W = 55Wh. We'll use 4 x Standard 18650 Li-Ion cells to start, each with a nominal charge of 3.7V. (more power calculation to come)
* My desire is for the battery life to be passed through to the OS, so the user can see the remaining battery when using Remote Access/Streaming. As of current, I'm not sure if the battery management IC to pass this information to BIOS, which is then accessible to windows, or directl accessible to windows via I2C. If the Former, i'm hoping LattePanda can work with me to develop this capacity within the bios. 

#### Prioirty 1: Size

#### Challenge: Possible Requests and Discussions with LattePanda BIOS Team
* undervolting and power modes
#### Challenge: High speed traces
- 
#### Choice: Reason I choose USB 4 over OCuLink, considering gaming is a pillar of need. (This maybe more to reassure myself).
Without a doubt, as showing in multiple reviews and analysis (i'll link any i find below), OCuLink wins in the eGPU department. BUT... this is not soley developed around gaming/eGPU. The top goals of the project is around portability, not absolute, but reasonable, in terms of size, weight, duration. Let's see a side by side feature comparison.
"Paper" Feature | USB 4 | OCuLink-2
--- | --- | ---
Standardization Body |	USB-IF (USB Implementers Forum)	| PCI-SIG (PCI Special Interest Group)
**Primary Use Case**	| "Universal connectivity (data, video, power)" i.e. consumers |	Internal storage and enterprise connections
Max Data Transfer Rate (don't forget this doesn't take into account protocol overhead, which is the real killer) |	Up to 5GB/s (40Gbps)	| Up to 16GB/s (i.e. PCIe 4.0 x8 lanes max, 1x 3.0 lane = 0.985 GB/s, 128b/130b encoding)
**Protocol Support**	| USB, PCIe, DisplayPort	| PCIe (x1, x2, x4, x8 lanes) 
Backward Compatibility |	USB 3.2, USB 2.0, Thunderbolt 3	| PCIe (PCIe 3.0 and 4.0 backward compatibility)
**Power Delivery** |	Up to 100W (USB Power Delivery)	| No direct power delivery
**Connector Type**	| USB Type-C |	OCuLink-specific connectors
**Hot Plugging** | Yes | No (well, apparently yes, but need specialized controllers)
Latency |	Low, optimized for peripheral connections |	Very low, optimized for high-speed storage interfaces
Cable Length | Shouldn't be connecting either with longer then 1 meter cable. Longer the cable the more error and performance hit you'd take.

Other factors to consider are where will System bottleneck(s) be? The N100 is an e-core only chip, and on average, it's CPU tests are around 1/2 performance of other CPU of the same year/generation. Frame per second (FPS) is typically CPU dependent (and the link speed between it with GPU), whereas resolution is more GPU dependent. Not to mention the limit of 8GB of RAM. Unfortunately, the USB protocol will also introduce overhead into the system, further limiting FPS, So you might say, "Well Reaver, all the more reaosn to use OCuLink". There are primarily two limiting factors I had to consider. Size x Space, and PCIe lanes (it's one or the other). In the table above, i've bold the aspects, indicating where USB 4 stands out. USB is ubiquitous, backwards compatible, tested/tried/rugged (components, hardware, software), and it's capable of not only data transfer/Tunnelling PCIe, but video output (wish input/capture was standardized), as well as bi-directional power delivery....  "One port to rule them all". The USB-C connector is smaller, and due to it's ubiqutiousness, there are more options avaialble, like right angle. So, with the exisiting lower performace and potential other bottlenecks, this project is NOT intended or expected to play anything new well, or do anything super mission critical. From a gaming perspective, if anything, it's meant as a compromise and reason to play some of the old catelogue of games you have that you haven't gotten to. Another aspect I think will get complicated is a lack of Hot Plugging. 

Ideally, I would incorpoate both USB4 and OCuLink. Hell, i even thought of using a PCIe switch of various types. 

[One XPlayer X1 w/ OneXGPU](https://www.xda-developers.com/oculink-egpu-hands-on/)

[N100 performance referrence, No eGPU](https://www.notebookcheck.net/Intel-N100-performance-debut-Beelink-Mini-S12-Pro-mini-PC-review.758950.0.html)

[LattePanda Mu review](https://www.cnx-software.com/2024/06/10/lattepanda-mu-review-intel-n100-compute-module-windows-11-carrier-boards-pcie-slots/)

Note: Another factor that could affect performance, in addition to protocol overhead, is error correction techniques, which might be more effective for PCIe, especially at these bit rates. But that's another topic for another investigation.


## Hardware / Spec
#### Pinout
If PCB layout allows I would like to have have GPIOs, UART and an unused I2C bus accessible via removable compartment on the enclosure.
#### LEDs
#### Buttons
#### Ports
* 2x USB-C, both will be charging capable. 
> This is the current plan. Since there are many USB-A devicces out there, I am/have considered adding one USB2.0 Type-A port, if PCB and phsysical space will allow. 
#### Storage
* M.2 2230 NVMe SSD via HSIO2 (PCIe 3.0 x1, 0.985 GB/s)
> * Ideally PCIe x4 
> * Hoping either PCIe BIOS (coming soon), or can discuss with Lattepanda BIOS team, if HSIO0/1 can be grouped with HSIO2/3, for an additional PCIe x4 
#### Connectivity
* USB 4 Controller Intel JHL8540 Maple Ridge
> * ASM4242 is an alternative, but doesn't seem avaiable
> * fall-back OCuLink
* M.2 E Key 2230 WLAN network card via HSIO6 (PCIe 3.0 x1, 0.985 GB/s)
> * Intel® Wi-Fi 6E AX210
> > * There is a history of issues with Virtual Desktop when using windows and Intel WiFi cards in AP mode. May need to use Broadcomm chipset.
> * having WiFi module soldered directly onto board would be better for space saving, but adds more complication to design. Would consider in a final build. 
> * Investigate if can use TCP (Technology Computer Port)
#### Battery (Based on N100 mini-pc review 22W while running The Witcher 3)
* 4 x Standard 18650 Li-Ion cells, range for 2Ah to 3.5Ah. 
> * If 4x Li-po (nominal 14V4), at approx 22W x 2.5Hours = 55Wh. Avg V = ( peak + discharged )/2 = ( 16V8 + 12V )/2 = 14V4. mAh = ( Energy (Wh) x 1000 )/ nominal V = 3819mAh. Add 1.2 efficeny losses, relaiabity and battery longetivity = 3819mAh * 1.2 = approx 4500mAh.
- Battery Management IC, TBD, based on communication with community and possible LattePanda

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
## Varients
* V2 = Maybe add camera (play around with Hello Windows) and/or LiDRa, or something to take advantage of those likely 5 unused USB 2.0 ports. (I've always want to have a spectrometer in my pocket... hummm)
* V-Alpha = Add mobile dGPU
* V-Beta = Portable Cluster

- Alt applications,Kiosk units, router


