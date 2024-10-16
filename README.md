# hosts
Curated hosts file with various domain blocks.

See ["**Source**"](https://github.com/vdbhb59/hosts#sources) below for credits and source list. Lot of hosts are based on my own digging and compatible with almost all kind of adblockers.

Use ["**this batch file**"](https://flossboxin.org.in/scripts/hosts_install_win.bat) as the latest shell script for Windows.

This readme is cosmetically-duplicated in my [parallel world](https://host.flossboxin.org.in).

___
# Nightly/Daily builds

* Daily builds of the hosts file is now implemented and can be directly found [here](https://hosts.flossboxin.org.in).
* Thanks to [Ushma](https://github.com/ushmashah8805) for the squashing, coding and nightly implementation. :)

___
# Install hblock
Thanks to [Héctor Molinero Fernández](https://github.com/hectorm/hblock/blob/master/hblock) for his scriptures.

```sh
curl -o /tmp/hblock 'https://raw.githubusercontent.com/vdbhb59/hosts/master/hblock' \
&& echo 'AD2D8EB91D914BD1FB00174F2434A97471A01297  /tmp/hblock' | shasum -c \
&& sudo mv /tmp/hblock /usr/local/bin/hblock \
&& sudo chown 0:0 /usr/local/bin/hblock \
&& sudo chmod 755 /usr/local/bin/hblock
```
___
# Install systemd service and timer units

The following commands will schedule a daily update of the hosts file. See [systemd-timers](https://wiki.archlinux.org/index.php/systemd/Timers) for more information.

```sh
curl -o '/tmp/hblock.#1' 'https://raw.githubusercontent.com/vdbhb59/hosts/master/hblock.{service,timer}' \
  && echo '08b736382cb9dfd39df1207a3e90b068f5325a41dc8254d83fde5d4540ba8b5b  /tmp/hblock.service' | shasum -c \
  && echo '87a7ba5067d4c565aca96659b0dce230471a6ba35fbce1d3e9d02b264da4dc38  /tmp/hblock.timer' | shasum -c \
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
(Thanks [Alexis La Porte](https://gist.github.com/aklap/3c66f1991909f448e5ff) for this.)
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

___
## Check hash algorithms: "MD2 MD4 MD5 SHA1 SHA256 SHA384 SHA512" via command prompt in Windows:

For default (sha1):
`certUtil -hashfile hosts`

Place the algorithm you wish to check after the filename:
`certUtil -hashfile hosts MD2`

`certutil -hashfile hosts SHA256`

___
## Supported Operating Systems

***Android:*** For non-rooted devices, these host files can be used with [`Virtual Hosts`](https://f-droid.org/en/packages/com.github.xfalcon.vhosts/), [`Tracker Control`](https://f-droid.org/en/packages/net.kollnig.missioncontrol.fdroid/), [`DNS66`](https://f-droid.org/en/packages/org.jak_linux.dns66/), [`Blokada`](https://f-droid.org/en/packages/org.blokada.alarm/), [`Personal DNS Filter`](https://www.zenz-solutions.de/personaldnsfilter/) or [`Nebulo`](https://nebulo.app/source).
The above softwares are free and open-source ad-blockers.

For rooted devices, one can replace the default **hosts** file with the file of choice from here, after renaming the choice file to "**hosts**". Permissions should be **rw-r--r--** / **644**.

Otherwise, if one does not wish to add it manually, one can use this host file with [`AdAway`](https://f-droid.org/en/packages/org.adaway/), a free and open-source ad-blocker for Android.

***Linux:*** An open-source host file manager called [`hBlock`](https://github.com/vdbhb59/hosts/blob/master/hblock).

***Mac OS:*** These host files can be used with [`gasmask`](https://github.com/2ndalpha/gasmask).

***Windows:*** Users for Windows would find it easy to use with [`Hostman`](http://www.abelhadigital.com/hostsman/), a software to manage host file.

In case the above is not working, you can try one of the following as well:

[`SwitchHosts`](https://oldj.github.io/SwitchHosts) or [`HostsFileEditor`](https://github.com/scottlerch/HostsFileEditor)

Use installer [`hostsinstaller`](https://github.com/vdbhb59/hosts/master/hosts_install_win.bat) with administrative rights in Windows.

Use [`Optimizer for Windows`](https://github.com/hellzerg/optimizer/releases) (use Hosts option > Advanced editor function), the finest Windows Optimizer with/without administrative rights in Windows.

___
**How to disable DNS CACHE services on Windows?**

1) Hit Win+R & type `regedit` & press enter.

2) Go to `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\services\Dnscache`, and locate the "Start" registry key. Now change its value from 2 (Automatic) to 4 (Disabled)

3) Restart computer once & now change your host file with bigger SIZE.

___
## Usage guide

### Virual Hosts
Launch Virtual Hosts > Click on the + (plus) sign at the bottom right of the screen > Click settings (gear) icon > Under "set net hosts url", click the "remote hosts url" > A new pop-up will open > Copy paste the below hosts file URL > Click OK > It will Show Downloading > Success (will list the number of hosts entries > Click back & done.
```
https://hosts.flossboxin.org.in/files/hosts
```

### TrackerControl [`TC`](https://f-droid.org/en/packages/net.kollnig.missioncontrol.fdroid/)
Launch TC > Top Right "3 Dots Drop Down" > Settings > Advanced options > "Hosts file URL" > Click and then copy paste the below hosts file URL.
Then click OK to save the URL and then click "update hosts file".
```
https://hosts.flossboxin.org.in/files/hosts
```

### Blokada
Open Blokada > navigate to Hosts List > Click + button and then copy paste the below hosts file URL.
Then press the Shield icon to activate.
```
https://hosts.flossboxin.org.in/files/hosts
```

### DNS66
Open DNS66 > swipe to Hosts > Click + button and then copy paste the below hosts file URL.
Then press the refresh icon on the top and press the start button.
```
https://hosts.flossboxin.org.in/files/hosts
```

### Adaway
Open Adaway > go to Host Source > Click + button and then copy paste the below hosts file URL.
Then Click enable ad blocking from the home menu.
```
https://hosts.flossboxin.org.in/files/hosts
```

### DNS Filter
Open DNS Filter > Tap on Advanced Settings > Tap on Configure Filter Update > Create a new filter by tapping on the Pencil icon > Copy paste the below hosts file URL > Tap on Active circle there > Tap on the (✔️) icon > Tap on Configure filter update to hide the menu > Tap on Advanced Settings > Tap on Restart
```
https://hosts.flossboxin.org.in/files/hosts
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
For YT users, use [NewPipe](https://github.com/TeamNewPipe/NewPipe) / [SkyTube](https://github.com/SkyTubeTeam/SkyTube) / [FreeTubeApp](https://github.com/FreeTubeApp/FreeTube). These are fully open sourced.
```
https://f-droid.org/app/org.schabi.newpipe
```
```
https://f-droid.org/app/free.rm.skytube.oss/
```
```
https://apt.izzysoft.de/fdroid/index/apk/io.freetubeapp.freetube
```
___
## Sources

* Trying to implement [these](https://dsi.ut-capitole.fr/blacklists/) sources.

- __Source lists for my hosts files:__

[FLOSSbOxIN](https://hosts.flossboxin.org.in/files/hosts) | [No-Amazon](https://github.com/nickspaargaren/no-amazon) | [Hectorm](https://hblock.molinero.dev/hosts) | [Hosts Vietnam](https://raw.githubusercontent.com/bigdargon/hostsVN/master/hosts) | [Steven Black](https://raw.githubusercontent.com/StevenBlack/hosts/master/alternates/fakenews-gambling-porn-social/hosts) | [PolishFiltersTeam](https://raw.githubusercontent.com/PolishFiltersTeam/KADhosts/master/KADhosts.txt) | [MetaMask](https://raw.githubusercontent.com/MetaMask/eth-phishing-detect/master/src/hosts.txt) | [Bad-Boyz](https://raw.githubusercontent.com/mitchellkrogza/Badd-Boyz-Hosts/master/hosts) | [AnudeepND](https://raw.githubusercontent.com/anudeepND/blacklist/master/CoinMiner.txt) | [Badmojr](https://badmojr.github.io/1Hosts/Pro/hosts.txt) | [Easy List](https://easylist.to/easylist/easylist.txt) | [Easy List-Privacy](https://easylist.to/easylist/easyprivacy.txt) | [Easy List-Cookie](https://easylist-downloads.adblockplus.org/easylist-cookie.txt) | [Yous](https://raw.githubusercontent.com/yous/YousList/master/hosts.txt) | [YHosts](https://raw.githubusercontent.com/vokins/yhosts/master/hosts.txt) | [GBA-Samsung](https://raw.githubusercontent.com/jerryn70/GoodbyeAds/master/Extension/GoodbyeAds-Samsung-AdBlock.txt) | [GBA-YT](https://raw.githubusercontent.com/jerryn70/GoodbyeAds/master/Extension/GoodbyeAds-YouTube-AdBlock.txt) | [GBA](https://raw.githubusercontent.com/jerryn70/GoodbyeAds/master/Hosts/GoodbyeAds.txt) | [GBA-Xiaomi](https://raw.githubusercontent.com/jerryn70/GoodbyeAds/master/Extension/GoodbyeAds-Xiaomi-Extension.txt) | [GBA-Le-Eco](https://raw.githubusercontent.com/jerryn70/GoodbyeAds/master/Extension/GoodbyeAds-LeEco-Extension.txt) | [Idoo](https://gist.githubusercontent.com/idoo/dc809ae93a3da54fb24c92185dfffffa/raw/d19b6edd63cbd9154d20dce782198920c3bb770e/hosts-yt-ads) | [XFiles-Stable](https://raw.githubusercontent.com/gioxx/xfiles/master/filtri.txt) | [XFiles-FB](https://raw.githubusercontent.com/gioxx/xfiles/master/facebook.txt) | [XFiles-SiteBlock](https://raw.githubusercontent.com/gioxx/xfiles/master/siteblock.txt) | [XFiles-UPD UBlock](https://raw.githubusercontent.com/gioxx/xfiles/master/upd.txt)

___
- __Resultant Host File:__

[`hosts`](https://hosts.flossboxin.org.in/files/hosts)

___
- __Credits:__

[vdbhb59](https://github.com/vdbhb59) |
[FLOSSbOxIN](https://github.com/FLOSSBoxIN)
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
[No-Google > Nick Spaargaren](https://github.com/nickspaargaren/no-google) |
[YouTube Hosts > Ivan Verevkin](https://github.com/idoo) |
[XFiles > Gioxx](https://github.com/gioxx/xfiles)

___
## License

Content of the **hosts** is licensed under a [MIT License](https://github.com/vdbhb59/hosts/blob/master/LICENSE).
