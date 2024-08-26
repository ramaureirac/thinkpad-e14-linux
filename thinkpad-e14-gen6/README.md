## Lenovo Thinkpad E14 Sixth Gen (AMD)

The current Thinkpad E14 Gen 6 AMD version supports Gnu/Linux out of the box. The fingerprint reader needs a driver from the vendor, which is now officially provided by Lenovo support.

There are issues waking up from hybernation.

The fingerprint reader was not set up out of the box. The installation guide and configuration of the fingerprint reader, follow the guide at `tweaks/fingerprint/README.md`.

Face authentification works upon installing [`howdy`](https://github.com/boltgolt/howdy).

The analog mic input did not work out of the box. Quick fix was enabling the unconnected pins using `alsa-tools-gui` and `hdjackretask` and installing the boot override, see [here](https://askubuntu.com/questions/897437/my-microphone-is-not-working?noredirect=1&lq=1).

### Current Status

The information below assumes that you run Linux `6.8 LTS or newer`.

| Device                      | Status                                    |
| ----------------------------|-------------------------------------------|
| Audio Input & Output        | ![](https://img.shields.io/badge/6th_ryzen-mic_issues-yellow)  |
| Battery                     | ![](https://img.shields.io/badge/6th_ryzen-working-success)  |
| Bluetooth                   | ![](https://img.shields.io/badge/6th_ryzen-working-success)  |
| Camera                      | ![](https://img.shields.io/badge/6th_ryzen-working-success)  |
| AMD Radeon Graphics         | ![](https://img.shields.io/badge/6th_ryzen-working-success)  |
| Keyboard & Touchpad         | ![](https://img.shields.io/badge/6th_ryzen-working-success)  |
| Trackpoint & Buttons        | ![](https://img.shields.io/badge/6th_ryzen-working-success)  |
| NVMe & Internal SSD         | ![](https://img.shields.io/badge/6th_ryzen-working-success)  |
| Screen                      | ![](https://img.shields.io/badge/6th_ryzen-working-success)  |
| Suspend & Hibernation       | ![](https://img.shields.io/badge/6th_ryzen-partially_working-yellow)  |
| WiFi                        | ![](https://img.shields.io/badge/6th_ryzen-working-success)  |
| USB                         | ![](https://img.shields.io/badge/6th_ryzen-working-success)  |
| Hot Keys                    | ![](https://img.shields.io/badge/6th_ryzen-working-success)  |
| Fans                        | ![](https://img.shields.io/badge/6th_ryzen-working-success)  |
| Fingerprint Reader          | ![](https://img.shields.io/badge/6th_ryzen-working-success)  |

### Tested GNU/Linux Distributions

| Distro                      | Status                                                      |
| ----------------------------|-------------------------------------------------------------|
| Ubuntu 22.04                | ![](https://img.shields.io/badge/6th_ryzen-working-success) |

Other Linux distro (Archlinux, Fedora, Ubuntu, etc.) should also work out of the box.
