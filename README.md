   # Nora EFI and device configuration
**This repository is used to back up the EFI folder for Nora**, which is my main AMD64 build.

## Quick specifications
| Hardware | Model |
| --- | --- |
| Motherboard | GIGABYTE X570 AORUS ULTRA rev 1.2 |
| CPU | AMD Ryzen 5 5600G with Radeon Graphics |
| Chipset | AMD X570 (Zen 2/3) |
| RAM | 2x8GB DDR4-3200 |
| GPU 0 | AMD Radeon Vega 7 |
| GPU 1 | NVIDIA GeForce GTX 1060 3GB |
| Ethernet | Intel I211-AT GbE |
| WiFi | Broadcom BCM943602CS |
| Bluetooth | Broadcom BCM943602CS |
| Audio | Realtek ALC1220 |
| PSU | Thermaltake Smart 80+ 500W |
| Case | Phanteks G500A D-RGB |

## Device locations
### PCIe devices 
| PCIe Slot | Device | Link Speed |
| --- | --- | --- |
| `M2A` | Intel SSDPEKNW512G8 | PCIe 3.0 x4 |
| `M2B` | Empty | -- |
| `M2C` | Empty | -- |
| `PCIEX16` | NVIDIA GeForce GTX 1080 | PCIe 3.0 x16 |
| `PCIEX1_1` | Empty | -- |
| `PCIEX8` | Empty | -- |
| `PCIEX1_2` | BCM43602 802.11ac Wireless LAN SoC | PCIe 1.1 x1 |
| `PCIEX4` | Empty | -- |
| `THB_C` | Empty | -- |

### SATA devices
| SATA Port | Device |
| --- | --- | 
| 1 | Empty | 
| 2 | Empty | 
| 3 | Empty | 
| 4 | Empty | 
| 5 | Empty | 
| 6 | Empty | 

## Operating Systems
| OS | Version | Location |
| --- | --- | --- |
| macOS | Tahoe | Intel SSDPEKNW512G8 |
| Linux | Arch Linux | ST1000LM035-1RK1 |
| Windows | 11 | Samsung SSD 960 EVO |

## OpenCore Setup
OpenCore version: **1.0.6**  
Last kext updates: **11.30.25**  
Current location: **Intel SSDPEKNW512G8**  

### ACPI configuration
| ACPI table | Prebuilt | Enabled | 
| --- | --- | --- | 
| `SSDT-EC` | No | Yes | 
| `SSDT-HPET` | No | Yes | 
| `SSDT-PMC` | No | Yes | 
| `SSDT-RHUB` | No | Yes | 
| `SSDT-SBUS-MCHC` | No | Yes | 
| `SSDT-USBX` | No | Yes |

### Driver configuration
| Driver | Source |
| --- | --- |
| `apfs_aligned.efi` | Apple |
| `AudioDxe.efi` | OpenCorePkg |
| `btrfs_x64.efi` | rEFInd |
| `CrScreenshotDxe.efi` | OpenCorePkg |
| `FirmwareSettingsEntry.efi` | OpenCorePkg |
| `ext4_x64.efi` | rEFInd |
| `Hash2DxeCrypto.efi` | OpenCorePkg |
| `HfsPlus.efi` | OpenCorePkg |
| `OpenCanopy.efi` | OpenCorePkg |
| `OpenLinuxBoot.efi` | OpenCorePkg |
| `OpenNetworkBoot.efi` | OpenCorePkg |
| `OpenRuntime.efi` | OpenCorePkg |
| `ResetNvramEntry.efi` | OpenCorePkg |
| `ToggleSipEntry.efi` | OpenCorePkg |

### Kext configuration
| Kext | Mode | Kernel Min | Kernel Max |
| --- | --- | --- | --- |
| `AMDRyzenCPUPowerManagement.kext` | Add | `17.0.0` | `25.9.99` |
| `AMFIPass.kext` | Add | `20.0.0` | `24.9.99` |
| `AppleALC.kext` | Add | `17.0.0` | `25.9.99` |
| `AppleMCEReporterDisabler.kext` | Add | `17.0.0` | `25.9.99` |
| `CatalinaI210Ethernet.kext` | Add | `20.0.0` | `25.9.99` |
| `CSLVFixup.kext` | Add | `20.0.0` | `25.9.99` |
| `DebugEnhancer.kext` | Add | `17.0.0` | `25.9.99` |
| `ECM-Override.kext` | Add | `23.0.0` | `25.9.99` |
| `FeatureUnlock.kext` | Add | `17.0.0` | `25.9.99` |
| `ForgedInvariant.kext` | Add | `17.0.0` | `25.9.99` |
| `IntelMKLFixup.kext` | Add | `20.0.0` | `25.9.99` |
| `IO80211FamilyLegacy.kext` | Add | `23.0.0` | `25.9.99` |
| `IOSkywalkFamily.kext` | Add</br>Block | `23.0.0` | `25.9.99` |
| `Lilu.kext` | Add | `17.0.0` | `25.9.99` |
| `NootedRed.kext` | Add</br>Add | `19.0.0`</br>`23.0.0` | `21.9.9`</br>`25.9.99` |
| `NVMeFix.kext` | Add | `17.0.0` | `25.9.99` |
| `RestrictEvents.kext` | Add | `17.0.0` | `25.9.99` |
| `SMCAMDProcessor.kext` | Add | `17.0.0` | `25.9.99` |
| `SMCRadeonSensors.kext` | Add | `19.0.0` | `25.9.99` |
| `USBMap.kext` | Add | `17.0.0` | `25.9.99` |
| `VirtualSMC.kext` | Add | `17.0.0` | `25.9.99` |
| `WhateverGreen.kext` | Add | `17.0.0`</br>`22.0.0` | `18.9.99`</br>`22.9.99` |
| `YAFOAppleIGB.kext` | Add | `17.0.0` | `25.9.99` |

### OCLP root patching configuration
- `modern_wireless.py` required for macOS Sonoma and later.
- `modern_audio.py` required for macOS Tahoe beta 2 and later.
