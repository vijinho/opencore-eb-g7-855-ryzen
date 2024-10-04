# HP EliteBook 855 G7 Opencore Ryzen 5 4650U Laptop

Running MacOS Ventura 13.6.7 although Sonoma 14.5 will work with occassional freezes and stutters, so better with Ventura for improved stability until the issue is resolved. Let me know if you have fixes and improvements for the internal audio and webcam to work. An SMBIOS is required for *MacbookPro 16,3* This being a 6-core processor will need modifying of kernel patches if your core count is differs.

**NOTE**: I no longer own this laptop but will accept patchess to the config, or if you improve it, I'll archive this and point to your repo.

## Hardware

- AMD Ryzen 5 4650U
- 2 x 16GB DDR4 3200
- Intel AX200NGW Wifi/Bluetooth    
- 1080P Screen (non-touch)
- WD SN520 256GB NVME (in WWAN Port)
 
## Working:

- Vega Graphics Acceleration
- Wifi & Bluetooth
- Brightness buttons
- Touchpad 
- USB ports 

## Not-working:

- In-built Speakers
- In-built Microphone
- In-built Stereo Speakers
- In-built HP Webcam
- Nipple pointer and touchpad top left/right buttons.
- Smart Card Reader (Untested)


# Kexts Used

## [Acidanthera (OpenCore Project)](https://github.com/acidanthera)

- [Lilu](https://github.com/acidanthera/Lilu) (Mandatory)
- [VirtualSMC](https://github.com/acidanthera/VirtualSMC) (Required emulate Apple SMC)
- [RestrictEvents](https://github.com/acidanthera/RestrictEvents) - block unwanted processes causing compatibility issues
- [AppleALC](https://github.com/acidanthera/AppleALC) - for in-built audio
- [NVMEFix](https://github.com/acidanthera/NVMeFix) - (optional for fixing NVME issues)

## AMD Specific

- [NootedRed](https://github.com/ChefKissInc/NootedRed) (Required for the AMD APU/iGPU) instead of WhateverGreen used on most other configs.
- [SMCRadeonSensors](https://github.com/ChefKissInc/SMCRadeonSensors) - Radeon GPU Sensors
- [AMDRyzenCPUPowerManagement](https://github.com/trulyspinach/SMCAMDProcessor) - CPU Power Management, load before:
- [SMCAMDProcessor](https://github.com/trulyspinach/SMCAMDProcessor) - System Management Controller for AMD CPU 
    
## Wireless/Networking

- [Intel Bluetooth IntelBTPatcher.kext and IntelBluetoothFirmware.kext](https://github.com/OpenIntelWireless/IntelBluetoothFirmware) with BlueToolFixup.kext from [acidanthera/BrcmPatchRAM](https://github.com/acidanthera/BrcmPatchRAM) - after IntelBTPatcher.kext and before IntelBluetoothFirmware.kext
- [AirportItwlm (use in-built WiFi) or itwlm](https://github.com/OpenIntelWireless/itlwm) with [https://github.com/OpenIntelWireless/HeliPort](HeliPort App) (more stable) 

## Other

- [ECEnabler](https://github.com/1Revenger1/ECEnabler) - Embedded Controller for battery status
- [USBToolBox](https://github.com/USBToolBox/kext) - for mapping USB ports
- [VoodooPS2](https://github.com/acidanthera/VoodooPS2) - Keyboard, Mouse, Touchpad with gesture support
- [VoodooSMBUS](https://github.com/VoodooSMBus/VoodooSMBus) - ELAN Touchpad support
- [BrightnessKeys](https://github.com/acidanthera/BrightnessKeys) - Brightness Keys

# References and Thanks

- [Ryzen and Threadripper(17h and 19h) | OpenCore Install Guide](https://dortania.github.io/OpenCore-Install-Guide/AMD/zen.html)
- [Kexts | ChefKiss](https://chefkissinc.github.io/guide/gathering-files/kexts#input)
- [GitHub - mikigal/ryzen-hackintosh: OpenCore EFI for AMD Ryzen Hackintosh](https://github.com/mikigal/ryzen-hackintosh)
- [FAQ | OpenIntelWireless](https://openintelwireless.github.io/IntelBluetoothFirmware/FAQ.html#what-additional-steps-should-i-do-to-make-bluetooth-work-on-macos-monterey-and-newer)
- [GitHub - long5436/Ryzentosh-Acer-aspire-7-A715-42G-Opencore-EFI: EFI Opencore hackintosh for Acer aspire 7 AMD Ryzen 5 5500U](https://github.com/long5436/Ryzentosh-Acer-aspire-7-A715-42G-Opencore-EFI)
- [GitHub - saeidex/ryzentosh-msi-modern-15: Ryzen 5 5500u Ryzentosh](https://github.com/saeidex/ryzentosh-msi-modern-15)
