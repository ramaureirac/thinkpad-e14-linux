## Current State of GNU/Linux on Lenovo Thinkpad E14 Gen1/Gen2

The following repository provides an overview about Linux support for Lenovo Thinkpad E14 (it should work with E15 as well). Please note this documents are based on my own experience and it doesn't means an official support for this models. If you follow this guide, no one is responsible for any damage to your hardware.

### Contribution

If you want to contribute to get Linux running smoothly on the Lenovo Thinkpad E14 series, report all findings on how to get devices working as pull requests! All help is appreciated.

### Current Status

The table shows up Linux 5.4+ support status for each device on this laptop series. Note that circle means it works but need extra tweak or configuration.
Tweaks can be found on the specific laptops folder.

| Device                            | First Gen                           | Second Gen                |
|-----------------------------------|-------------------------------------|---------------------------|
| Audio Input & Output              | :heavy_check_mark:                  | :heavy_check_mark:        |
| Battery                           | :heavy_check_mark:                  | :heavy_check_mark:        | 
| Bluetooth                         | :heavy_check_mark:                  | :heavy_check_mark:        |
| Camera                            | :heavy_check_mark:                  | :heavy_check_mark:        |
| Graphics Card (Intel)             | :heavy_check_mark:                  | :heavy_check_mark:        |
| Graphics Card (AMD)               | :o:                                 | :heavy_check_mark:        |
| Graphics Card (Nvidia)            | :heavy_minus_sign:                  | :o:                       |
| Keyboard and Touchpad             | :heavy_check_mark:                  | :heavy_check_mark:        |
| Trackpoint and buttons            | :o:                                 | :o:                       |
| NVMe & Internal SSD               | :heavy_check_mark:                  | :heavy_check_mark:        |
| Screen                            | :heavy_check_mark:                  | :heavy_check_mark:        |
| Suspend & Hibernation             | :o:                                 | :heavy_check_mark:        |
| Wi-Fi                             | :heavy_check_mark:                  | :heavy_check_mark:        |
| USB                               | :heavy_check_mark:                  | :heavy_check_mark:        |
| Fingerprint Reader                | :x:                                 | :x:                       |
| Fn Hot Keys                       | :heavy_check_mark:                  | :heavy_check_mark:        |
| Fans                              | :heavy_check_mark:                  | :heavy_check_mark:        |
    
You can find more details of every model on their folder:
[Gen1](./thinkpad-e14-gen1/README.md),
[Gen2](./thinkpad-e14-gen2/README.md)

[Grub-Config](./grub-config/README.md) to fix the touchpoint


