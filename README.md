Asterisk-Allstar-for-Arch-odroid
============================

ArchLinux package for Allstar (https://allstarlink.org) on the Odroid X,X2,X3,U or U2

Either download the asterisk-allstar-pi-0.1.0.0-1505-armv7h.pkg.tar.xz package or build you own using "makepkg".

Due to upgrades to pacman (4.2) you need to load using "pacman -U --force asterisk-allstar-odroid-0.1.0.0-1505-armv6h.pkg.tar.xz" at the moment.

Must load the "dahdi-linux-allstar-odroid" package (from this repository) beforehand as it is a dependency for this package and this must be created using the makepkg command

Asterisk should automatically start after the package install (and on reboot), this can be checked by running "asterisk -r".
