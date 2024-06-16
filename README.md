# Mu-boo Cub Mug 
(Working Project Title - Fun cute spin alluding to work with LattePanda Mu)

Minimalist Battery-powered and USB4 carrier board and enclosure for the LattePanda Mu compute module.

## Highlights
* Two full functioning USB 4.0 ports, for eGPU, USB Docks and port expanders, Displayport/HDMI, etc.
* Apprx 4500 to 5000 mAh built-in battery
* Charging/powered via USB-PD
* 1x M.2 M-key 2230 slot, for NVMe SSD (hopefully with x4 PCIe lanes)
* 1x M.2 E-Key 2230 slot, for WLAN
* Performance mode button

## Purpose
The goal of this project is to design a highly portable, remote access/streaming x86 ~~computer~~ "server" that fits in your pocket. A x86 device for moderate-weight workloads when suitable ARM-based alternatives are lacking. Examples include but not limited to; Gaming, Emulation, Engineering applications such as CAD and CAM, Portable Software Development Environment for running some IDEs, Cybersecurity tools/distros (although Kali has some good ARM stuff), Scientific Research and Enginnering Field Data Analysis, and more....

With the increasing popularity of MR headsets like the Apple Vision Pro, or Oculus Quest, last but not least larger phones/tablets, access to a display and some input method are unending. Yet, these headsets and android/iOS devices, leave some applications inaccessible due to their dependence on x86 CPU architecture. This includes a catalog of older software, like gaming titles, emulation and custom client software, that may take years or never get optimizated to emulate on ARM, god willing run natively. 

The Mu-boo Cub Mug aims to provide access to these applications/software without the need for additional screens or redundant hardware. Minimalism, and (hopefully) sleek will be key. Less ports, generally means less chips, which means less power draw, size, weight and complexity. The design intent is for the device to operate without physical connections for a minimum of two hours, allowing users to access these applications and the raw power of x86, through remote access/streaming, via a Smartphone or VR/MR/AR headset, including emerging glasses displays.

The target formfactor will be the size of a large external USB battery pack, featuring the moderately powerful x86 Intel N100 CPU, WiFi6, a few buttons for power on/off, performance mode selection, WiFi on/off, and two USB-C ports (one for device connectivity and one for power). Additional ports and connectivity can be managed through inexpensive and user-friendly USB hubs, or Bluetooth connectivity. The device will be USB4 compliant, supporting eGPUs and other Thunderbolt devices.

In order to access the desired function the device will also need to similtaneous function as a portable router. For V1, this will occur via running proxmox as a Host VM, with OpenWRT as a guest OS VM, and Windows 11 guest OS VM for it's Desktop Enviroment.

## Conception and why the LattePanda Mu. 
### TL;DR: skip past if you don't need/want to know my story behind the idea.
In today's world, there are screens aplenty. They are everywhere, replacing paper, posters, and whiteboards with displays. Lest our homes, but many workplaces and even schools have external monitors for use with laptops. Boardrooms are equipped with big screen TVs or projectors, not to forget everyone has a fairly good screen in their pocket. So, why do i need to carry another screen, with my laptop, when I just need the familiar desktop environment of Windows, Linux, or MacOS? iOS and Android alternatives just aren't the same, and while the world tries to create the perfect finger-friendly workspace; Windows, MacOS, and Linux still dominate for getting most tasks done.

This concept started for me in late 2022 when I got an Oculus Quest 2. Whether gaming in VR or using Virtual Desktop for PCVR and flat-screen games, my Quest headset quickly replaced my monitor for all gaming (shout out to VorpX for converting flat-screen games to stereo 3D). Yes, the Quest 2 doesn't match the latest gaming monitors in quality or refresh rate (fingers crossed for Quest 4 with HDR), but with Virtual Desktop being wireless, I could game in [choose] room, chair, or bed, and even began experimenting, "if the moons align", on the go. (In all fairness, using something like Moonlight for many years). Despite this, it didn't occur to me to work via my VR headset until over a year later, using apps like Immersed or Virtual Desktop. (the latter only recently added support for multiple displays.)

