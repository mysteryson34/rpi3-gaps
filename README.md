# rpi3-gaps

I repackaged the .img that comes loaded as Raspbian lite and made the following changes:
- updated/upgraded default packages
- upgraded firmware (sudo rpi-update)
- added 'agent' user (password: agent); added 'agent' to group sudo and sudoers file
- changed 'root' password to root; removed 'pi' user
- changed hostname to raspbian-rpi
- settings: SSH, en_US (locale, timezone, keyboard, etc.), 1920x1080
- installed additional packages:

		zsh nmap bridge-utils neofetch lshw raspberrypi-kernel-headers bc git ranger libncurses5-dev libparted-dev alsa-tools libasound2-dev bsdtar lrzip autotools-dev dh-make xutils-dev

After flashing the image to a larger capacity SD card, be sure to use raspi-config to expand the filesystem and restart before continuing.

*These instructions are missing important additions and revisions that I hope to make on a later date.*

		sudo apt-get install --no-install-recommends xserver-xorg -y
		sudo apt-get install --no-install-recommends lightdm -y
		sudo apt-get install gvfs i3 -y
		sudo apt-get install libpthread-stubs0-dev libxcb-composite0-dev libxcb-damage0-dev libxcb-dpms0-dev libxcb-dri2-0-dev libxcb-dri3-dev libxcb-ewmh-dev libxcb-glx0-dev libxcb-image0-dev libxcb-present-dev libxcb-record0-dev libxcb-render-util0-dev libxcb-render0-dev libxcb-res0-dev libxcb-screensaver0-dev libxcb-shape0-dev libxcb-shm0-dev libxcb-sync-dev libxcb-xf86dri0-dev libxcb-xfixes0-dev libxcb-xtest0-dev libxcb-xv0-dev libxcb-xvmc0-dev libxcb-keysyms1-dev libpango1.0-dev libxcb-util0-dev xcb libxcb1-dev libxcb-icccm4-dev libyajl-dev libev-dev libxcb-xkb-dev libxcb-cursor-dev libxkbcommon-dev libxcb-xinerama0-dev libxkbcommon-x11-dev libstartup-notification0-dev libxcb-randr0-dev libxcb-xrm0 libxcb-xrm-dev -y
		cd /tmp && git clone https://github.com/Airblader/xcb-util-xrm && cd xcb-util-xrm && git submodule update --init && ./autogen.sh --prefix=/usr && make && sudo make install
		cd /tmp && git clone https://www.github.com/Airblader/i3 i3-gaps && cd i3-gaps && autoreconf --force --install && rm -rf build/ && mkdir -p build && cd build/ && ../configure --prefix=/usr --sysconfdir=/etc --disable-sanitizers && make && sudo make install

If ~/.config/i3/ does not exist, use mkdir to create both folders.

		cp /etc/i3/config ~/.i3/config

At this point, i3-gaps is installed. Everything from here on is in regards to my own personal method of customizing the user interface.
