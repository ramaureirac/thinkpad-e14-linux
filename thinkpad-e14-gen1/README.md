## Lenovo Thinkpad E14 First Gen

The following document provides an overview about GNU/Linux (kernel 5.4+) for the Lenovo Thinkpad E14 (First-Gen). Please note this info is based on my own experience and it doesn't represent an official support for this machine. If you follow this guide, no one is responsible for any damage to your hardware.

According to Lenovo's web site. There are three base models for the Lenovo Thinkpad E14 according to their wireless network adapter; wich can be a Realtek RTL8822CE or an Intel Wireless AC9560/AX201. A part of that, everything else is almost identical except for the posibility to include a dedicated GPU (AMD Radeon 625/AMD Radeon RX640)

To checks if hardware works, all test were done with some Linux Distributions (Ubuntu, Fedora and Arch) To state the obvious: The newer kernel the better.

#### Tested hardware

So I bought a Thinkpad E14 (first-gen). I got to say it's one of the most Linux friendly laptop that I ever have, performance is smooth (GNOME lags a little), battery its ok (4-6 hrs) and you can even play demanding hardware games like Rise of the Tomb Raider with your AMD GPU (720p @30FPS mid settings). The only thing that doesn't work (at the moment) is the fingerprint reader. The following table shows up my Thinkpad specs:

| Device        | Hardware                       |
|---------------|--------------------------------|
| CPU           | Intel i5-10210U @4.2Ghz        |
| GPU           | Intel UHD + AMD RX640 GDDR5    |
| RAM           | 16GB DDR4 2666Mhz              |
| WIFI          | Intel Wi-Fi6 AX201             |
| AUDIO         | Dual Speaker by Harman         |

#### Linux distribution compatibility

I also tested various Linux distributions on this machine. Here they are some of them. To be honnest there are some easy tweaks you must do in order to get your system fully compatible with your favorite distro (see next secction). In my personal opinion Fedora 33 and Pop! where the best options out there (at least for me).

| Distro        | Status             | Additional notes                                                             |
|---------------|--------------------|------------------------------------------------------------------------------|
| Debian 10     | :x:                | Not able to boot. Debian testing presents random black flickering with GNOME |
| Ubuntu 20.04  | :heavy_check_mark: | Everything works out of the box! (update kernel for better AMD support)      |
| Fedora 33     | :heavy_check_mark: | Everything works out of the box! (requires driver tweaks)                    |
| Arch Linux    | :heavy_check_mark: | Requires some alsa tweaks (sound too low)                                    |
| Pop! OS 20.10 | :heavy_check_mark: | Everything works out of the box!                                             |

### Current State

In this secction I'll show a detailed overview about Linux compatibility for Lenovo Thinkpad E14 (fist-gen). As I said before, there are some tweaks you must do  on your system in order to get a fully functional Linux Workstation. Please note I've made this table with Linux 5.4 LTS. The current version (5.9) doesn't require extra tweaks except for BIOS downgrade.

| Device                            | Status                              | Additional notes                                                                |
|-----------------------------------|-------------------------------------|---------------------------------------------------------------------------------|
| Audio Input & Output              | :heavy_check_mark:                  | Working, when you connect headphones internal mic will be disable               |
| Battery                           | :heavy_check_mark:                  | Up to six hours of battery life!                                                | 
| Bluetooth                         | :heavy_check_mark:                  | Working!                                                                        |
| Camera                            | :heavy_check_mark:                  | Working, for some reason Kamoso applies a red filter                            |
| Graphics Card (Intel)             | :heavy_check_mark:                  | Working!                                                                        |
| Graphics Card (RX640)             | :o:                                 | Working after installing amdgpu drivers                                         |
| keyboard and touchpad             | :heavy_check_mark:                  | Working!                                                                        |
| Trackpoint and buttons            | :o:                                 | Working, append "psmouse.elantech_smbus=0" as boot parameter                    |
| NVMe & Internal SSD               | :heavy_check_mark:                  | Working!                                                                        |
| Screen                            | :heavy_check_mark:                  | Working!                                                                        |
| Suspend & Hibernation             | :o:                                 | Needs BIOS downgrade, ECP 1.04                                                  |
| Wi-Fi                             | :heavy_check_mark:                  | Intel Wireless works out of the box!                                            |
| USB                               | :heavy_check_mark:                  | Working!                                                                        |
| Fingerprint Reader                | :x:                                 | Definitely not working                                                          |
| Fn Hot Keys                       | :heavy_check_mark:                  | Working except for F11                                                          |
| Fans                              | :heavy_check_mark:                  | Working!                                                                        |


