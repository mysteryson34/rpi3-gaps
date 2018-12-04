# rpi3-gaps

I repackaged the .img that comes loaded as Raspbian lite and made the following changes:
- updated/upgraded default packages
- upgraded firmware (sudo rpi-update)
- added 'agent' user (password: agent); added 'agent' to group sudo and sudoers file
- changed 'root' password to root; 'pi' password to pi
