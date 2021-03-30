# Thinkpad E14 First Gen (Polaris)

| Device        | Hardware                                                                      |
|---------------|-------------------------------------------------------------------------------|
| CPU           | Intel Core i3 10th Gen, Intel Core i5 10th Gen, Intel Core i7 10th Gen        |
| GPU           | Intel UHD Graphics G1 + AMD Radeon RX640 2GB GDDR5, AMD Radeon 620 GDDR5 2GB  |
| RAM           | Up to 16GB 2666Mhz                                                            |
| WIFI          | Intel Adapter AC9560, Intel Adapter AX201                                     |
| AUDIO         | Dual Speaker 2W                                                               |

### Known issues

- [Enable Trackpoint & Buttons](../tweaks/trackpoint/README.md) : In case you cannot use the trackpoint and its respective buttons, we recommend you to read this small guide to enable them. This problem should be solved in kernel versions after 5.10.
- [Suspend & Hibernation](../tweaks/suspend-and-hibernation/README.md) : There is an issue with newer BIOS updates and the Thinkpad E14 First-Gen. Check this in case your not able to recover after suspend or hibernation.
- [Dedicated AMD GPU](../tweaks/amdgpu-rx640/README.md) : In case you are not able to run specific software with your dedicated AMD GPU. This problem was found on old linux distributions. Anyways make sure to configure your GPU properly.
- [Intel CPU Throttling](../tweaks/intel-cpu-throttling/README.md) : Performance issues? Check this guide in order to get a better experience with Intel CPUs. Also checkout TLP in order to extend your battery life.
