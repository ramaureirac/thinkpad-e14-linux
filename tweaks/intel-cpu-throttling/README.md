## Intel 10th CPU Throttling

According to [erpalma](https://github.com/erpalma/throttled) there are some thermal throttling issues with Intel CPUS where the power limit is forced to a value of 44 W (29 W on battery) and the temperature trip point to 95 'C (85 'C on battery). This thermal problems could give you some kind of *laggy* animations under GNOME Desktop. 

#### Installing ErPalma's Fix

In order to fix this issue remove thermald

    # ubuntu
    sudo apt remove thermald -y
    
    # fedora
    sudo dnf remove thermald -y
    
Now install throttled

    # ubuntu
    sudo apt install git build-essential python3-dev libdbus-glib-1-dev libgirepository1.0-dev libcairo2-dev python3-venv python3-wheel
    git clone https://github.com/erpalma/throttled.git
    sudo ./throttled/install.sh
    
    # fedora
    sudo dnf copr enable abn/throttled
    sudo dnf install -y throttled
    sudo systemctl enable --now throttled
    
##### Now restart your system and you should get a better performance

