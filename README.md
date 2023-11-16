# Nora-EFI
Backups of the EFI for my main rig

| Hardware | Model |
| --- | --- |
| Motherboard | MSI B550 MPG GAMING PLUS |
| CPU | AMD Ryzen 5 5600G with Radeon Graphics |
| Chipset | AMD B550 (Zen 2/3) |
| RAM | 2x8GB DDR4-3200 |
| GPU 0 | AMD Radeon Vega 7 |
| GPU 1 | NVIDIA GeForce GTX 1080 |
| Ethernet | Realtek RTL8168E GbE |
| WiFi | Broadcom BCM943602CS |
| Bluetooth | Broadcom BCM943602CS |
| Audio | Realtek ALC897 |

## Device locations
### PCIe devices 
| PCIe Slot | Device | Link Speed |
| --- | --- | --- |
| `M2_1` | Sabrent Rocket nano (512GB) | PCIe 3.0 x4 |
| `M2_2` | Samsung SSD 960 EVO (500GB) | PCIe 3.0 x4 |
| `PCI_E1` | NVIDIA GeForce GTX 1080 | PCIe 3.0 x16 |
| `PCI_E2` | BCM43602 802.11ac Wireless LAN SoC | PCIe 1.1 x1 |
| `PCI_E3` | Empty | -- |
| `PCI_E4` | SAS2008 PCI-Express Fusion-MPT SAS-2 [Falcon] | PCIe 2.0 x1 |

### SATA devices over `PCI_E4`
| SAS Domain Port | Device |
| --- | --- | 
| `SCSI Target Device @ 9` | APPLE HDD ST500L | 
| `SCSI Target Device @ 10` | SanDisk SD6SB1M1 | 
| `SCSI Target Device @ 11` | WDC WD40EFZX-68A | 
| `SCSI Target Device @ 12` | ST1000LM035-1RK1 | 
| `SCSI Target Device @ 13` | ST9500424AS | 
| `SCSI Target Device @ 14` | Not powered | 
| `SCSI Target Device @ 15` | Not powered | 

## Operating Systems
| OS | Version | Location |
| --- | --- | --- |
| macOS | Sonoma 14.2b3 | Sabrent Rocket nano |
| macOS | Ventura 13.6.3 | Sabrent Rocket nano |
| Linux | Manjaro 23.0.4 | SanDisk SD6SB1M1 |
| Windows | 11 23590 | Samsung SSD 960 EVO |

## OpenCore Setup
OpenCore version: **0.9.5**  
Last kext updates: **10.26.23**  
Current location: **Sabrent Rocket nano**  

### ACPI configuration
| ACPI table | Prebuilt | Enabled | Notes |
| --- | --- | --- | --- |
| `SSDT-CPUR` | Yes | Yes | Required for macOS boot |  
| `SSDT-EC-USBX-DESKTOP` | Yes | Yes | Required for macOS boot |  
| `SSDT-GPU-DISABLE` | No | No | Disabled for non-Metal + Metal |  
| `SSDT-HPET` | No | Yes | Disabling makes pre-Big Sur freeze |  

### Driver configuration
| Driver | Source |
| --- | --- |
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
| `AirportBrcmFixup.kext` | Add | `17.0.0` | `23.9.99` |
| `AMDRyzenCPUPowerManagement.kext` | Add | `17.0.0` | `23.9.99` |
| `AMFIPass.kext` | Add | `20.0.0` | `23.9.99` |
| `AppleALC.kext` | Add | `17.0.0` | `23.9.99` |
| `AppleMCEReporterDisabler.kext` | Add | `17.0.0` | `23.9.99` |
| `AstekFusion2Adapter.kext` | Add | `17.0.0` | `23.9.99` |
| `AstekFusion2Family.kext` | Add | `17.0.0` | `23.9.99` |
| `CSLVFixup.kext` | Add | `20.0.0` | `23.9.99` |
| `DebugEnhancer.kext` | Add | `17.0.0` | `23.9.99` |
| `ECM-Override.kext` | Add | `23.0.0` | `23.9.99` |
| `FeatureUnlock.kext` | Add | `17.0.0` | `23.9.99` |
| `IO80211FamilyLegacy.kext` | Add | `23.0.0` | `23.9.99` |
| `IOSkywalkFamily.kext` | Add</br>Block | `23.0.0` | `23.9.99` |
| `Lilu.kext` | Add | `17.0.0` | `23.9.99` |
| `NootedRed.kext` | Add</br>Add | `19.0.0`</br>`23.0.0` | `21.9.9`</br>`23.9.99` |
| `NVMeFix.kext` | Add | `17.0.0` | `23.9.99` |
| `RealtekRTL8111.kext` | Add | `17.0.0` | `23.9.99` |
| `RestrictEvents.kext` | Add | `17.0.0` | `23.9.99` |
| `SMCAMDProcessor.kext` | Add | `17.0.0` | `23.9.99` |
| `USBMap.kext` | Add | `17.0.0` | `23.9.99` |
| `VirtualSMC.kext` | Add | `17.0.0` | `23.9.99` |
| `WhateverGreen.kext` | Add | `22.0.0` | `22.9.99` |



