## Current State of GNU/Linux on Lenovo Thinkpad E14 (First-Gen)

The following repository provides an overview about Linux support for Lenovo Thinkpad E14 (it should work with E15 as well). Please note this documents are based on my own experience and it doesn't means an official support for this models. If you follow this guide, no one is responsible for any damage to your hardware.

According to Lenovo's documentation there are different models of the Thinkpad E14 based on the Wi-Fi card ,wich can be a Realtek RTL8822CE or an Intel Wireless AC9560/AX201. A part of that, all models are nearly identical except for the option to add an AMD RX640 as dedicated graphics card. 

Theres also a second-gen Thinkpad E14 wich includes a AMD Ryzen 4000 series CPU insted of the Intel 10th gen. This suppose a better performance and battery life. Also, as far as I know, theres only a Realtek RTL8822CE available as a Wi-Fi adapter and there are no dedicated GPUs for this model.

To checks if hardware works, all test were done with some Linux Distributions (Ubuntu, Fedora and Arch) To state the obvious: The newer kernel the better. However, I personally suggest you to keep the current LTS version (Linux 5.4)


### Contribution

If you want to contribute to get Linux running smoothly on the Lenovo Thinkpad E14 series, report all findings on how to get devices working as pull requests! All help is appreciated.

### Current Status (First-Gen)

The table shows up Linux 5.4+ support status for each device on this laptop.

| Device                            | Status                              | Additional notes                                                                |
|-----------------------------------|-------------------------------------|---------------------------------------------------------------------------------|
| Audio Input & Output              | :heavy_check_mark:                  | Working, when you connect headphones internal mic will be disable               |
| Battery                           | :heavy_check_mark:                  | Up to six hours of battery life!                                                | 
| Bluetooth                         | :heavy_check_mark:                  | Working!                                                                        |
| Camera                            | :heavy_check_mark:                  | Working, for some reason Kamoso applies a red filter                            |
| Graphics Card (Intel)             | :heavy_check_mark:                  | Working!                                                                        |
| Graphics Card (RX640)             | :o:                                 | Working after installing amdgpu drivers                                         |
| Keyboard, Touchpad and Trackpoint | :o:                                 | Working, append "psmouse.elantech_smbus=0" as boot parameter                    |
| NVMe & Internal SSD               | :heavy_check_mark:                  | Working!                                                                        |
| Screen                            | :heavy_check_mark:                  | Working!                                                                        |
| Suspend & Hibernation             | :o:                                 | Needs BIOS downgrade, ECP 1.04                                                  |
| Wi-Fi                             | :heavy_check_mark:                  | Intel Wireless works out of the box!                                            |
| USB                               | :heavy_check_mark:                  | Working!                                                                        |
| Fingerprint Reader                | :x:                                 | Definitely not working                                                          |
| Fn Hot Keys                       | :heavy_check_mark:                  | Working except for F11                                                          |
| Fans                              | :heavy_check_mark:                  | Working!                                                                        |

#### Audio Input & Output

This laptop model includes two stereo speakers (Harman Kardon) wich work fine out of the box. If you are having issues with the internal audio input, and you are using PulseAudio; then try switching between the built-in audio profiles. This laptop (for some unknow reason) disables internal mic when a headphone is plugged-in, so make sure your external headset have a working mic.

Finally, I've tested audio vio HDMI, Bluetooth and USB-connected devices and I haven't found any issue.

See also:
 - https://wiki.archlinux.org/index.php/Advanced_Linux_Sound_Architecture/Troubleshooting#Low_Sound_Volume
 - https://wiki.archlinux.org/index.php/Advanced_Linux_Sound_Architecture/Troubleshooting#No_microphone_input

#### AMD RX640 Graphic Card

