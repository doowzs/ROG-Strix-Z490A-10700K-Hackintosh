# ROG-Strix-Z490-A 10700K Hackintosh

## Hardware

Hardware Specification:

- MotherBoard: ROG Strix Z490-A Gaming
  - I225-V Ethernet is Rev.3
- CPU: Intel i7-10700K
- iGPU: Intel UHD 630
- dGPU: AMD Radeon RX5700XT
- MEM: 4x Corsair 16G DDR4 Memory @ 3200MHz
- Storage: 2x Samsung 970 EVO Plus 500G
- WiFi: Fenvi FV-T919 (BCM94360CS)

PCIe configuration:

|PCIe Slot|Hardware|
|---------|--------|
|x1       |FV-T919 |
|x16      |RX5700XT|
|x16      |Empty   |
|x4       |Empty   |
|x16      |Empty   |

BIOS configuration:

- BIOS version: 2103
- Advanced:
  - disable VT-D
  - enable Memory Remapping
  - enable iGPU / Multi-monitor
  - enable XCHI Hand-off
  - set SATA mode to AHCI
- Boot:
  - disable CSM
  - disable Fast Boot
  - set OS type to other OS

## Working

- Ethernet (using AppleIntelI210Ethernet.kext)
- Onboard Audio
- WiFi and Bluetooth (no patch required)
- iServices (including Airdrop, Handoff)
- Virtualization
- Dual boot with Windows 10

## Not working

- Hardware DRM (Netflix, etc.)
- Type-C Earphones (USB-A audio works)

## Installation

1. Create macOS install media
2. Mount EFI of flash drive and copy files
3. Install macOS
4. Mount EFI of boot disk and copy files
5. Load or create USB mapping
6. Install Windows if needed

## USB Mapping Data

ROG-Strix-Z490-A comes with >15 USB ports.

USB mapping is required for macOS >= 11.3 as it only accepts a maximum of 15 ports in one USB hub.

|Type |ID (left)  |ID (right) |Comments|
|-----|-----------|-----------|--------|
|Front|08         |05 (Type-C)|Type-C contains a switch|
|Pins |06         |07         |used for bluetooth, mapped as internal|
|Pins |~~11~~     |           |used for AURA RGB, deleted
|Rear(Top) |12         |13         |USB2.0 only, used for mouse and keyboard, mapped as internal|
|Rear |04 (Type-C)|03         |Type-C contains a switch, 03 mapped as USB3.0 only|
|Rear |02         |01         |mapped as USB3.0 only|
|Rear(Bottom) |09         |10         |mapped as USB2.0 only|