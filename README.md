# Mu-boo Cub Mug (Mu cub Mug, Mu Mocha Mug)
Minimalist Thunderbold 4/USB 4, WiFi 6, Battery-powered Compute module expansion for the LattePanda Mu

## Purpose
The goal of this project is to design a highly portable, remote access/streaming x86 computer that fits in your pocket, tailored for certain moderate-weight workloads lacking suitable ARM-based alternatives.

With the increasing popularity of MR headsets like the Apple Vision Pro, Oculus Quest, and larger phones/tablets, there are still some applications that remain inaccessible due to their dependence on x86 CPU architecture. This includes a catalog of older software that may never run natively on ARM and modern applications, particularly in gaming, hardware design, and content creation, which require the raw power of x86.

The Mu-boo Cub Mug aims to provide access to these applications/software without the need for additional screens or redundant hardware. The device will operate without physical connections for approximately two hours, allowing users to remotely connect/stream to it from a phone or VR/MR/AR headset, including emerging glasses displays.

The target form factor is the size of a large external USB battery pack, featuring a moderately powerful x86 Intel N100 CPU, WiFi, a few buttons (power, performance mode, WiFi), and two USB-C ports (one for device connectivity and one for power). Less ports, generally means less chips, which means less power draw. Additional ports and connectivity can be managed through inexpensive and user-friendly USB hubs, or Bluetooth connectivity. The device will be USB4 compliant, supporting eGPUs and other Thunderbolt devices.

## Conception
In todays world there are screens aplenty. Paper has been replaced by displays, EVERYWHERE. Not to mention our homes, but many work places, even schools, have an external monitor (or two), for their workforces/students to use with laptops. Board/meeting rooms have big screen TVs or projectors, and there is a fairly good screen in almost everyones pocket. So, why do i need to carr another screen for windows/linux/MacOS, here iOS or particularly android apps haven't quite caught up yet?

In early 2023, I got a Oculus Quest, and it has replaced my monitor for gaming entirely. Be it gaming PCVR, or flatscreen via Virtual Desktop (and VorpX to convert flat to stereo 3D). Yes, it's not the best quality, or fastest (fingers cross Quest 4 = HDR), but I have it setup so i can game in [insert] room, chair, bed, and "if the moons align" on the go. (In all fairness, using something like Moonlight for many years). I had wonder about working in VR using something like Immersed, as Virtual Desktop was limited to 1 display till recently.
Then late last year, I switched to Samsung Fold (from iPhone), and started using Samsung DeX (amazing function) for almost half my work, especially, as i have had to be a more remote this year. This is how apple's ecosstem continuity must feel, not having a Macbook. It was great early on when I was in a rush and couldn't bring much with me. But, when i started to prepare and bring my laptop, it felt like it was weighting me down, espeically as i wasn't needing it constantly. but when i didn't bring it, i needed it. One night back at home after playing diablo IV, that thought about streaming my Desktop to my VR for work came back to mind, and i also started playing with moonlight and other remote desktop apps. It was so fluid and great at times, when i had cell signal, not to mention data plan to boot, or family with Ggigbit internet. But half the time, cell singal was consistent, and hotel/public wifi isn't going to provide high bandwidth, even forgetting ifi security. 

So the spark of the idea came to light, but rather then having to put it together, i figured with all the Mixed Reality headset coming out developer or company must have come up with the concept..... well 3 months later, and here we are. 

## Priorities, Choices and Challenges
#### Priority 1: Battery 
* Based on Mu web info, TDP is between 6W to 35W. Let's preliminarily plan out 3 power modes, 6W, 18W, 35W.
* I'll aim for the approx. 2.5 hours of use @ 18W = 45Wh. We'll use 4 x Standard 18650 Li-Ion cells to start, each with a nominal charge of 3.7V. (more power calculation to come)
* My desire is for the battery life to be passed through to the OS, so the user can see the remaining battery when using Remote Access/Streaming. As of current, I'm not sure if the battery management IC to pass this information to BIOS, which is then accessible to windows, or directl accessible to windows via I2C. If the Former, i'm hoping LattePanda can work with me to develop this capacity within the bios. 

#### Prioirty 1: Size

