## TouchpPoint Drivers Officially Working

It seems both ThinkPad E14 and E15 are now officially supported in the latest version of Fedora 34. Other Linux distributions will follow suit soon likely. However, in case you are on a more older distro it is possible that your trackpoint or buttons aren't recognized by your operating system. In order to fix it keep reading this document.

## Thinkpad E14 Enable Trackpoint & Buttons 

Acording to [mimi89999](https://github.com/rodmaureirac/thinkpad-e14-linux/issues/8), just append `options psmouse elantech_smbus=0` in `/etc/modprobe.d/psmouse.conf` file:

    echo "options psmouse elantech_smbus=0" >> /etc/modprobe.d/psmouse.conf
    
Fix should apply on next boot