Last year, I switched to a Samsung Fold (from iPhone) and started using Samsung DeX for almost half my work, especially since I've had to be more remote this year. Due to the remote work and previously experimenting with streaming my Quest 2 outside the house, I started using Moonlight Streaming for some gaming, particularly with in transit. About 2 weeks into this, there was a particularly frustration day, with two moments, which lead to the conception of a device such as the Mu-boo Cub Mug (it's a redicious name... but that's why its stuck so far).

It was a planned, packed 14-hour day, while in a wait room or in transit, i attempted play via moonlight, Star Wars Jedi: Survivor, but the cellular networks weren't cooperating. Later, in a busy environment where I needed to focus on getting some work done, it occured to me, "if only i had my Oculus to remote into my home office and work on massive virtual monitors". However, I remembered the terrible network conditions from earlier in the day, and it also would have been a pain to carry around a laptop that day. So the thought occured, if only i had a pocket size Windows PC I could stream into. I spent some time searching but didn't come up with anything that fit; x86, moderately powerfut yet pocketable and battery powered. This planted the idea of a smaller, more portable solution that could be streamed from. Possible a laptop replacement. I don't know if it would qualify as a cyberdeck. 

Over the next two months, I used my Quest more for remote work but faced hiccups like a PC freeze, random reboot (likely due to brownout, but software not set to startup at boot), a router stall, and on many occasions of network sliggishness. I even ran out of data on my plan one month. Lowering the resolution to 900p on Moonlight usually helped, and for the screen size to held screen distance, plus how games are designed, it hard to notice. But in a work scenario using VR, if it's not 1080p its aweful, especially when the screen is centimeter from my eyes. Higher resolution means higher chance of "hiccups". A PC locally, in my pocket, all these "hicups" would be easily addressed or not at all.

At this point, i have this desire for a new ~~mini~~micro-pc, but it's got to be portable, and be USB-PD powered (It's 2024, I mean most of the mini-pc's don't run near 100W and we've had 240W official since 2022).

Finally, last month, it really got to me. While working as AV at a conference, I saw people using handheld PCs like the Asus Ally and Steamdeck. IMO, I (almost) had a better system, a high end desktop gaming Rig in my hands, more powerful then any handheld. Capable of any game @ 60+ FPS; I just needed reliable and consistant remote access. 

It weight on me so much, as there were hours of downtime during the confrence, i could be getting through my back catologe of game. In the hotel, i had next to no cell signal. And, even if i could access the WiFi (which i wouldn't expose to), likely there would be all kind of network lockdown, possible ports blocked, yet alone reduction in bandwidth due to the thousands of people attending the conference. Why couldn't my beautiful folding phone be my "steamdeck"... it could if only.... and in those moments of dispear, when i did get a cell connection, i found the Lattepanda Mu. 

It's a pretty powerful N100 x86 chip in card-sized compute module. This form-factor makes it perfect, no, the only way, for me prototype my idea, and get the minimalized design im looking for, without all the complex PCB work need for an x86 chip, including PCB RAM Traces. The small size allows for a custom design that isn't too heavy but still functional. I don't want a 5kg weight in my pocket, but it don't need to be an Apple feather, either.

This idea could become a unique project for many to enjoy. I'm open to anyone interested in contributing their time, effort, or support to complete this project so they can build their own device.

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
* The desire is for the battery life/status to be integrated into the OS, as if it was a laptop battery. This way the user can see the remaining battery when using Remote Access/Streaming, without having to pull the device out of bag/pocket.
>  * There are two options: either, Windows has a SMBus/I2C driver which can detect various BMIC (unless there is a standard i'm not aware of. OR (and what i think it more likely), the BIOS is programmed with the address of the BMIC, and maintains all communication. The OS then pulls this information from the BIOS. If this is as i suspect, the latter, then I hope i can request and discuss with the LattePanda BIOS Team adding this ability, and they can even tell me what BMIC they would prefer if any. 
> * Investigation Update, with some contraditory info:
> * 1) My initial quick search seem to indicate, an OS (such as Windows) does get the power information from BIOS through the ACPI (Advanced Configuration and Power Interface) Table. Major firmware update steps on top of address mapping: (Source ChatGPT, so i would need to verify)
> > * DSDT (Differentiated System Description Table): This table must be updated to include descriptions of the new BMIC and its associated battery. The DSDT provides the operating system with the necessary information to manage the hardware.
> > * BAT0/BAT1 Objects: These ACPI objects represent the primary and secondary batteries. They must be defined correctly to describe the battery's properties and status.
> > * Power Source Objects (ACPI Power Source Object - AC): Define the power source objects to ensure the operating system can correctly identify and switch between power sources (e.g., AC adapter and battery).
> > * Battery Status Methods (e.g., _BST, _BIF): Implement methods in the ACPI tables to provide the battery status (_BST) and battery information (_BIF) to the operating system.
> * 2) However, attempting to verify, i came across the UPS (Universal Power Supply) Hat created by the DFRobot (which i think is the same ppl at LattePanda). It is powered by 3 18650 Cells. It is said it "supports the HID-UPS protocol, which can be recognized as a battery device in the operating system. You can use system power management to implement power-saving modes and automatic shutdown functions, just like using an internal laptop battery." and the their [wiki](https://wiki.dfrobot.com/SKU_DFR0682_LattePanda_Alpha_Delta_UPS_Hat) shows picutres of Windows showing batter. HURRAY!
> * now the downside is this seems to be using the arudino co-processor as the BMIC.... which i don't plan or want to incorportate for a number of reasons, size, more power draw, to name a few. but i may be able to review the source code, and see if i could implement using the same HIDPowerDevice library.
> * So this is great for Windows, but i would still prefer a more universal solution, where that information is pulled from the ACPI of the BIOS, as this would allow proxmox as well as other, plug and play.
> * 3) Additionally, and this is more of a note, but the LattePanda Alpha has a LiPo connector, and it appears to be a pretty standard pinout. BUT with only Voltage and GND, which i believe means the board likely has BMIC onboard.

