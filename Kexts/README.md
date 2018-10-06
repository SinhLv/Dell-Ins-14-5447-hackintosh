# Dell-Ins-14-5447-hackintosh

Assume you replaced your wireless card by DW1707 (AR9565)

How to install kext

add boot-args to clover: -ath9565

open terminal and type:
sudo cp hda-verb /usr/bin

sudo cp -R "kextName".kext /Library/Extensions/

Delete IO80211Family.kext and IO80211Familyv2.kext in S/L/E and install patched IO80211Family.kext with kextWizard.app

sudo kextcache -i /