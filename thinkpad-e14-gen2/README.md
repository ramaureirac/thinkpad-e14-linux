## Lenovo Thinkpad E14 Second Gen (Intel)

The following document provides an overview about GNU/Linux (kernel 5.10) for the Lenovo Thinkpad E14 (Second-Gen). Please note this info is based on my own experience and it doesn't represent an official support for this machine. If you follow this guide, no one is responsible for any damage to your hardware.

According to Lenovo's web site. There are four base models for the Lenovo Thinkpad E14 (gen2). The AMD Ryzen version, the Intel 11th Gen version, the Intel 11th Gen with dedicated Nvidia Graphics, and the Intel 11th Gen with Intel Iris Xe Integrated Graphics.

To checks if hardware works, all test were done with some Linux Distributions (Ubuntu, Fedora and Arch) To state the obvious: The newer kernel the better.

### Current Status

The checks if hardware works below were done with multiple Linux distributions. To state the obvious: The newer the kernel the better. The information below assumes that you run Linux 5.10 LTS or newer.

| Device                      | Status                                    |
| ----------------------------|-------------------------------------------|
| Audio Input & Output        | ![](https://img.shields.io/badge/2nd_vanila-mic_issues-yellow.svg) ![](https://img.shields.io/badge/2nd_iris-mic_issues-yellow.svg) |
| Battery                     | ![](https://img.shields.io/badge/2nd_vanila-working-success.svg) ![](https://img.shields.io/badge/2nd_iris-working-success.svg)|
| Bluetooth                   | ![](https://img.shields.io/badge/2nd_vanila-working-success.svg) ![](https://img.shields.io/badge/2nd_iris-working-success.svg)|
| Camera                      | ![](https://img.shields.io/badge/2nd_vanila-working-success.svg) ![](https://img.shields.io/badge/2nd_iris-working-success.svg)|
| Intel Graphics              | ![](https://img.shields.io/badge/2nd_vanila-working-success.svg) ![](https://img.shields.io/badge/2nd_iris-working-success.svg) |
| Keyboard & Touchpad         | ![](https://img.shields.io/badge/2nd_vanila-working-success.svg) ![](https://img.shields.io/badge/2nd_iris-working-success.svg)|
| Trackpoint & Buttons        | ![](https://img.shields.io/badge/2nd_vanila-working-success.svg) ![](https://img.shields.io/badge/2nd_iris-working-success.svg)|
| NVMe & Internal SSD         | ![](https://img.shields.io/badge/2nd_vanila-working-success.svg) ![](https://img.shields.io/badge/2nd_iris-working-success.svg)|
| Screen                      | ![](https://img.shields.io/badge/2nd_vanila-working-success.svg) ![](https://img.shields.io/badge/2nd_iris-working-success.svg)|
| Suspend & Hibernation       | ![](https://img.shields.io/badge/2nd_vanila-working-success.svg) ![](https://img.shields.io/badge/2nd_iris-sleep_issues-yellow.svg) |
| WiFi                        | ![](https://img.shields.io/badge/2nd_vanila-working-success.svg) ![](https://img.shields.io/badge/2nd_iris-working-success.svg) |
| USB                         | ![](https://img.shields.io/badge/2nd_vanila-working-success.svg) ![](https://img.shields.io/badge/2nd_iris-working-success.svg) |
| Hot Keys                    | ![](https://img.shields.io/badge/2nd_vanila-partially_working-yellow.svg) ![](https://img.shields.io/badge/2nd_iris-partially_working-yellow.svg) |
| Fans                        | ![](https://img.shields.io/badge/2nd_vanila-working-success.svg) ![](https://img.shields.io/badge/2nd_iris-working-success.svg)  |
| Fingerprint Reader          | ![](https://img.shields.io/badge/2nd_vanila-not_working-red.svg) ![](https://img.shields.io/badge/2nd_iris-not_working-red.svg)  |

### Tested GNU/Linux Distributions

| Distro                      | Status                                    |
| ----------------------------|-------------------------------------------|
| Fedora 34                   | ![](https://img.shields.io/badge/2nd_vanila-working-success.svg) ![](https://img.shields.io/badge/2nd_iris-working-success.svg) |
| Ubuntu 20.10                | ![](https://img.shields.io/badge/2nd_vanila-tweak_required-yellow.svg) ![](https://img.shields.io/badge/2nd_iris-tweak_required-yellow.svg) |
| Arch Linux                  | ![](https://img.shields.io/badge/2nd_vanila-working-success.svg) ![](https://img.shields.io/badge/2nd_iris-working-success.svg) |
| Debian 10                   | ![](https://img.shields.io/badge/2nd_vanila-not_working-red.svg) ![](https://img.shields.io/badge/2nd_iris-not_working-red.svg)  |
| Debian Bullseye             | ![](https://img.shields.io/badge/2nd_vanila-tweak_required-yellow.svg) ![](https://img.shields.io/badge/2nd_iris-tweak_required-yellow.svg) |
