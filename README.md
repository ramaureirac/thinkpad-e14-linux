## Current State of GNU/Linux on Lenovo Thinkpad E14 Gen1/Gen2

The following repository provides an overview about Linux support for Lenovo Thinkpad E14 (it should work with E15 as well). Please note this documents are based on my own experience and it doesn't means an official support for this models. If you follow this guide, no one is responsible for any damage to your hardware.

### Contribution

If you want to contribute to get Linux running smoothly on the Lenovo Thinkpad E14 series, report all findings on how to get devices working as pull requests! All help is appreciated.

### Current Status

The table shows up Linux 5.4+ support status for each device on this laptop series. Note that circle means it works but need extra tweak or configuration.
Tweaks can be found on the specific laptops folder.

| Device                            | First Gen                           | Second Gen                | Details                                           |
|-----------------------------------|-------------------------------------|---------------------------|---------------------------------------------------|
| Audio Input & Output              | :heavy_check_mark:                  | :grey_exclamation:        | Some 2nd Gen models have mic problems             |
| Battery                           | :heavy_check_mark:                  | :heavy_check_mark:        |                                                   |
| Bluetooth                         | :heavy_check_mark:                  | :heavy_check_mark:        |                                                   |
| Camera                            | :heavy_check_mark:                  | :heavy_check_mark:        |                                                   |
| Graphics Card (Intel)             | :heavy_check_mark:                  | :heavy_check_mark:        |                                                   |
| Graphics Card (AMD)               | :o:                                 | :heavy_check_mark:        | Dedicated GPU on first gen requieres extra tweaks |
| Graphics Card (Nvidia)            | :heavy_minus_sign:                  | :grey_question:           | Nvidia not tested yet                             |
| Keyboard and Touchpad             | :heavy_check_mark:                  | :heavy_check_mark:        |                                                   |
| Trackpoint and buttons            | :o:                                 | :o:                       | Working, but requires some extra config           |
| NVMe & Internal SSD               | :heavy_check_mark:                  | :heavy_check_mark:        |                                                   |
| Screen                            | :heavy_check_mark:                  | :heavy_check_mark:        |                                                   |
| Suspend & Hibernation             | :o:                                 | :heavy_check_mark:        | Suspension in first gen requires BIOS downgrade   |
| Wi-Fi                             | :heavy_check_mark:                  | :heavy_check_mark:        |                                                   |
| USB                               | :heavy_check_mark:                  | :heavy_check_mark:        |                                                   |
| Fingerprint Reader                | :x:                                 | :x:                       |                                                   |
| Fn Hot Keys                       | :heavy_check_mark:                  | :heavy_check_mark:        | Except F11                                        |
| Fans                              | :heavy_check_mark:                  | :heavy_check_mark:        |                                                   |


### Models
You can find more details about each model on their folder
- [Thinkpad E14 First-Gen](./thinkpad-e14-gen1/README.md),
- [Thinkpad E14 Second-Gen](./thinkpad-e14-gen2/README.md)

### Quick Fixes
Even when Lenovo Thinkpad E14 series are friendly with Linux, there are some tweaks you'll need to do in order make your Linux distro fully compatible with your hardware (check above table). So make sure to see those post installation steps.

- [Enable Trackpoint & Buttons](./tweaks/trackpoint/README.md) : In case your trackpoint is detected by your system but not usable. Also fixes the issue where it just stop working. This problem was found under kernel 5.4 - 5.9.
- [Dedicated AMD GPU](./tweaks/amdgpu-rx640/README.md) : In case you are not able to run specific software with your dedicated AMD GPU. This problem was found on old linux distributions. Anyways make sure to configure your GPU properly.
- [Suspend & Hibernation](./tweaks/suspend-and-hibernation/README.md) : There is an issue with newer BIOS updates and the Thinkpad E14 First-Gen. Check this in case your not able to recover after suspend or hibernation.
- [Intel CPU Throttling](./tweaks/intel-cpu-throttling/README.md) : Performance issues? Check this guide in order to get a better experience with Intel CPUs. Also checkout TLP in order to extend your battery life.
- [Speakers issues in Second Gen](./tweaks/audio/README.md): Fix speakers by disabling the internal mic.