#### Prioirty 2: Size
* Mu: 69.6 x 60mm (Credit Card: 54 x 85.6mm)
* 18650 cell, D18mm x L65mm, 21700 cell, D21mm x L70mm
* Preliminary:  4 x 21mm battery width (single row, side-by-side, all 4 cells) + 2 x 1mm enclosure wall thickness + 2 x 1mm wiggle = 88mm wide. 

#### Challenge: Possible Requests and Discussions with LattePanda BIOS Team
1) (Update is needed) In order for OS to have battery info/status, does it need to be passed through BIOS, and can they provide bios with that capabiltiy. 
2) Request for binding HSIO0-3, as a PCIe3.0 x4, as well as HSIO8-11 for two seperate PCIe3.0 x4 connections. additionally, having HSIO6 for PCIe3.0 x1. (This could be planned by Lattepanda with coming soon PCIe BIOS branch)
3) Discuss and request BIOS detecting, when the unit is connected to external power or running on battery, either using a GPIO or via USB-PD IC messaging.
> Additionally, and ideally have the BIOS detect when a GPIO is pulled low, to have PL1/PL2 change between two sets of value at any time. Alternatively, if that's not possible, the BIOS will set the PL1/PL2 level based on the GPIO state at boot.
> > I generally prefer the first option, but if the second option, should Lattepanda wish to give the option, could create "BIOS setting saves #1 and #2". GPIO low at boot would load setting 1, or at boot, high would load setting 2. This would give user more choice for how they want to run the Mu without needing a monitor and accessing the bios. 

#### Challenge: High speed traces
- Routing any high speed differential trace will always be a PITA, and pretty much guaranteed need a few board spins to nail the eye. 

#### Challenge: implementation of remote access/streaming.
I'm currently aware of two method to establish a wireless connection Mu-boo Cub Mug, and another device. 
* connecting to a external router, and 3rd device. which is completely counter to the project purpose.
* connecting to the WiFi card on the Mu-boo Cub Mug. which has its own obstacles and issues.
The two route for the later would:
1) (need to revise) using Windows network config to share a connection, typically this would be done through Windows setting and creating a bridge between ethernet port and wireless adapter (soft Access Point). However, there will not be an ethernet adapter, and thus the wireless adapter would need to be set to ad-hoc to turn it into an access point. It is well documented that the reliability of both those ways is not great. As well as Intel adapters being terrible for ad-hoc mode. Additionally, B-Link has/had a usb wireless adapter specifically designed to connect with the Quest via WiFi, but this adapter was problematic with Virtual Desktop users. In fact, the minimum requirements are for a PC/Laptop to be connected to a router via a physical wired connection.
2) but since, your still connecting wirelessly to a router, that where the second route would come in. Using the virtualization capability of the N100 chip, with something like Proxmox to run two guess OS, one an Open Source router like OpenWRT and Windows.

