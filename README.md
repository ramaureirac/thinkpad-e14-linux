## Current State of GNU/Linux on Lenovo Thinkpad E14 (First-Gen)

The following repository provides an overview about Linux support for Lenovo Thinkpad E14 (it should work with E15 as well). Please note this documents are based on my own experience and it doesn't means an official support for this models. If you follow this guide, no one is responsible for any damage to your hardware.

According to Lenovo's documentation there are different models of the Thinkpad E14 based on the Wi-Fi card ,wich can be a Realtek RTL8822CE or an Intel Wireless AC9560/AX201. A part of that, all models are nearly identical except for the option to add an AMD RX640 as dedicated graphics card. 

Theres also a second-gen Thinkpad E14 wich includes a AMD Ryzen 4000 series CPU insted of the Intel 10th gen. This suppose a better performance and battery life. Also, as far as I know, theres only a Realtek RTL8822CE available as a Wi-Fi adapter and there are no dedicated GPUs for this model.

To checks if hardware works, all test were done with some Linux Distributions (Ubuntu, Fedora and Arch) To state the obvious: The newer kernel the better. However, I personally suggest you to keep the current LTS version (Linux 5.4)


### Contribution

If you want to contribute to get Linux running smoothly on the Lenovo Thinkpad E14 series, report all findings on how to get devices working as pull requests! All help is appreciated.

### Current Status (First-Gen)

The table shows up Linux 5.4+ support status for each device on this laptop series. Note that circle means it works but need extra tweak or configuration.

| Device                            | Thinkpad E14 First Gen              | Thinkpad E14 Second Gen   |
|-----------------------------------|-------------------------------------|---------------------------|
| Audio Input & Output              | :heavy_check_mark:                  | :heavy_check_mark:        |
| Battery                           | :heavy_check_mark:                  | :heavy_check_mark:        | 
| Bluetooth                         | :heavy_check_mark:                  | :heavy_check_mark:        |
| Camera                            | :heavy_check_mark:                  | :heavy_check_mark:        |
| Graphics Card (Intel)             | :heavy_check_mark:                  | *Not available*           |
| Graphics Card (AMD)               | :o:                                 | :o:                       |
| Keyboard, Touchpad and Trackpoint | :o:                                 | :x:                       |
| NVMe & Internal SSD               | :heavy_check_mark:                  | :heavy_check_mark:        |
| Screen                            | :heavy_check_mark:                  | :heavy_check_mark:        |
| Suspend & Hibernation             | :o:                                 | :x:                       |
| Wi-Fi                             | :heavy_check_mark:                  | :heavy_check_mark:        |
| USB                               | :heavy_check_mark:                  | :heavy_check_mark:        |
| Fingerprint Reader                | :x:                                 | :x:                       |
| Fn Hot Keys                       | :heavy_check_mark:                  | :x:                       |
| Fans                              | :heavy_check_mark:                  | :heavy_check_mark:        |
    
You can find more details of every model on their folder
