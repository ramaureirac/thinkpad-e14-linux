# Working with the fingerprint reader

To check the device name of the fingerprint reader
```bash
$ lsusb
```
```
Bus 003 Device 003: ID 10a5:9800 FPC FPC Sensor Controller L:0002 FW:27.26.23.31
```
Another result
```
Bus 003 Device 002: ID 27c6:550a Shenzhen Goodix Technology Co.,Ltd. FingerPrint
```
You can have different controllers depending on the PC model.


## Download Driver
Lenovo officially provides the driver, which can be downloaded from the `Lenovo PC support` website under the `E14 gen 4` section. The driver works with the `E14 gen 5` model and some Ideapad models.

## Driver Installaion

### FingerPrint Driver
First, download the driver from Lenovo PC support. [FPC](https://download.lenovo.com/pccbbs/mobiles/r1slm02w.zip) or [Goodix](https://download.lenovo.com/pccbbs/mobiles/r1slg01w.zip).

Extract the `.zip` file and cd into it directory.

Installation script can be found from [Lenovo forums](https://forums.lenovo.com/t5/Fedora/Fingerprint-reader-FPC-10a5-9800-IdeaBook-15-G4-IPA/m-p/5255485?page=1#6242266)

Here are the step-by-step detailed guides that one can follow, 

#### FPC driver

Edit the `install.sh` file at `FPC_driver_linux_27.26.23.39/install_fpc/install.sh`
```bash
if grep -qE 'ID=fedora' /etc/os-release; then
  sudo cp ./libfpcbep.so /usr/lib64/
  sudo chmod +x /usr/lib64/libfpcbep.so
else
  sudo cp ./libfpcbep.so /usr/lib/x86_64-linux-gnu/
fi;
```
then install by,
```bash
cd FPC_driver_linux_27.26.23.39/install_fpc
chmod +x install.sh
sudo ./install.sh
```

#### libfprint

Now, also edit the `install.sh` file at `FPC_driver_linux_libfprint/install_libfprint/install.sh`
```bash
if grep -qE 'ID=fedora' /etc/os-release; then
  sudo dnf -y install libfprint fprintd fprintd-pam 'dnf-command(versionlock)'
  sudo dnf versionlock add libfprint
  sudo cp -r lib/* /usr/lib/
  sudo cp usr/lib/x86_64-linux-gnu/* /usr/lib64/
  sudo chmod +x /usr/lib64/libfprint-2*
else
  sudo cp -r lib/* /lib/
  sudo cp -r usr/* /usr/
  sudo mkdir -p /var/log/fpc
  #avoid libfprint being modified under apt upgrading
  echo "libfprint-2-2 hold" | sudo dpkg --set-selections
  sudo chmod 755 /usr/lib/x86_64-linux-gnu/libfprint-2.so.2.0.0
fi
echo "Installation completed successfully. You must reboot your system."
```
and, install by

```bash
cd FPC_driver_linux_libfprint/install_libfprint
chmod +x install.sh
sudo ./install.sh
```


For `opensuse-tumbleweed` replace with `if grep -qE 'ID=opensuse-tumbleweed' /etc/os-release; then`
or simply copy the file
```bash
cd FPC_driver_linux_27.26.23.39/install_fpc/
sudo cp ./libfpcbep.so /usr/lib64/
sudo chmod +x /usr/lib64/libfpcbep.so
cd FPC_driver_linux_libfprint/install_libfprint/
sudo cp -r lib/* /usr/lib/
sudo cp usr/lib/x86_64-linux-gnu/* /usr/lib64/
sudo chmod +x /usr/lib64/libfprint-2*
```
and in `Yast` protected the `libfprint-2*` package from `Software Management`

## Configuration
Whether you have the same fingerprint controller or not, this configuration is the same for all drivers.

First, register your fingerprint using kde-plasma or gnome settings.

If you use `fprint` then
```bash
# to enroll
fprintd-enroll
# to verify
fprintd-verify
```
To enable fingerprint authentification for the command line simply run
```bash
sudo pam-auth-update
```
Now, for authetication,

```bash
sudo pam-config --update --fprintd
```

or, for `sddm`, first copy the

```bash
sudo cp /usr/lib/pam.d/sddm /etc/pam.d/sddm
```

and put the lines at the beginning of the file

```
#%PAM-1.0
auth    [success=1 new_authtok_reqd=1 default=ignore]   pam_unix.so try_first_pass likeauth nullok
auth    sufficient      pam_fprintd.so
```
To configure `kde` lockscreen to accept password first and then fingerprint,

```bash
sudo cp /usr/lib/pam.d/kde /etc/pam.d/kde
```

and past the lines at the beginning of the file
```
auth 			sufficient  	pam_unix.so try_first_pass likeauth nullok
auth 			sufficient  	pam_fprintd.so
```

**Reference**

- [Opensuse wiki](https://en.opensuse.org/SDB:Using_fingerprint_authentication)
- [Arch wiki](https://wiki.archlinux.org/title/fprint)
