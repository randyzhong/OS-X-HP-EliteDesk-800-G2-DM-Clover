# OS-X-HP-EliteDesk-800-G2-DM-Clover
This repository contains the files and scripts to install macOS on the HP EliteDesk 800 G2 Desktop Mini Business PC (35 W/65 W).

![HP EliteDesk 800 G2 Desktop Mini Business PC](https://ssl-product-images.www8-hp.com/digmedialib/prodimg/lowres/c04876268.png)

## Hardware Specs
### Basic info
Here is my EliteDesk 800 G2 DM specs:
- Product Number: L2X86AV
- Product Name: HP EliteDesk 800 G2 DM 65W
- BIOS: N21 Ver.02.21 11/01/2016

### Specs:
- CPU: Intel® Core i7-6700 @ 3.40 GHz processor (65 W model only)
- GPU: Integrated Intel® HD Graphics 530 (3 DisplayPorts)
- Memory: 1 x 8GB Micron DDR4-2400
- Storage: SAMSUNG MZ7LN256HMJP-000H1 
- LAN: Intel® I219M Gigabit Network Connection LOM
- WLAN: Intel® 8260 802.11ac 2x2 Wi-Fi with Bluetooth M.2 Combo Card Vpro (802.11ac Wave 2 supported)
- Audio: Realtec ALC221 Audio Codec (all ports are stereo, 1 internal speaker, 1 front headphone, 1 front CITA port)

## Configure BIOS Settings
To start, set BIOS to defaults.
Then insure:
- Advanced -> Boot Options
  - Disable **Fast Boot**
  - Disable **CD-ROM Boot**
  - Enable **USB Storage Boot**
  - Disable **Network (PXE) Boot**
  
- Advanced -> Secure Boot Configuration
  - Select **Legacy Support Enable and Secure Boot Disable**, press **F10** to save changes, system will reboot and lead you to Secure Boot and ask you to input a 4 digits security code for authorization, type in the code shows on the screen and enter to reboot and then press **F10** again to enter BIOS configuration

- Advanced -> System Options
  - Disable **Virtualization Technology (VTx)**
  - Disable **Virtualization Technology for Directed I/O (VTd)**
  - Enable **M.2 SSD** if you're using a NVME SSD
  - Uncheck **M.2 WLAN/BT** if you're using a Intel 8265NGW or other unsupported card
  - Check **Allow PCIe/PCI SERR# Interrupt** (Uncheck it if have interruption issues)

#### Advanced -> Built-in Device Options
- Disable **Wake on LAN**
- Set Video memory size to **64MB** or larger
- Disable **LAN/WLAN Auto Switching**
- Disable **Wake on WLAN**

#### Advanced -> Port Options
- Enable **all** if no specific reasons.

#### Advanced -> Power Management Options
- Disable **Extended Idle Power States**

Press **F10** to save changes.

## Installation
- To be updated

### Tested OS
- macOS Catalina 10.15.4

### Clover
- Clover r5108

### Kexts
- FakePCIID_XHCIMux.kext (1.3.15) 
- VirtualSMC.kext (1.1.2)
  - SMCProcessor.kext (1.1.2)
  - SMCSuperIO.kext (1.1.2)
- IntelMausi.kext (1.0.2)
- USBPorts.kext (1.0)
- SATA-unsupported (0.9.2)
- XHCI-unsupported.kext (0.9.2)
- Lilu.kext (1.4.3)
- AppleALC (1.4.8)
- WhateverGreen.kext (1.3.8)

### USB 3.0 Ports
**USB 2.0 Device**
- HS01
- HS02
- HS03
- HS04
- HS05
- HS13

**USB 3.0 Device**
- SS01
- SS02
- SS03
- SS04
- SS05
- SS08

**Type-C not tested**

## Known Issues:
- Type-C port is not tested
- Sleep is not working (Reboot or blackscreen when trying to wake it)
