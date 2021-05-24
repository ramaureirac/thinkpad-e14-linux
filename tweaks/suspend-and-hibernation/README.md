## Thinkpad E14 (First-Gen) Suspend & Hbernation

When I recived my Thinkpad E14 (first-gen) it arrives with BIOS v1.09 which for some reason has troubles with suspension (black screen). In order to fix this issue you'll have to apply a BIOS downgrade. In case you don't know how check this guide.

### Download compatible BIOS

From [Lenovo's Support Center](https://pcsupport.lenovo.com/us/en/products/laptops-and-netbooks/thinkpad-edge-laptops/thinkpad-e14-type-20ra-20rb/downloads/DS541516) download any ECP 1.04 BIOS. I personally suggest you [BIOS v1.06](https://download.lenovo.com/pccbbs/mobiles/r16uj03wd.iso). This ISO file should be flashed inside an USB Stick. In my case I use [Balena Etcher](https://www.balena.io/etcher/) which has a very friendly user interface. Note: Etcher will say our ISO file is not valid, just ignore this warning.

![](./etcher.png?raw=true)

### Disable Rollback BIOS

Default BIOS configuration present some kind of rollback protection (which does not allow us to apply the downgrade). However is super easy to disable it. Just go inside *Security*, then *UEFI BIOS Update Options* and uncheck *Secure RollBack Protection*. Here is my configuration as example

![](./bios-settings.jpg?raw=true)

Now save changes and reboot your machine.

Note: If you boot Windows, it will download a newer BIOS version automatically, so make sure to diable *Windows UEFI Firmware Update* if you are going for a dual-boot

### Boot from USB

Now, you just need to boot from your USB stick (where you install your ISO file). Installation is super simple and it should take up to 5 minutes.

![](./bios-update.jpg?raw=true)

#### Now you should be able to recover from suspension & hibernation
