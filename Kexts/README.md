# Dell-Ins-14-5447-hackintosh

Assume you replaced your wireless card by DW1820A (BCM94350ZAE ngff)

How to install kext:
Open Terminal and navigate to this current folder.

sudo cp -R "kextName".kext /Library/Extensions/
(You use * instead of kextName to batch copy all kext to LE)

sudo kextcache -i /

sudo cp -R hda-verb /usr/bin
sudo cp -R Jack\ fix /usr/bin

WARNING: No update CodecCommander cuz specific Infi.plist for ALC255
If updated, re-edit Info.plist by adding this to Default key

					<key>Custom Commands</key>
					<array>
						<dict>
							<key>Command</key>
							<data>
							AZcHJQ==
							</data>
							<key>Comment</key>
							<string>0x19 SET_PIN_WIDGET_CONTROL 0x25</string>
							<key>On Init</key>
							<true/>
							<key>On Sleep</key>
							<false/>
							<key>On Wake</key>
							<true/>
						</dict>
						<dict>
							<key>Command</key>
							<data>
							AhcIgw==
							</data>
							<key>Comment</key>
							<string>0x21 SET_UNSOLICITED_ENABLE 0x83</string>
							<key>On Init</key>
							<true/>
							<key>On Sleep</key>
							<false/>
							<key>On Wake</key>
							<true/>
						</dict>
					</array>
					<key>Perform Reset</key>
					<false/>
					<key>Send Delay</key>
					<integer>10</integer>
					<key>Sleep Nodes</key>
					<false/>

Which is automatic triggered by CodecCommander for this terminal command:

hda-verb 0x19 SET_PIN_WIDGET_CONTROL 0x25
hda-verb 0x21 SET_UNSOLICITED_ENABLE 0x83