Unfortunately, a small hiccup would be if you connect a quest wireless to the Mu-boo Cub Mug, neither would have a connection to the internet. I suspect this could be accomplished in Windows, but know it can be done in an open-source router where you bridge the wifi to another wifi device. ideally, you'll want to connect the 2.4Ghz band the internet, leaving the 5GHz or 6GHz band dedicated to only your streaming devices. 

This is where another potential issue crops up. limited resources of core and ram. you basically have 3 OS (proxmox, openWRT and indows) running similtaneously. Ideally, I would like to investigate and try to solve these issues and "hiccups" on Windows, without having to use virtualization. but this would likely take more time, and I would assign it as a V1.1 task. 

#### Choice: Reason I choose USB 4 over OCuLink, considering gaming is a pillar of need. (This maybe more to reassure myself).
Without a doubt, as showing in multiple reviews and analysis (i'll link any i find below), OCuLink wins in the eGPU department. BUT... this is not soley developed around gaming/eGPU. The top goals of the project is around portability, not absolute, but reasonable, in terms of size, weight, duration.

1st factor to consider is, where will System bottleneck(s) be? The N100 is an e-core only chip, and on average, it's CPU tests are around 1/2 performance of other CPU of the same year/generation. Frame per second (FPS) is typically CPU dependent (and the link speed between it with GPU), whereas resolution is more GPU dependent. Not to mention the limit of 8GB of RAM. Next, according to the N100 public documents, the max PCIe link speed is x4 (I will reach out to Lattepanda to see if they can verify that PCIe controller 1 and PCIe controller 3 CANNOT be bonded to form a x8 slot). As shown below, on paper, this puts USB4 and OCuLink at the same badnwidth. But, and Unfortunately, the USB protocol will also introduce overhead into the system, further limiting FPS, So you might say, "Well Reaver, all the more reaosn to use OCuLink". Let's see a Side-by-side:

"Paper" Feature | USB 4 | OCuLink-2
--- | --- | ---
Standardization Body |	USB-IF (USB Implementers Forum)	| PCI-SIG (PCI Special Interest Group)
**Primary Use Case**	| "Universal connectivity (data, video, power)" i.e. consumers |	Internal storage and enterprise connections
Max Data Transfer Rate (don't forget this doesn't take into account protocol overhead, which is the real killer) |	Up to 5GB/s (40Gbps, limited to 4GB/s)	| Up to 16GB/s (i.e. PCIe 4.0 x8 lanes max, but we're limited to 4GB/s, or 31.5 Gbps, as it's PCIe3.0 x4)
**Protocol Support**	| USB, PCIe, DisplayPort	| PCIe (x1, x2, x4, x8 lanes) 
Backward Compatibility |	USB 3.2, USB 2.0, Thunderbolt 3	| PCIe (PCIe 3.0 and 4.0 backward compatibility)
**Power Delivery** |	Up to 100W (USB Power Delivery)	| No direct power delivery
**Connector Type**	| USB Type-C |	OCuLink-specific connectors
**Hot Plugging** | Yes | No (well, apparently yes, but need specialized controllers)
Latency |	Low, optimized for peripheral connections |	Very low, optimized for high-speed storage interfaces
Cable Length | Shouldn't be connecting either with longer then 1 meter cable. Longer the cable the more error and performance hit you'd take.

In the table above, I've highlighted the aspects where USB 4 particularly excels for me. USB is ubiquitous, backwards compatible, tried and tested (components, hardware, software), and capable of not only data transfer and tunneling PCIe, but also video output (though I wish input/capture was standardized) and bi-directional power delivery—truly "one port to rule them all."

Considering these aspects, the smaller and easier-to-handle USB-C connector, the availability of various options like right-angle connectors due to its ubiquity, and the N100's limited PCIe bandwidth along with other potential bottlenecks of a lower power design, USB4 was the optimal choice for this project. This project is not intended to handle new or mission-critical tasks but to serve as a practical solution. From a gaming perspective, it's meant as a compromise and a reason to play some of the older games you might have missed.

Additionally, it's worth noting that OCuLink not being hot-pluggable and requiring a second cable for power can complicate things further.

Ideally, I would incorpoate both USB4 and OCuLink. Hell, i even thought of using a PCIe switch of various types. 

[One XPlayer X1 w/ OneXGPU](https://www.xda-developers.com/oculink-egpu-hands-on/)

[N100 performance referrence, No eGPU](https://www.notebookcheck.net/Intel-N100-performance-debut-Beelink-Mini-S12-Pro-mini-PC-review.758950.0.html)

[LattePanda Mu review](https://www.cnx-software.com/2024/06/10/lattepanda-mu-review-intel-n100-compute-module-Windows-11-carrier-boards-pcie-slots/)

Note: a note that could affect performance, in addition to protocol overhead, is error correction techniques, which might be more effective for PCIe, especially at these bit rates. But that's another topic for another investigation.


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
* Power mode tact switch
#### Ports
* 2x USB-C, both will be charging capable. 
> This is the current plan. Since there are many USB-A devicces out there, I am/have considered adding one USB2.0 Type-A port, if PCB and phsysical space will allow. 
#### Storage
* M.2 2230 NVMe SSD via HSIO2/3 (PCIe 3.0 x1, 1.97 GB/s, half the USB4 transfer rate as limited by the system )
> * Ideally PCIe x4 (HSIO0-3)
> > * Hoping either PCIe BIOS (coming soon), or can discuss with Lattepanda BIOS team, if HSIO0/1 can be grouped with HSIO2/3 to form a PCIe 3.0x4 port. (Since all the lanes belong to the same controller, i'm hopeful.)
> > * If stuck with only a PCIe x2 port, an NVMe at x2 will still 4 times faster then SATA3 SSD, even if it's limited to it's full speed. 
#### Connectivity
* USB 4 Controller Intel JHL8540 Maple Ridge via HSIO 8-11 (PCIe 3.0 x4)
> * ASM4242 is an alternative, but doesn't seem avaiable
> * fall-back OCuLink
* M.2 E Key 2230 WLAN network card via HSIO6 (PCIe 3.0 x1, 0.985 GB/s)
> * Intel® Wi-Fi 6E AX210
> > * There is a history of issues with Virtual Desktop when using Windows and Intel WiFi cards in AP mode. May need to use Broadcomm chipset.
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
1) Investigate, Research, Planning
a) Research and discuss with LattePanda Team passing battery status to OS Level.
b) Getting Thunderbolt chip Reference Manual from Intel
c) finalize alpha components (look to see if i can find a damaged/broken Thunderbolt PCIe expansion card with same chip for circuit reference. Options:Gigabyte GC-TITAN RIDGE 2.0, ASRock Thunderbolt 4 AIC, ASUS ThunderboltEX 4 )
d) purchase battery related components, USB-PD IC, as well as WiFi card. 
2) use included carrier board to get familar with BIOS and do some baseline performance testing, possibly seeing stability ith undervolting.
> Installing Windows natively
> > Create some baseline data point with typical benchmarks used in reviews.  
> Setup VM host, Proxmox, and install openWRT guest OS, and install Windows Guest OS
> > Create second set of bench data points.
> > 
3) Using carrier, prototype battery pack, and get it to pass through to Windows.
4) Macro testing PCB Design v0.1, ordering.
5) 
6) Enclosure Design and printing. 

