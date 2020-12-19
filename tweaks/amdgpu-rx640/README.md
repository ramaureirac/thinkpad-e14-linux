## AMD Dedicated GPU RX640

There are some models wich include a dedicated AMD Graphic card. This model should work out of the box on newer Linux distirbutions. However, in case your are not able to run software with your dedicated graphic card check this guide.

| Model                             | Working            |
|-----------------------------------|--------------------|
| Thinkpad E14 + AMD RX640          | :heavy_check_mark: |
| Thinkpad E14 + AMD 620            | :heavy_check_mark: | 


#### Install AMDGPU driver

For some reason your distribution could have install a wrong driver (ati-driver) for your graphic card. So first of all let's make sure to install the right one by using the following command:

    # install on fedora:
    sudo dnf install xorg-x11-drv-amdgpu -y
    
    # install on debian/ubuntu:
    sudo apt install -y libdrm-amdgpu1 xserver-xorg-video-amdgpu
    
Once it is done, you cand uninstall the old drivers by typping:

    # uninstall old ubuntu/debian drivers (ati + intel):
    sudo apt remove xserver-xorg-video-ati
    sudo apt remove xserver-xorg-video-intel
    
    # uninstall old fedora drivers (ati + intel):
    sudo dnf remove xorg-x11-drv-intel 
    sudo dnf remove xorg-drv-x11-ati
    
#### Tweak your AMD GPU with CoreCtrl

CoreCtrl it's an utility for overclocking and create custom profiles for your graphic card. Now it's important to know that this laptops are not design for playing games. However you still are able to run some demanding games with your graphic card. But first keep in mind to setup your game profile with this utlity. So first you'll need to install it.

    # install corectrl on ubuntu:
    sudo add-apt-repository ppa:ernstp/mesarc
    sudo apt-get update
    sudo apt-get install -y corectrl
    
    # instal corectrl on fedora:
    sudo dnf install -y corectrl
    
Once CoreCtrl is installed make sure to append *amdgpu.ppfeaturemask=0xffffffff* on your grub configuration file. I'll be using *nano* on this process. So first, open up your grub configuration file.
 
    sudo nano /etc/default/grub
    
Now, append the line at the end of *GRUB_CMDLINE_LINUX_DEFAULT*

    GRUB_CMDLINE_LINUX_DEFAULT="<other_params>... amdgpu.ppfeaturemask=0xffffffff"
    
Finally restart your device:

    reboot
    
#### Set a gamming profile

For some reason the default profile enables up to 25W for your dedicated GPU wich is too much and maybe you could make irreversilbe damage on your hardware. Also it will overheat reaching up to 85°C. So make sure to set power limit at 18. On this value it will work fine and you will even play some demanding games like Rise of the Tomb Raider at 720@30fps.

![](https://github.com/rodmaureirac/thinkpad-e14-linux/tree/main/tweaks/amdgpu-rx640/corectrl-rx640.png)

 

    
