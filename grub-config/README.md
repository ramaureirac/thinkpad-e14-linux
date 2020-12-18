## Grub Config for E14 gen2/gen1

` sudo nano /etc/default/grub`

change the line to this:
`GRUB_CMDLINE_LINUX="rhgb quiet psmouse.elantech_smbus=0"`

then:
`sudo grub2-mkconfig -o /boot/grub2/grub.cfg`
or `sudo update-grub` (ubuntu systems)

`reboot`

### You should now have working trackpoint and buttons.
