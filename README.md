# Hackintosh - Intel i7 10700 Z490 Vision G
OpenCore EFI for a 100% stable Intel i7 10700 + Z490 Vision G Hackintosh

**Latest working macOS**: 10.15.6

**Current OpenCore**: 0.6.1

Complete hardware specs:
- i7 10700 OC to 5.1GHz
- Gigabyte Z490 Vision G
- WD Black 256GB
- Radeon RX 5600 XT 6 GB
- Fenvi T919
- 32GB RAM - 3000 MHz DDR4

**SMBIOS**: iMac20,2

The system dual boots Windows 10

## Get it running
0. Make sure to update your BIOS, disable VT-d, disable CSM support and enable XHCI Hand-off (for Airdrop/Continuity/Sidecar)
1. Create an macOS Catalina 10.15.x USB-Installer Stick, install OpenCore and copy my EFI folder ([how?](https://github.com/SchmockLord/Hackintosh-Intel-i7-10700-Gigabyte-Z490-Vision-D#installation-notes))
2. Generate a new serial number, motherboard id, ROM (that's your mobo's mac address without dots) and SMUUID (make sure serial number is **invalid** in order to iMessage/Facetime to work) ([how?](https://hackintosh.gitbook.io/-r-hackintosh-vanilla-desktop-guide/config.plist-per-hardware/skylake#explanation-5) + [this tool](http://mackie100projects.altervista.org/download-clover-configurator/))
3. Boot the new macOS partition

## What works
- macOS Catalina (+ Big Sur as of beta 3)
- WiFi and Bluetooth + Airdrop + Sidecar + Continuity (OOB thanks to Fenvi T919)
- Audio
- HDMI/DP (OOB thanks to 5700 XT)
- All USB ports
- 2.5Gbit Ethernet
- Everything iCloud related (Drive, iMessage, Facetime, unlock with Apple Watch, etc)
- Intel Quick Sync (if you enable IGPU in BIOS)
- Temperature monitoring for everything except GPU (no 5700xt temp support in VirtualSMC)
- DRM content (Netflix, ATV+, Airplay 2 mirroring etc)
- Shutdown/Reboot/Update to newer macOS builds over time

## What doesn't work
- Sleep? Never got the chance to test it, my hackintosh is up 24/7

![alt text](https://i.imgur.com/hn6s1Ik.jpg "neofetch")

## Kexts used:
- AppleALC (audio)
- Lilu + Whatevergreen (Audio helper, DRM support, IGPU helper)
- VirtualSMC + addons (you cannot boot without this + temperature support)
- FakePCIID (there is no real Mac running a 10700, we must fool the macOS to boot. this is how)
- FakePCIID_Intel_I225-V (ethernet)
- FakePCIID_Intel_HDMI_Audio (optional, support for audio via HDMI)
- DAGPM (better dGPU performance for 5700xt)

## Drivers used:
- OpenCanopy.efi (required by OpenCore)
- OpenRuntime.efi (required by OpenCore)
- HFSPlus (optional, make HFS drives discoverable in OpenCore bootloader if you want to use Mojave or older macOS versions)

## Thanks/Credits
- [SchmockLord](https://github.com/SchmockLord/Hackintosh-Intel-i7-10700-Gigabyte-Z490-Vision-D)
- [samuel21119](https://github.com/samuel21119/Intel-i9-10900-Gigabyte-Z490-Vision-G-Hackintosh)
- [rursache](https://github.com/rursache/Hackintosh-i9-10900k-Z490-Vision-G)
- tonymacx86
- insanelymac


**Fuck /r/Hackintosh for not allowing EFI sharing**
