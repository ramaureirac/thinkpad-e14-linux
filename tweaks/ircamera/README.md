## IR Camera and Howdy

Some Lenove ThinkPad models include an IR Camera for Windows Hello Authentication, this feature has been reimplemented for GNU/Linux using [Howdy](https://github.com/boltgolt/howdy) and [EmixamPP](https://github.com/EmixamPP/linux-enable-ir-emitter) script for enable IR Camera, so if you wanna use this authentication method make shure to enable your IR Camera properly.

## Enable IR Camera

First of all install howdy

    # for ubuntu
    sudo add-apt-repository ppa:boltgolt/howdy
    sudo apt update && sudo apt install howdy

    # for fedora
    sudo dnf copr enable luya/howdy
    sudo dnf install howdy

Then install EmixamPP script for enabling IR Camera

    # for ubuntu and others:
    git clone https://github.com/EmixamPP/linux-enable-ir-emitter.git
    cd linux-enable-ir-emitter
    sudo bash installer.sh install

    # for fedora
    sudo dnf copr enable emixampp/linux-enable-ir-emitter
    sudo dnf --refresh install linux-enable-ir-emitter

Restart and Howdy should be working correctly

