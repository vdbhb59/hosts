# hosts
Curated host file with various domain blocks.

See "**Source**" below for credits and source list. Lot of hosts are based on my own digging and compatible with almost all kind of adblockers.
___
# Install hblock

```sh
curl -o /tmp/hblock 'https://raw.githubusercontent.com/vdbhb59/hosts/master/hblock' \
  && echo 'aeb47fce80baa1a47c907ab2b1af37de7fe68dff92fd4e7e4a5df075bf5b668f /tmp/hblock' | shasum -c \
  && sudo mv /tmp/hblock /usr/local/bin/hblock \
  && sudo chown 0:0 /usr/local/bin/hblock \
  && sudo chmod 755 /usr/local/bin/hblock
```
___
# Install systemd service and timer units

The following commands will schedule a daily update of the hosts file. See [systemd-timers](https://wiki.archlinux.org/index.php/systemd/Timers) for more information.

```sh
curl -o '/tmp/hblock.#1' 'https://raw.githubusercontent.com/vdbhb59/hosts/master/hblock.{service,timer}' \
  && echo '08b736382cb9dfd39df1207a3e90b068f5325a41dc8254d83fde5d4540ba8b5b /tmp/hblock.service' | shasum -c \
  && echo '87a7ba5067d4c565aca96659b0dce230471a6ba35fbce1d3e9d02b264da4dc38 /tmp/hblock.timer' | shasum -c \
  && sudo mv /tmp/hblock.{service,timer} /etc/systemd/system/ \
  && sudo chown 0:0 /etc/systemd/system/hblock.{service,timer} \
  && sudo chmod 644 /etc/systemd/system/hblock.{service,timer} \
  && sudo systemctl daemon-reload \
  && sudo systemctl enable hblock.timer \
  && sudo systemctl start hblock.timer
```
___
# Modify default options with environment variables

To change the default options instead of modifying the original service it is possible to override its properties.

For example, to have multiple domains on the same line and enable regular expressions in the allow-list, create the file
`/etc/systemd/system/hblock.service.d/override.conf` with the following content:

```
[Service]
Environment=HBLOCK_WRAP=20
Environment=HBLOCK_REGEX=true
```

Then reload the systemd configuration and start the service:

```sh
sudo systemctl daemon-reload
sudo systemctl start hblock.service
```
___
# Check Shasum the actual way
**Organic:**
In terminal run: 

For sha2:
`shasum -a 256 filename/path`

For sha1:<br>
`shasum -a 1 filename/path`

Use your eyeballs and compare by sight the expected hash and the computed hash in the terminal. Eye strain might ensue.

**Artisanal & organic:**
Run the above commands. Copy the resulting shasum with Ctrl + C.
In browser or file use Ctrl + F with your copied shasum; if you find a match, congrats your file is fine! If no match, your file might have been altered or tampered with. 

**Inorganic, man-made:**
Use shasum check command. Runs diff and prints results in terminal.

In terminal run:<br>
`echo 'your_expected_shasum_here_followed_by_a_space *name_of_file_to_check_after_asterisk' | shasum -c`

References:
---
[Alexis La Porte](https://gist.github.com/aklap/3c66f1991909f448e5ff)

___
## Supported Operating Systems

***Android:*** For non-rooted devices, these host files can be used with [`Tracker Control`](https://f-droid.org/en/packages/net.kollnig.missioncontrol.fdroid/), [`DNS66`](https://f-droid.org/en/packages/org.jak_linux.dns66/), [`Blokada`](https://f-droid.org/en/packages/org.blokada.alarm/), [`Personal DNS Filter`](https://www.zenz-solutions.de/personaldnsfilter/) or [`Nebulo`](https://nebulo.app/source).
The above softwares are free and open-source ad-blockers.

For rooted devices, one can replace the default **hosts** file with the file of choice from here, after renaming the choice file to "**hosts**". Permissions should be **rw-r--r--** / **644**.

Otherwise, if one does not wish to add it manually, one can use this host file with [`AdAway`](https://f-droid.org/en/packages/org.adaway/), a free and open-source ad-blocker for Android.

***Linux:*** An open-source host file manager called [`hBlock`](https://github.com/hectorm/hBlock).

***Mac OS:*** These host files can be used with [`gasmask`](https://github.com/2ndalpha/gasmask).

***Windows:*** Users for Windows would find it easy to use with [`Hostman`](http://www.abelhadigital.com/hostsman/), a software to manage host file.

In case the above is not working, you can try one of the following as well:

[`SwitchHosts`](https://oldj.github.io/SwitchHosts) or [`HostsFileEditor`](https://github.com/scottlerch/HostsFileEditor)

Use installer [`hostsinstaller`](https://github.com/vdbhb59/hosts/master/hosts_install_win.bat) with administrative rights in Windows.
___
**How to disable DNS CACHE services on Windows?**

1) Hit Win+R & type `regedit` & press enter.

2) Go to `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\services\Dnscache`, and locate the "Start" registry key. Now change its value from 2 (Automatic) to 4 (Disabled)

3) Restart computer once & now change your host file with bigger SIZE.
___
## Usage guide

### TrackerControl [`TC`](https://f-droid.org/en/packages/net.kollnig.missioncontrol.fdroid/)
Open TC > Top Right "3 Dots Drop Down" > Settings > Advanced options > "Hosts file URL" > Click and then copy paste the below hosts file URL.
Then click OK to save the URL and then click "update hosts file".
```
https://raw.githubusercontent.com/vdbhb59/hosts/master/hosts
```

### Blokada
Open Blokada > navigate to Hosts List > Click + button and then copy paste the below hosts file URL.
Then press the Shield icon to activate.
```
https://raw.githubusercontent.com/vdbhb59/hosts/master/hosts
```

### DNS66
Open DNS66 > swipe to Hosts > Click + button and then copy paste the below hosts file URL.
Then press the refresh icon on the top and press the start button.
```
https://raw.githubusercontent.com/vdbhb59/hosts/master/hosts
```

### Adaway
Open Adaway > go to Host Source > Click + button and then copy paste the below hosts file URL.
Then Click enable ad blocking from the home menu.
```
https://raw.githubusercontent.com/vdbhb59/hosts/master/hosts
```

### DNS Filter
Open DNS Filter > Tap on Advanced Settings > Tap on Configure Filter Update > Create a new filter by tapping on the Pencil icon > Copy paste the below hosts file URL > Tap on Active circle there > Tap on the (✔️) icon > Tap on Configure filter update to hide the menu > Tap on Advanced Settings > Tap on Restart
```
https://raw.githubusercontent.com/vdbhb59/hosts/master/hosts
```

## Recommended Whitelist

- __Facebook main app__
- __Facebook Lite Messenger__

## Recommended Apps
For those who still are hardcore f*c*book (lol) users, you can try Frost from F-Droid.
Frost for Facebook (A fast and extensive third party wrapper for Facebook.)
```
https://f-droid.org/app/com.pitchedapps.frost
```
For YT users, use NewPipe. It is fully open sourced.
```
https://f-droid.org/app/org.schabi.newpipe
```
___
## Sources

- __Source lists for my hosts files:__

[No-Amazon](https://github.com/nickspaargaren/no-amazon) | [Hectorm](https://hblock.molinero.dev/hosts) | [Hosts Vietnam](https://raw.githubusercontent.com/bigdargon/hostsVN/master/hosts) | [Steven Black](https://raw.githubusercontent.com/StevenBlack/hosts/master/alternates/fakenews-gambling-porn-social/hosts) | [PolishFiltersTeam](https://raw.githubusercontent.com/PolishFiltersTeam/KADhosts/master/KADhosts.txt) | [MetaMask](https://raw.githubusercontent.com/MetaMask/eth-phishing-detect/master/src/hosts.txt) | [Bad-Boyz](https://raw.githubusercontent.com/mitchellkrogza/Badd-Boyz-Hosts/master/hosts) | [AnudeepND](https://raw.githubusercontent.com/anudeepND/blacklist/master/CoinMiner.txt) | [Badmojr](https://badmojr.github.io/1Hosts/Pro/hosts.txt) | [Easy List](https://easylist.to/easylist/easylist.txt) | [Easy List-Privacy](https://easylist.to/easylist/easyprivacy.txt) | [Easy List-Cookie](https://easylist-downloads.adblockplus.org/easylist-cookie.txt) | [Yous](https://raw.githubusercontent.com/yous/YousList/master/hosts.txt) | [YHosts](https://raw.githubusercontent.com/vokins/yhosts/master/hosts.txt) | [GBA-Samsung](https://raw.githubusercontent.com/jerryn70/GoodbyeAds/master/Extension/GoodbyeAds-Samsung-AdBlock.txt) | [GBA-YT](https://raw.githubusercontent.com/jerryn70/GoodbyeAds/master/Extension/GoodbyeAds-YouTube-AdBlock.txt) | [GBA](https://raw.githubusercontent.com/jerryn70/GoodbyeAds/master/Hosts/GoodbyeAds.txt) | [GBA-Xiaomi](https://raw.githubusercontent.com/jerryn70/GoodbyeAds/master/Extension/GoodbyeAds-Xiaomi-Extension.txt) | [GBA-Le-Eco](https://raw.githubusercontent.com/jerryn70/GoodbyeAds/master/Extension/GoodbyeAds-LeEco-Extension.txt) | [Gloeyisk](https://raw.githubusercontent.com/gloeyisk/SystemlessHosts/master/system/etc/hosts) | [Idoo](https://gist.githubusercontent.com/idoo/dc809ae93a3da54fb24c92185dfffffa/raw/d19b6edd63cbd9154d20dce782198920c3bb770e/hosts-yt-ads)
___
- __Resultant Host File:__

[`hosts`](https://raw.githubusercontent.com/vdbhb59/hosts/master/hosts)
___
- __Credits:__
[No-Amazon](https://github.com/nickspaargaren/no-amazon) |
[Easylist > Easylist](https://easylist.to/index.html) |
[HBlock > Héctor Molinero Fernández](https://github.com/hectorm) |
[HostsVN > Bigdragon](https://github.com/bigdargon) |
[Steven Black > Steven Black](https://github.com/StevenBlack) |
[GoodByeAds > Jerryn70](https://github.com/jerryn70) |
[KAD Hosts > PolishFiltersTeam](https://github.com/PolishFiltersTeam) |
[Ethereum Phishing > MetaMask](https://github.com/MetaMask) |
[Badd-Boyz-Hosts > Mitchell Krog](https://github.com/mitchellkrogza) |
[CoinMiner > Anudeep](https://github.com/anudeepND) |
[Pro Hosts (BadMojr) > Imre Kristoffer Eilertsen (Dandelion Sprout)](https://github.com/DandelionSprout) |
[Master Hosts > Chayoung You](https://github.com/Yous) |
[Master Hosts > Vokins](https://github.com/vokins) |
[Systemless Hosts (Porn+FakeNews+Gambling) > Gilang Iskandar (Gloeyisk)](https://github.com/gloeyisk) -- May be removed soon, if not updated any longer.. |
[No-Google > Nick Spaargaren](https://github.com/nickspaargaren/no-google) (Thanks Evan (785172845)(Telegram) for pointing this out) |
[YouTube Hosts > Ivan Verevkin](https://github.com/idoo)

___
## License

Content of the **hosts** is licensed under a [MIT License](https://github.com/vdbhb59/hosts/blob/master/LICENSE).
