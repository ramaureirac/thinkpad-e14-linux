## Lenovo Thinkpad E14 second Gen

The following document provides an overview about GNU/Linux (kernel 5.4+) for the Lenovo Thinkpad E14 (second-Gen). Please note this info is based on my own experience and it doesn't represent an official support for this machine. If you follow this guide, no one is responsible for any damage to your hardware.

According to Lenovo's web site. There are four base models for the Lenovo Thinkpad E14(gen2) Amd version, 11th gen intel version black 8gb ddr4, 11th gen with nvidia, and grey intel 11th.

To checks if hardware works, all test were done with some Linux Distributions (Ubuntu, Fedora and Arch) To state the obvious: The newer kernel the better.

#### Tested hardware

So I bought a Thinkpad E14 (second-gen).

| Device        | Hardware                       |
|---------------|--------------------------------|
| MODEL ID      | 20TBS08F00                     |
| CPU           | Intel i5-1135G7 @4.2Ghz        |
| GPU           | Intel iris Xe                  |
| RAM           | 8GB DDR4 3200hz                |
| WIFI          | Intel Wi-Fi6 AX201             |
| AUDIO         | Dual Speaker by Harman         |

#### Linux distribution compatibility

I also tested various Linux distributions on this machine. Here they are some of them. To be honnest there are some easy tweaks you must do in order to get your system fully compatible with your favorite distro (see next secction). In my personal opinion Fedora 33 and Pop! where the best options out there (at least for me)

| Distro            | Status             | Additional notes                                                             |
|-------------------|--------------------|------------------------------------------------------------------------------|
| Debian 10         | :x:                | Not able to boot                                                             |
| Debian Testing    | :o:                | Requires firmware-sof-signed for audio and firmware-iwlwifi for Wi-Fi        |
| Ubuntu 20.04      | :heavy_check_mark: | Everything works out of the box! (update kernel for better AMD support)      |
| Fedora 33         | :heavy_check_mark: | Everything works out of the box!                                             |
| Arch Linux        | :heavy_check_mark: | Everything works out of the box!                                             |
| Pop! OS 20.10     | :heavy_check_mark: | Everything works out of the box!                                             |

### Current State

In this secction I'll show a detailed overview about Linux compatibility for Lenovo Thinkpad E14 (second-gen). As I said before, there are some tweaks you must do  on your system in order to get a fully functional Linux Workstation. Please note I've made this table with Linux 5.4 LTS. The current version (5.9) doesn't require extra tweaks except for BIOS downgrade.

| Device                            | Status                              | Additional notes                                                                |
|-----------------------------------|-------------------------------------|---------------------------------------------------------------------------------|
| Audio Input & Output              | :grey_exclamation:                  | Some 2nd gen models have mic problems                                           |
| Battery                           | :heavy_check_mark:                  | Up to four-six hours of battery life!                                           | 
| Bluetooth                         | :heavy_check_mark:                  | Working!                                                                        |
| Camera                            | :heavy_check_mark:                  | Working, for some reason Kamoso applies a red filter                            |
| Graphics Card (Intel)             | :heavy_check_mark:                  | Working!                                                                        |
| Graphics Card (Intel)             | :heavy_check_mark:                  | Working!                                                                        |
| Keyboard and Touchpad             | :heavy_check_mark:                  | Working!,                                                                       |
| Trackpoint and buttons            | :o:                                 | Working, append "psmouse.elantech_smbus=0" as boot parameter [here](../tweaks/trackpoint/README.md) | 
| NVMe & Internal SSD               | :heavy_check_mark:                  | Working!                                                                        |
| Screen                            | :heavy_check_mark:                  | Working!                                                                        |
| Suspend & Hibernation             | :heavy_check_mark:                  | Windows suspend works but ironicly linux suspend doesnt (bios options)          |                 
| Wi-Fi                             | :heavy_check_mark:                  | Intel Wireless works out of the box!                                            |
| USB                               | :heavy_check_mark:                  | Working!                                                                        |
| Fingerprint Reader                | :x:                                 | Definitely not working                                                          |
| Fn Hot Keys                       | :heavy_check_mark:                  | Working except for F9, F10 and F11                                              |
| Fans                              | :heavy_check_mark:                  | Working!                                                                        |

#### Audio Input & Output

It seems some second gen laptops are having issues with the speakers. The ways to fix it is by disabling the internal mic. Please checkout [Speakers issues in Second Gen](../tweaks/audio/README.md)

#### Keyboard, Touchpad & Trackpoint

all of it works if you add the [grub-config](../tweaks/trackpoint/README.md)

#### Suspend & Hibernation

Works fine on default options.

### Conclusions

Works fine once grub configs have been changed. Great laptop and works well with linux.
