## Configure Audio on ThinkPad E14 Gen 2

According to [Barabazs](https://github.com/rodmaureirac/thinkpad-e14-linux/issues/9) it seems some second gen laptops are having issues with external speakers. We actually do
not know why this happens, however Barabazs found a solution by disabling the internal mic. In order to do apply this patch:

### By edditing GRUB

Open your favorite editor and append this line `snd_hda_intel.dmic_detect=0` inside the `GRUB_CMDLINE_LINUX_DEFAULT` entry on `/etc/default/grub` config file

    GRUB_CMDLINE_LINUX_DEFAULT="quiet splash ... snd_hda_intel.dmic_detect=0"
    
Then rebuild your GRUB and restart your machine

    sudo update-grub && reboot
    
#### Your speakes should be working

