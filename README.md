## Current State of GNU/Linux on Lenovo Thinkpad E14 Series

The following repository provides an overview about GNU/Linux support for some diferent models of the Lenovo Thinkpad E14 family (it should work with E15 series as well). Please note this documents are based on our own experience and it doesn't represent an official support for these models. If you follow this guide, no one is responsible for any damage to your hardware. If you wish to purchase one of these laptops, make sure that it complies with the same hardware configuration indicated in this repository. Remember that some devices may change depending on the market and region to which they belong.

### Contribution

If you want to contribute to get Linux running smoothly on the Lenovo Thinkpad E14 series, report all findings on how to get devices working as pull requests! All help is appreciated. Also, remember to share your model id (this is not really necesary, but it will help us to have a better documentaion for each hardware configuration).

### Current ThinkPad E14 Models

I initially thought of this repository as being exclusive to the first generation Lenovo ThinkPad E14. However, thanks to the support of the community, today we can provide a base documentation for different sub-models of the family as well as the second wave of laptops. Unfortunately we have not yet been able to describe every existing model and therefore we recommend to purchase only those that have the same configuration as the ones we document in this repository. That said, we present the models that we know exist around the world. You can clic them in order to know their details.

| Generation            | Available Models                        |
|-----------------------|-----------------------------------------|
| First                 | [![](https://img.shields.io/badge/1st_vanila-working-success.svg)](./thinkpad-e14-gen1/vanila.md) [![](https://img.shields.io/badge/1st_polaris-tweak_required-green.svg)](./thinkpad-e14-gen1/polaris.md) [![](https://img.shields.io/badge/1st_realtek-untested-lightgrey.svg)](./thinkpad-e14-gen1/realtek.md) |
| Second                | [![](https://img.shields.io/badge/2nd_vanila-tweak_required-green.svg)](./thinkpad-e14-gen2/vanila.md) [![](https://img.shields.io/badge/2nd_iris-tweak_required-green.svg)](./thinkpad-e14-gen2/iris.md) [![](https://img.shields.io/badge/2nd_ryzen-untested-lightgrey.svg)](./thinkpad-e14-gen2/ryzen.md) [![](https://img.shields.io/badge/2nd_nvidia-untested-lightgrey.svg)](./thinkpad-e14-gen2/nvidia.md) |


### Current Status

The checks if hardware works below were done with multiple Linux distributions. To state the obvious: The newer the kernel the better. The information below assumes that you run Linux 5.10 LTS or newer.

| Device                      | Status                                    |
| ----------------------------|-------------------------------------------|
| Audio Input & Output        | ![](https://img.shields.io/badge/1st_vanila-working-success.svg) ![](https://img.shields.io/badge/1st_polaris-working-success.svg) ![](https://img.shields.io/badge/2nd_vanila-mic_issues-yellow.svg) ![](https://img.shields.io/badge/2nd_iris-mic_issues-yellow.svg) |
| Battery                     | ![](https://img.shields.io/badge/1st_vanila-working-success.svg) ![](https://img.shields.io/badge/1st_polaris-working-success.svg) ![](https://img.shields.io/badge/2nd_vanila-working-success.svg) ![](https://img.shields.io/badge/2nd_iris-working-success.svg)  |
| Bluetooth                   | ![](https://img.shields.io/badge/1st_vanila-working-success.svg) ![](https://img.shields.io/badge/1st_polaris-working-success.svg) ![](https://img.shields.io/badge/2nd_vanila-working-success.svg) ![](https://img.shields.io/badge/2nd_iris-working-success.svg)  |
| Camera                      | ![](https://img.shields.io/badge/1st_vanila-working-success.svg) ![](https://img.shields.io/badge/1st_polaris-working-success.svg) ![](https://img.shields.io/badge/2nd_vanila-working-success.svg) ![](https://img.shields.io/badge/2nd_iris-working-success.svg)  |
| Intel Graphics              | ![](https://img.shields.io/badge/1st_vanila-working-success.svg) ![](https://img.shields.io/badge/1st_polaris-working-success.svg) ![](https://img.shields.io/badge/2nd_vanila-working-success.svg) ![](https://img.shields.io/badge/2nd_iris-working-success.svg)  |
| AMD Polaris Graphics        | ![](https://img.shields.io/badge/1st_polaris-working-success.svg) |
| Keyboard & Touchpad         | ![](https://img.shields.io/badge/1st_vanila-working-success.svg) ![](https://img.shields.io/badge/1st_polaris-working-success.svg) ![](https://img.shields.io/badge/2nd_vanila-working-success.svg) ![](https://img.shields.io/badge/2nd_iris-working-success.svg)  |
| Trackpoint & Buttons        | ![](https://img.shields.io/badge/1st_vanila-working-success.svg) ![](https://img.shields.io/badge/1st_polaris-working-success.svg) ![](https://img.shields.io/badge/2nd_vanila-working-success.svg) ![](https://img.shields.io/badge/2nd_iris-working-success.svg)  |
| NVMe & Internal SSD         | ![](https://img.shields.io/badge/1st_vanila-working-success.svg) ![](https://img.shields.io/badge/1st_polaris-working-success.svg) ![](https://img.shields.io/badge/2nd_vanila-working-success.svg) ![](https://img.shields.io/badge/2nd_iris-working-success.svg)  |
| Screen                      | ![](https://img.shields.io/badge/1st_vanila-working-success.svg) ![](https://img.shields.io/badge/1st_polaris-working-success.svg) ![](https://img.shields.io/badge/2nd_vanila-working-success.svg) ![](https://img.shields.io/badge/2nd_iris-working-success.svg)  |
| Suspend & Hibernation       | ![](https://img.shields.io/badge/1st_vanila-working-success.svg) [![](https://img.shields.io/badge/1st_polaris-sleep_issues-yellow.svg)](./tweaks/amdgpu-rx640/README.md) ![](https://img.shields.io/badge/2nd_vanila-working-success.svg) ![](https://img.shields.io/badge/2nd_iris-working-success.svg)  |
| WiFi                        | ![](https://img.shields.io/badge/1st_vanila-working-success.svg) ![](https://img.shields.io/badge/1st_polaris-working-success.svg) ![](https://img.shields.io/badge/2nd_vanila-working-success.svg) ![](https://img.shields.io/badge/2nd_iris-working-success.svg)  |
| USB                         | ![](https://img.shields.io/badge/1st_vanila-working-success.svg) ![](https://img.shields.io/badge/1st_polaris-working-success.svg) ![](https://img.shields.io/badge/2nd_vanila-working-success.svg) ![](https://img.shields.io/badge/2nd_iris-working-success.svg)  |
| Hot Keys                    | ![](https://img.shields.io/badge/1st_vanila-partially_working-yellow.svg) ![](https://img.shields.io/badge/1st_polaris-partially_working-yellow.svg) ![](https://img.shields.io/badge/2nd_vanila-partially_working-yellow.svg) ![](https://img.shields.io/badge/2nd_iris-partially_working-yellow.svg)  |
| Fans                        | ![](https://img.shields.io/badge/1st_vanila-working-success.svg) ![](https://img.shields.io/badge/1st_polaris-working-success.svg) ![](https://img.shields.io/badge/2nd_vanila-working-success.svg) ![](https://img.shields.io/badge/2nd_iris-working-success.svg)  |
| Fingerprint Reader          | ![](https://img.shields.io/badge/1st_vanila-not_working-red.svg) ![](https://img.shields.io/badge/1st_polaris-not_working-red.svg) ![](https://img.shields.io/badge/2nd_vanila-not_working-red.svg) ![](https://img.shields.io/badge/2nd_iris-not_working-red.svg) |

### Quick Fixes
Even when Lenovo Thinkpad E14 series are friendly with Linux, there are some tweaks you'll need to do in order make your Linux distro fully compatible with your hardware (check above table). So make sure to see those post installation steps.

- [Enable Trackpoint & Buttons](./tweaks/trackpoint/README.md) : In case your trackpoint is detected by your system but not usable. Also fixes the issue where it just stop working. This problem was found under kernel 5.4 - 5.9.
- [Dedicated AMD GPU](./tweaks/amdgpu-rx640/README.md) : In case you are not able to run specific software with your dedicated AMD GPU. This problem was found on old linux distributions. Anyways make sure to configure your GPU properly.
- [Suspend & Hibernation](./tweaks/suspend-and-hibernation/README.md) : There is an issue with newer BIOS updates and the Thinkpad E14 First-Gen. Check this in case your not able to recover after suspend or hibernation.
- [Intel CPU Throttling](./tweaks/intel-cpu-throttling/README.md) : Performance issues? Check this guide in order to get a better experience with Intel CPUs. Also checkout TLP in order to extend your battery life.
- [Speakers issues in Second Gen](./tweaks/audio/README.md): Fix speakers by disabling the internal mic.


