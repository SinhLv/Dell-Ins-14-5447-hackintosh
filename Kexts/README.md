# Dell-Ins-14-5447-hackintosh

Assume you replaced your wireless card by DW1820A (BCM94350ZAE ngff)

How to install kext:
Open Terminal and navigate to this current folder.

sudo cp -R "kextName".kext /Library/Extensions

sudo cp hda-verb /usr/bin

sudo kextcache -i /