## Timeline
Stage 1 Completion June 30
Stage 2 completion July 5
Stage 3 completion July 14
Stage 4 completion Augest 11
Completion End of Sept 2024

## Varients
* V2 = Higher mAh battery, (20,000 mAH target). Maybe add camera (play around with Hello Windows) and/or LiDRa, or something to take advantage of those likely 5 unused USB 2.0 ports. (I've always want to have a spectrometer in my pocket... hummm)
* V-Alpha = Add mobile dGPU, such as GeForce RTX4060 Laptop chip (35-115W) or Radeon RX 7600M (90W)
* V-Beta = Portable Cluster
* V-Delta = a Mu-sized PC with Lattepanda Mu(s?) carrier board and configurable Case/Enclosure, designed for portable PC with Low-profile PCIe card, or carry-able Full Size PCIe card with integrarted seperate 12V power connection.
> * Note: I suspect any GPU that has a TDP greater then 200W will be bottlenecked by N100 system, but there are other reasons you may need a full size card slot.)
> 
> * #### Base Core Enclosure
> * Enclosure will consist of two parts. Base Core for low-profile GFX, which is more portable, or, Expanded yet carry-able design.
> * Possible cluster/SSI design with 2x Mu compute modules (Initial investigation from V-Beta will determine direction)
> * 1x PCIe3.0 x16 (mechanically, x4 electrically) slot. (Facilitates either low-profile, or, full-size card via Expanded enclosure)
> * 1x USB4 Host Controller (Preliminarily Intel JHL8540, ideally ASM4242m which has more DFP)
>> * Update: Further investigation on this has revealed I can't seem to find a source of the 3 available possible IC (VL830, ASM4242, RTS5930).
>> * -> USB4.0 to PCIe bridge chip, for M.2 M Key 2280 (Perhaps JHL8440)
>> * -> USB4 port, both PD and video out (two different locations on enclosure, for different orientations)
>>> * Reasoning: USB4.0 improved resource allocation capability. In addition to same reasons as for Mu-boo original, and allows for greater flexility of other projects. Ex. a project needs an additional PCIe slot (like AI co-processor), ethernet port, two screens and two USB 3.0 ports. ONLY USB 4.0 can get anywhere near accomedating that.  
> * 1x M.2 E Key for WiFi (x1 electrically)
>> *  For reference: WiFi 6 paper max bandwidth is 9.6 Gbps, but practical is 1-2Gbps. WiFI 7 is paper bandwidth 46 Gbps, 5-10Gbps Practical. This is likely based on # of links aswell.)
> * USB-PD 240W (Gigabyte 0RTX460 Low-profile is TDP 115W) 
> * The Physical design will be unique, not your typical retangular design. Emphasis will be aiming for portablity, but will try to include:
>> * 1x USB2.0 Type-A
>> * 1x USB2.0 Type-C
>> * 1x HDMI output
>> * 
> * Challenges: The challenge in the design will be to figure out a way to limit the power usage, particularly of the GFX so that a reason size battery can use used. Simply cutting off power at the PCIe 12V Aux wouldn't benefit as, PCIe standard allows for up to 75W and I'm not sure if cards are designed to limit current through slot. Ideally we'd want to limit it to 35W in battery mode. Aim for total draw of 55W. The alternative would be to not provide power to PCIe 12V in battery mode, but this would be like hot plugging PCIe. 
> 
>  * #### Expanded Enclosure
>  * Larger Enclosure frame to allow for full-size PCIe Card.
>  * Quick removal for taking your the more portable Base Core on the go.
>  * Additional integrated USB-PD 240W power connection.( there is the possibly for a more typical external brick, for higher wattage)
>    
> CWWK Mini PC has something like this called the Magic PC, and claim to have an x8 slot (Intel Doc No.:759603, Sec 19.4, figure.18, would suggest this is NOT possible. According to document, their are 3 seperate PCIe Controllers, two of which have a max of 4 lanes. CWWK's website only shows customs PCBs being attacked to the port, so they could be using their own implementation).
>
> [Low-profile RTX4060 Power Draw](https://www.thefpsreview.com/2023/12/13/gigabyte-geforce-rtx-4060-oc-low-profile-8g-video-card-review/6/)

#### Roadmap 
Update 14-06-24: Post Mu-boo V1.
* Doing some preliminary mechanical layout and concept ~~sketches~~ doodles, I came up with a design concept, V-Delta varient. It's not pocketable, but i believe has a lot of potential for many, and i'm really excitd about. As it's not pocketable, the design might allow more volume in the enclosure. This leads me to wonder if a expandable cluster design would improve performance. Thus, i will do some initial investigation into this, possibly doing the V-Beta post. 