#### Challenge: Possible Requests and Discussions with LattePanda BIOS Team
- 
#### Reason I choose USB 4 over OCuLink, especially given this will be used for gaming.
Let's get this out of the way. Yes, based on multiple reviews (i'll put some links below), OCuLink wins in the eGPU department. BUT... this is not soley developed around gaming/eGPU. Remember the top goals of the project is around portability. Let's see a side by side feature comparison.
"Paper" Feature | USB 4 | OCuLink-2
--- | --- | ---
Standardization Body |	USB-IF (USB Implementers Forum)	| PCI-SIG (PCI Special Interest Group)
**Primary Use Case**	| "Universal connectivity (data, video, power)" i.e. consumers |	Internal storage and enterprise connections
Max Data Transfer Rate (don't forget this doesn't take into account protocol overhead, which is the real killer) |	Up to 5GB/s (40Gbps)	| Up to 16GB/s (i.e. PCIe 4.0 x8 lanes max) 
**Protocol Support**	| USB, PCIe, DisplayPort	| PCIe (x1, x2, x4, x8 lanes) (x1 lane 4.0 = 7.877GB/s 128b/130b encoding)
Backward Compatibility |	USB 3.2, USB 2.0, Thunderbolt 3	| PCIe (PCIe 3.0 and 4.0 backward compatibility)
**Power Delivery** |	Up to 100W (USB Power Delivery)	| No direct power delivery, depends on the specific implementation
**Connector Type**	| USB Type-C |	OCuLink-specific connectors (OCuLink-1, OCuLink-2)
**Hot Plugging** | Yes | No (well, apparently yes, but need specialized controllers)
Latency |	Low, optimized for peripheral connections |	Very low, optimized for high-speed storage interfaces

Another factor that could affect performance, in addition to protocol overhead, is error correction techniques, which might be more effective for PCIe, especially at these bit rates. But that's another topic for another investigation.

If i could, I would incorpoate both USB4 and OCuLink, but there are two limiting factors. Size/Space, and PCIe lanes. In the table, i've embolded the aspects, which really held USB 4 out. Again project keys are around portablity and size. USB is ubiquitous, backwards compatible, tested/tried (components, hardware, software), and it's capable of not only data transfer (including thunderbolt/PCIe), but video output (wish input was standardized), as well as bi-directional power delivery....  "One port to rule them all". Another aspect I think will get complicated is a lack of Hot Plugging, and then needing another cable. It's just not a simple and clean. 

[One XPlayer X1 w/ OneXGPU]https://www.xda-developers.com/oculink-egpu-hands-on/


## Hardware / Spec
Storage
- M.2 2230 NVMe SSD (PCIe 3.0 x1, 0.985 GB/s)
Connectivity
- USB 4 Controller (fall-back OCuLink)
- Intel® Wi-Fi 6E AX210 M.2 E Key 2230 WLAN network card (PCIe 3.0 x1, 0.985 GB/s)
- *Investigate if can use TCP (Technology Computer Port)
Battery
- 4 x Standard 18650 Li-Ion cells
- Battery Management IC, TBD, based on communication with community and possible LattePanda
## Challenges
- Battery needs bios
- High Speed traces
- 
## Stages
1) Research and discuss with LattePanda Team passing battery status to OS Level. 
## Varients
- Replace OCuLink with 

HSIO# | HSIO Type | RX + | RX - | TX + | TX -
--- | --- | --- | --- | --- | ---
HSIO0 | USB 3.2 10Gbps | 16 | 18 | 
HSIO1 | USB 3.2 10Gbps | 22 | 24 |
HSIO2 | PCIe 3.0 x1 | 28 | 30 | 
HSIO3 | PCIe 3.0 x1 | 34 | 36 |

HSIO8 | PCIe 3.0 x4 (Lane 0)
HSIO9 | PCIe 3.0 x4 (Lane 1)
HSIO10 | PCIe 3.0 x4 (Lane 2)
HSIO11 | PCIe 3.0 x4 (Lane 3)

HSIO6 | PCIe 3.0 x1

### DDI/TCP
- DDIB: HDMI 2.0
- TCP0: HDMI 2.0
- TCP1: USB Type-C (requires external PD controller)
- USB2_P6: Dedicated for USB Type-C, must be used in conjunction with a PD controller, cannot be used as a standard USB port.
### GPIO
- I2C2: Communication with Type-C PD controller
- GPP_B11: Type-C PD controller PMCALERT#
- GPP_B14: SATA HDD LED
- GPP_D0: WWAN_Power_Off
- GPP_D1: WWAN_Reset
GPP_D2: Communication interrupt with Type-C PD controller
