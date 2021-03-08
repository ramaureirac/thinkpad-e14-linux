## Thinkpad E14 Enable Trackpoint & Buttons

Not able to use your trackpoint? this guide is for you:


| Model         | Working             |
|---------------|---------------------|
| E1 First Gen  | :heavy_check_mark:  |
| E1 Second Gen | :heavy_check_mark:  |

### New alternative

Acording to [mimi89999](https://github.com/rodmaureirac/thinkpad-e14-linux/issues/8), just append `options psmouse elantech_smbus=0` in `/etc/modprobe.d/psmouse.conf` file:

    echo "options psmouse elantech_smbus=0" >> /etc/modprobe.d/psmouse.conf
    
Fix should apply on next boot

### Old alternative
#### Edit grub config file

First of all you need to open a terminal and edit the */etc/default/grub* file. In this case we will be using *nano*:

    sudo nano /etc/default/grub

Append *psmouse.elantech_smbus=0* at the end of the *GRUB_CMDLINE_LINUX* line. Something like this:

    GRUB_CMDLINE_LINUX="rhgb quiet (...) psmouse.elantech_smbus=0"


#### Rebuild grub

Then make sure to rebuild your grub with the follwing command (Ubuntu):

    sudo update-grub

Grub rebuild for non Ubuntu-based distros (Legacy):

    sudo grub2-mkconfig -o /boot/grub2/grub.cfg

Grub rebuild for non Ubuntu-based distros (EFI):

    sudo grub2-mkconfig -o /boot/efi/EFI/<your-distro>/grub.cfg

#### Restart system

Then you'll need to restart your system:

    reboot

#### You should now have working trackpoint and buttons.