#### AMD RX640 Graphic Card

In case your model includes and AMD GPU (Radeon 625 or Radeon RX640) you may need to install the *amdgpu* drivers (they should be included on your distro repos). For some unkown reason some distros (like Fedora 32, Ubuntu 18.10, Debian Testing) installs the *ati* drivers instead, so you'll need to replace them by doing:

    # install on fedora:
    sudo dnf install xorg-x11-drv-amdgpu -y
    # uninstall old drivers (ati + intel):
    sudo dnf remove xorg-x11-drv-intel 
    sudo dnf remove xorg-drv-x11-ati
    
    # install on debian/ubuntu:
    sudo apt install -y libdrm-amdgpu1 xserver-xorg-video-amdgpu
    # uninstall old drivers (ati + intel):
    sudo apt remove xserver-xorg-video-ati
    sudo apt remove xserver-xorg-video-intel

Now, when ever you wanna start an application with dedicated graphics, use the following command:

    # start VLC with AMD dedicated graphics
    DRI_PRIME=1 vlc
    
Now, assuming you wanna play some video games you should install corectrl (for tweak your gpu) and gamemode (optional, increase cpu performance). The only thing you wanna do with them is to lowe the TDP for your AMD GPU; default is 25 (wich is too much), so set it to 18 and gamming will be fine (CS:GO, Dota, Tomb Raider, etc.). Install corectrl is quite easy on any Linux distro, so I'll provide you the links where you can find the official documentation:

- https://gitlab.com/corectrl/corectrl
- https://github.com/FeralInteractive/gamemode

In case you are not able to twak your AMD GPU with corectrl, put this as boot parameter on your grub configuration file.

    GRUB_CMDLINE_LINUX="rhgb quiet ... amdgpu.ppfeaturemask=0xffffffff ..."

#### Keyboard, Touchpad & Trackpoint

To be honest this should work out of the box on any distro running 5.4+ kernel. However, some people say after some time the touchpad and trackpad stop working (some kind of freeze?). I order to fix it add the following line in your grub configuration file.
    
    GRUB_CMDLINE_LINUX="rhgb quiet ... psmouse.elantech_smbus=0 ..."
    
#### Suspend & Hibernation

When I recived my Thinkpad it arrived with BIOS v1.09 wich for some reason wasn't able to recover after suspend (black screen on every monitor). In order to fix it you may need to apply a BIOS Downgrade by downloading the version 1.06 (iso file) from Lenovo's support center. Then flash it on a USB with Etcher. Make sure to enable BIOS rollback on BIOS settings!

See also:
- https://pcsupport.lenovo.com/us/en/products/laptops-and-netbooks/thinkpad-edge-laptops/thinkpad-e14-type-20ra-20rb/downloads/DS541516
- https://support.lenovo.com/us/en/solutions/ht117858-bios-rollback-flash-failure-secure-flash-authentication-failed-when-secure-rollback-prevention-enabled-thinkpad-t450-t450s

### Conclusions

As I said before Thinkad E14 (first-gen) is one of the best latptops for Linux that I ever have. Yes, you must apply a BIOS downgrade a add some boot parameters in order to keep everything working, but still as long as my system works everything is just some irrelevant technical details. I would recommend this laptops for Linux use.