In case your model includes the AMD RX640 you'll have to do some extra stuff in order to run specific software with your dedicated graphic card (Blender, Steam Games, Shotcut, etc.). First, make shure you have the correct graphic driver for your GPU, in this case the "amdgpu" driver; for some reason some distros install "ati" drivers by default:

    # install on fedora:
    sudo dnf install xorg-x11-drv-amdgpu -y
    
    # install on arch:
    sudo pacman -S xf86-video-amdgpu
    
    # install on ubuntu:
    sudo apt install -y libdrm-amdgpu1 xserver-xorg-video-amdgpu
    
Now, when ever you wanna start an application with dedicated graphics, use the following command:

    # start VLC with AMD RX640
    DRI_PRIME=1 vlc

You can also create custom .desktop entries or launch arguments on Steam.

In case you have the Intel or ATI drivers you can uninstall them by doing:

    # fedora:
    sudo dnf remove xorg-x11-drv-intel 
    sudo dnf remove xorg-drv-x11-ati
    
    # arch:
    sudo pacman -R xf86-video-ati 
    sudo pacman -R xf86-video-intel
    
    # ubuntu:
    sudo apt remove xserver-xorg-video-ati
    sudo apt remove xserver-xorg-video-intel

See also:

- https://gitlab.com/corectrl/corectrl/-/wikis/Setup
- https://github.com/FeralInteractive/gamemode

#### Keyboard, Touchpad & Trackpoint

To be honest this should work out of the box on any distro running 5.4+ kernel. However, some people say after some time the touchpad and trackpad stop working (some kind of freeze?). I order to fix it add the following line in your grub configuration file.
    
    GRUB_CMDLINE_LINUX="rhgb quiet ... psmouse.elantech_smbus=0 ..."
    
#### Suspend & Hibernation

When I recived my Thinkpad it arrived with BIOS v1.09 wich for some reason wasn't able to recover after suspend (black screen on every monitor). In order to fix it you may need to apply a BIOS Downgrade by downloading the version 1.06 (iso file) from Lenovo's support center. Then flash it on a USB with Etcher. Make sure to enable BIOS rollback on BIOS settings!

See also:
- https://pcsupport.lenovo.com/us/en/products/laptops-and-netbooks/thinkpad-edge-laptops/thinkpad-e14-type-20ra-20rb/downloads/DS541516
- https://support.lenovo.com/us/en/solutions/ht117858-bios-rollback-flash-failure-secure-flash-authentication-failed-when-secure-rollback-prevention-enabled-thinkpad-t450-t450s



### Current Status (Second-Gen)

| Device                            | Status                              | Additional notes                                                                |
|-----------------------------------|-------------------------------------|---------------------------------------------------------------------------------|
| Audio Input & Output              | :heavy_check_mark:                  | Working, when you connect headphones internal mic will be disable               |
| Battery                           | :heavy_check_mark:                  | Up to six hours of battery life!                                                | 
| Bluetooth                         | :heavy_check_mark:                  | Working!                                                                        |
| Camera                            | :heavy_check_mark:                  | Working, for some reason Kamoso applies a red filter                            |
| Graphics Card (AMD Vega)          | :heavy_check_mark:                  | Working, for kenrel 5.6+                                                        |
| Keyboard, Touchpad and Trackpoint | :x:                                 | Trackpoint not woking                                                           | 
| NVMe & Internal SSD               | :heavy_check_mark:                  | Working!                                                                        |
| Screen                            | :heavy_check_mark:                  | Working!                                                                        |
| Suspend & Hibernation             | :x:                                 | Temp solution: apply s2idle as boot parameter                                   |
| Wi-Fi                             | :heavy_check_mark:                  | Intel Wireless works out of the box!                                            |
| USB                               | :heavy_check_mark:                  | Working!                                                                        |
| Fingerprint Reader                | :x:                                 | Definitely not working                                                          |
| Fn Hot Keys                       | :x:                                 | Not working!                                                                    |
| Fans                              | :heavy_check_mark:                  | Working!                                                                        |

