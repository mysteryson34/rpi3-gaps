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

##These instructions are missing important additions and revisions that I hope to make on a later date.##
