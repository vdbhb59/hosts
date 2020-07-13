# hosts
Curated lists of hosts files with various domain blocks. See "Source" text file for credits and source list. Lot of hosts are based on my own digging.

I have made 3 variants, to make them work with older model of phones and with lesser ram available. All lists are compatible with almost all kind of adblockers.

Following are the list of files present within the repository:

01. **Large** > Contains almost all blocklists.

02. **Midi** > Limited in hosts. Bit smaller in size (`7-9 MB`).

03. **Mini** > Minimal hosts, but with device wide (android only) ads blocked. The Ads-Block-List android blockers are included to cover device wide blocking.
File size (has changed due to recent rise in spamverts) - `3-5 MB`. Caters to all low memory phones, or older version phones. Works on Jellybean too (may break few functions, minimum though).

## Supported Operating Systems

***Android:*** For non-rooted devices, these host files can be used with [`DNS66`](https://f-droid.org/en/packages/org.jak_linux.dns66/), [`Blokada`](https://f-droid.org/en/packages/org.blokada.alarm/), [`Personal DNS Filter`](https://www.zenz-solutions.de/personaldnsfilter/) or [`Nebulo`](https://nebulo.app/source).
The above softwares are free and open-source ad-blockers.

For rooted devices, one can replace the default **hosts** file with the file of choice from here, after renaming the choice file to "**hosts**". Permissions should be **rw-r--r--** / **644**.

Otherwise, if one does not wish to add it manually, one can use this host file with [`AdAway`](https://f-droid.org/en/packages/org.adaway/), a free and open-source ad-blocker for Android.

***Linux:*** An open-source host file manager called [`hBlock`](https://github.com/hectorm/hBlock).

***Mac OS:*** These host files can be used with [`gasmask`](https://github.com/2ndalpha/gasmask).

***Windows:*** Users for Windows would find it easy to use with [`Hostman`](http://www.abelhadigital.com/hostsman/), a software to manage host file.

In case the above is not working, you can try one of the following as well:

[`SwitchHosts`](https://oldj.github.io/SwitchHosts) or [`HostsFileEditor`](https://github.com/scottlerch/HostsFileEditor)

Use installer [`hostsinstaller`](https://github.com/vdbhb59/hosts/blob/master/hosts_install_win.bat) with administrative rights in Windows.

**How to disable DNS CACHE services on Windows?**

1) Hit Win+R & type `regedit` & press enter.

2) Go to `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\services\Dnscache`, and locate the "Start" registry key. Now change its value from 2 (Automatic) to 4 (Disabled)

3) Restart computer once & now change your host file with bigger SIZE.

## Usage guide

### Blokada
Open Blokada > navigate to Hosts List > Click + button and then copy paste your choice of hosts from the below url.
Then press the Shield icon to activate.
```
https://raw.githubusercontent.com/vdbhb59/hosts/master/Hosts-Large.txt
https://raw.githubusercontent.com/vdbhb59/hosts/master/Hosts-Midi.txt
https://raw.githubusercontent.com/vdbhb59/hosts/master/Hosts-Mini.txt
```

### DNS66
Open DNS66 > swipe to Hosts > Click + button and then copy paste your choice of hosts from the below url.
Then press the refresh icon on the top and press the start button.
```
https://raw.githubusercontent.com/vdbhb59/hosts/master/Hosts-Large.txt
https://raw.githubusercontent.com/vdbhb59/hosts/master/Hosts-Midi.txt
https://raw.githubusercontent.com/vdbhb59/hosts/master/Hosts-Mini.txt
```

### Adaway
Open Adaway > go to Host Source > Click + button and then copy paste your choice of hosts from the below url.
Then Click enable ad blocking from the home menu.
```
https://raw.githubusercontent.com/vdbhb59/hosts/master/Hosts-Large.txt
https://raw.githubusercontent.com/vdbhb59/hosts/master/Hosts-Midi.txt
https://raw.githubusercontent.com/vdbhb59/hosts/master/Hosts-Mini.txt
```

### DNS Filter
Open DNS Filter > Tap on Advanced Settings > Tap on Configure Filter Update > Create a new filter by tapping on the Pencil icon > copy paste your choice of hosts from the below url > Tap on Active circle there > Tap on the (✔️) icon > Tap on Configure filter update to hide the menu > Tap on Advanced Settings > Tap on Restart
```
https://raw.githubusercontent.com/vdbhb59/hosts/master/Hosts-Large.txt
https://raw.githubusercontent.com/vdbhb59/hosts/master/Hosts-Midi.txt
https://raw.githubusercontent.com/vdbhb59/hosts/master/Hosts-Mini.txt
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

## Sources

- __Source lists for my hosts files:__

[Hectorm](https://hblock.molinero.dev/hosts) | [Hosts Vietnam](https://raw.githubusercontent.com/bigdargon/hostsVN/master/hosts) | [Steven Black](https://raw.githubusercontent.com/StevenBlack/hosts/master/alternates/fakenews-gambling-porn-social/hosts) | [PolishFiltersTeam](https://raw.githubusercontent.com/PolishFiltersTeam/KADhosts/master/KADhosts.txt) | [MetaMask](https://raw.githubusercontent.com/MetaMask/eth-phishing-detect/master/src/hosts.txt) | [Bad-Boyz](https://raw.githubusercontent.com/mitchellkrogza/Badd-Boyz-Hosts/master/hosts) | [AnudeepND](https://raw.githubusercontent.com/anudeepND/blacklist/master/CoinMiner.txt) | [Badmojr](https://badmojr.github.io/1Hosts/Pro/hosts.txt) | [Easy List](https://easylist.to/easylist/easylist.txt) | [Easy List-Privacy](https://easylist.to/easylist/easyprivacy.txt) | [Easy List-Cookie](https://easylist-downloads.adblockplus.org/easylist-cookie.txt) | [Yous](https://raw.githubusercontent.com/yous/YousList/master/hosts.txt) | [YHosts](https://raw.githubusercontent.com/vokins/yhosts/master/hosts.txt) | [GBA-Samsung](https://raw.githubusercontent.com/jerryn70/GoodbyeAds/master/Extension/GoodbyeAds-Samsung-AdBlock.txt) | [GBA-YT](https://raw.githubusercontent.com/jerryn70/GoodbyeAds/master/Extension/GoodbyeAds-YouTube-AdBlock.txt) | [GBA](https://raw.githubusercontent.com/jerryn70/GoodbyeAds/master/Hosts/GoodbyeAds.txt) | [GBA-Xiaomi](https://raw.githubusercontent.com/jerryn70/GoodbyeAds/master/Extension/GoodbyeAds-Xiaomi-Extension.txt) | [GBA-Le-Eco](https://raw.githubusercontent.com/jerryn70/GoodbyeAds/master/Extension/GoodbyeAds-LeEco-Extension.txt) | [Gloeyisk](https://raw.githubusercontent.com/gloeyisk/SystemlessHosts/master/system/etc/hosts) | [Idoo](https://gist.githubusercontent.com/idoo/dc809ae93a3da54fb24c92185dfffffa/raw/d19b6edd63cbd9154d20dce782198920c3bb770e/hosts-yt-ads)

- __Resultant Hosts:__

[`Large`](https://raw.githubusercontent.com/vdbhb59/hosts/master/Hosts-Large.txt)
[`Midi`](https://raw.githubusercontent.com/vdbhb59/hosts/master/Hosts-Midi.txt)
[`Mini`](https://raw.githubusercontent.com/vdbhb59/hosts/master/Hosts-Mini.txt)

- __Credits:__
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

To be used list:
[No-Amazon](https://github.com/nickspaargaren/no-amazon) (Thanks Evan (785172845)(Telegram) for pointing this out)

## License

Content of the **hosts** is licensed under a [MIT License](https://github.com/vdbhb59/hosts/blob/master/LICENSE).
