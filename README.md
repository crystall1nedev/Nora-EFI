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
| `M2A` | Empty | -- |
| `M2B` | Sabrent Rocket nano (512GB) | PCIe 3.0 x4 |
| `M2C` | Samsung SSD 960 EVO (500GB) | PCIe 3.0 x4 |
| `PCIEX16` | Empty | -- |
| `PCIEX1_1` | BCM43602 802.11ac Wireless LAN SoC | PCIe 1.1 x1 |
| `PCIEX8` | NVIDIA GeForce GTX 1060 3GB | PCIe 3.0 x4 |
| `PCIEX1_2` | Empty | -- |
| `PCIEX4` | Empty | -- |
| `THB_C` | Empty | -- |

### SATA devices
| SATA Port | Device |
| --- | --- | 
| 1 | APPLE HDD ST500L | 
| 2 | SanDisk SD6SB1M1 | 
| 3 | WDC WD40EFZX-68A | 
| 4 | ST1000LM035-1RK1 | 
| 5 | None | 
| 6 | None | 

## Operating Systems
| OS | Version | Location |
| --- | --- | --- |
| macOS | Sonoma | Sabrent Rocket nano |
| macOS | Ventura | TBA |
| macOS | Catalina | TBA |
| macOS | High Sierra | TBA |
| Linux | Arch Linux | ST1000LM035-1RK1 |
| Windows | 11 | Samsung SSD 960 EVO |

## OpenCore Setup
OpenCore version: **0.9.8**  
Last kext updates: **12.30.23**  
Current location: **Sabrent Rocket nano**  

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
| `AudioDxe.efi` | OpenCorePkg |
| `btrfs_x64.efi` | rEFInd |
| `CrScreenshotDxe.efi` | OpenCorePkg |
| `ext2_x64.efi` | rEFInd |
| `ext4_x64.efi` | rEFInd |
| `HfsPlus.efi` | OpenCorePkg |
| `NvmExpressDxe.efi` | OpenCorePkg |
| `OpenCanopy.efi` | OpenCorePkg |
| `OpenLegacyBoot.efi` | OpenCorePkg |
| `OpenLinuxBoot.efi` | OpenCorePkg |
| `OpenNtfsDxe.efi` | OpenCorePkg |
| `OpenPartitionDxe.efi` | OpenCorePkg |
| `OpenRuntime.efi` | OpenCorePkg |
| `reiserfs_x64.efi` | rEFInd |
| `ResetNvramEntry.efi` | OpenCorePkg |
| `ToggleSipEntry.efi` | OpenCorePkg |

### Kext configuration
| Kext | Mode | Kernel Min | Kernel Max |
| --- | --- | --- | --- |
| `AMDRyzenCPUPowerManagement.kext` | Add | `17.0.0` | `23.9.99` |
| `AMFIPass.kext` | Add | `20.0.0` | `23.9.99` |
| `AppleALC.kext` | Add | `17.0.0` | `23.9.99` |
| `AppleMCEReporterDisabler.kext` | Add | `17.0.0` | `23.9.99` |
| `AppleIGB.kext` | Add | `17.0.0` | `23.9.99` |
| `BFixup.kext` | Add | `20.0.0` | `23.9.99` |
| `CatalinaI210Ethernet.kext` | Add | `20.0.0` | `23.9.99` |
| `CSLVFixup.kext` | Add | `20.0.0` | `23.9.99` |
| `DebugEnhancer.kext` | Add | `17.0.0` | `23.9.99` |
| `ECM-Override.kext` | Add | `23.0.0` | `23.9.99` |
| `FeatureUnlock.kext` | Add | `17.0.0` | `23.9.99` |
| `IO80211FamilyLegacy.kext` | Add | `23.0.0` | `23.9.99` |
| `IOSkywalkFamily.kext` | Add</br>Block | `23.0.0` | `23.9.99` |
| `Lilu.kext` | Add | `17.0.0` | `23.9.99` |
| `NootedRed.kext` | Add</br>Add | `19.0.0`</br>`23.0.0` | `21.9.9`</br>`23.9.99` |
| `NVMeFix.kext` | Add | `17.0.0` | `23.9.99` |
| `RadeonSensor.kext` | Add | `19.0.0` | `23.9.99` |
| `RestrictEvents.kext` | Add | `17.0.0` | `23.9.99` |
| `SMCAMDProcessor.kext` | Add | `17.0.0` | `23.9.99` |
| `SMCRadeonGPU.kext` | Add | `19.0.0` | `23.9.99` |
| `USBMap.kext` | Add | `17.0.0` | `23.9.99` |
| `VirtualSMC.kext` | Add | `17.0.0` | `23.9.99` |
| `WhateverGreen.kext` | Add | `17.0.0`</br>`22.0.0` | `18.9.99`</br>`22.9.99` |

### Tool configuration
