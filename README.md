## Current State of GNU/Linux on Lenovo Thinkpad E14 Gen1/Gen2

The following repository provides an overview about Linux support for Lenovo Thinkpad E14 (it should work with E15 as well). Please note this documents are based on my own experience and it doesn't means an official support for this models. If you follow this guide, no one is responsible for any damage to your hardware.

### trackpoint drivers officially working
e14 and e15 gen 1 and 2 are now officially supported in the latest version of fedora 34 other distros will follow suit soon likely.

### Contribution

If you want to contribute to get Linux running smoothly on the Lenovo Thinkpad E14 series, report all findings on how to get devices working as pull requests! All help is appreciated. Also, remember to share your model id (this is not really necesary, but it will help us to have a better documentaion for each hardware configuration).

### Current Status

The table shows up Linux 5.4+ support status for each device on this laptop series. Note that circle means it works but need extra tweak or configuration.
Tweaks can be found on the specific laptops folder.

| Key | Working | Needs config | Not working | Untested
|---|---|---|---|---|
| Updated devices | :heavy_minus_sign: | :large_blue_circle: | :large_blue_diamond: | :grey_question: |
| Most devices | :white_check_mark: | :black_circle: | :heavy_multiplication_x: | :grey_question: |
| All devices | :heavy_check_mark: | :red_circle: | :x: | :grey_question: |

| Device | First Gen | Second Gen | Details |
|---|---|---|---|
| Audio Input & Output | :heavy_check_mark: | :white_check_mark: | Some 2nd Gen models have mic problems | 
| Battery | :heavy_check_mark: | :heavy_check_mark: | |
| Bluetooth | :heavy_check_mark: | :heavy_check_mark: | |
| Camera | :heavy_check_mark: | :heavy_check_mark: | |
| Graphics Card (Intel) | :heavy_check_mark: | :heavy_check_mark: | |
| Graphics Card (AMD) | :red_circle: | :heavy_check_mark: | Dedicated GPU on first gen requieres extra tweaks                     |
| Graphics Card (Nvidia) | :heavy_minus_sign: | :grey_question:    | Nvidia not tested yet                                                 |
| Keyboard and Touchpad | :heavy_check_mark: | :heavy_check_mark: | |
| Trackpoint and buttons | :heavy_minus_sign: | :heavy_minus_sign: | Working ootb on up to date distros but more stable distros require some extra config |
| NVMe & Internal SSD | :heavy_check_mark: | :heavy_check_mark: | |
| Screen | :heavy_check_mark: | :heavy_check_mark: | |
| Suspend & Hibernation | :red_circle: | :heavy_check_mark: | Suspension in first gen requires BIOS downgrade |
| Wi-Fi | :heavy_check_mark: | :heavy_check_mark: | |
| USB | :heavy_check_mark: | :heavy_check_mark: | |
| Fingerprint Reader | :x: | :x: | |
| Fn Hot Keys | :heavy_check_mark: | :heavy_check_mark: | Some keys doesn't work (F11 for 1st gen. F9-F11 for 2nd gen) |
| Fans | :heavy_check_mark: | :heavy_check_mark: | |


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


