# rpi3-gaps

I repackaged the .img that comes loaded as Raspbian lite and made the following changes:
- updated/upgraded default packages
- upgraded firmware (sudo rpi-update)
- added 'agent' user (password: agent); added 'agent' to group sudo and sudoers file
- changed 'root' password to root; 'pi' password to pi
- changed hostname to raspbian-rpi
- settings: SSH, en_US (locale, timezone, keyboard, etc.), 1920x1080
- installed packages: raspberrypi-kernel-headers bc git libncurses5-dev libparted-dev alsa-tools libasound2-dev bsdtar lrzip autotools-dev dh-make xutils-dev
