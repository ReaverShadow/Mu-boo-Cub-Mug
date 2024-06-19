# Mu-boo Cub Mug 
(Working Project Title - Fun cute spin alluding to work with LattePanda Mu)

Minimalist Battery-powered and ~~USB4~~ OCuLink carrier board and enclosure for the LattePanda Mu compute module.

See the [Wiki](https://github.com/ReaverShadow/Mu-boo-Cub-Mug/wiki) for indepth view of the project, including hardware spec, planning, estimated timeline, and long-term roadmap. 

## Highlights
* ~~Two full functioning USB 4.0 ports, for eGPU, USB Docks and port expanders, Displayport/HDMI, etc.~~
* **It's looking like, at the current time, adding USB4 might not be possible unless your a large scale company. Investigating still but could likely fall-back to OCuLink. If this is turely the case, i will design an expansion that will latch/slide/or otherwise lock-on to Mu-boo, with a OCuLink to PCIe slot which will fit a low-profile card**
* Two USB 3.2 Gen 2x1 ports with Alt. Mode Display Port Output
* Approx. 4500 to 5000 mAh built-in battery
* Charging/powered via USB-PD
* 1x M.2 M-key 2230 slot, for NVMe SSD (hopefully with x4 PCIe lanes)
* 1x M.2 E-Key 2230 slot, for WLAN
* Performance mode button
* I2C pinout via removable window
* UART pinout via removable window

## Purpose
The goal of this project is to design a highly portable, remote access/streaming x86 ~~computer~~ "server" that fits in your pocket. A x86 device for moderate-weight workloads when suitable ARM-based alternatives are lacking. Examples include but not limited to; Gaming, Emulation, Engineering applications such as CAD and CAM, Portable Software Development Environment for running some IDEs, Cybersecurity tools/distros (although Kali has some good ARM stuff), Scientific Research and Enginnering Field Data Analysis, and more....

With the increasing popularity of MR headsets like the Apple Vision Pro, or Oculus Quest, last but not least larger phones/tablets, access to a display and some input method are unending. Yet, these headsets and android/iOS devices, leave some applications inaccessible due to their dependence on x86 CPU architecture. This includes a catalog of older software, like gaming titles, emulation and custom client software, that may take years or never get optimizated to emulate on ARM, god willing run natively. 

The Mu-boo Cub Mug aims to provide access to these applications/software without the need for additional screens or redundant hardware. Minimalism, and (hopefully) sleek will be key. Less ports, generally means less chips, which means less power draw, size, weight and complexity. The design intent is for the device to operate without physical connections for a minimum of two hours, allowing users to access these applications and the raw power of x86, through remote access/streaming, via a Smartphone or VR/MR/AR headset, including emerging glasses displays.

The target formfactor will be the size of a large external USB battery pack, featuring the moderately powerful x86 Intel N100 CPU, WiFi6, a few buttons for power on/off, performance mode selection, WiFi on/off, and two USB-C ports (one for device connectivity and one for power). Additional ports and connectivity can be managed through inexpensive and user-friendly USB hubs, or Bluetooth connectivity. The device will be USB4 compliant, supporting eGPUs and other Thunderbolt devices.

In order to access the desired function the device will also need to similtaneous function as a portable router. For V1, this will occur via running proxmox as a Host VM, with OpenWRT as a guest OS VM, and Windows 11 guest OS VM for it's Desktop Enviroment.

