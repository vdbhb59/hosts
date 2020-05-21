# hosts
Curated lists of hosts files with various domain blocks. See "Source" text file for credits and source list. Lot of hosts are based on my own digging.

I have made different variants, with older model of phones and with lesser ram available. All lists are compatible with almost all adblockers.

N.B.: I am not planning on filters yet, as that is a very heavy task, and takes way much time to maintain. Will come to it soon though.

Following are the list of files present within the repository:

01. **ALL** > Contains blockers for almost all sites. Will break many things, so please ask me to whitelist with the correct hosts-ip. The list is huge, so it is difficult to examine and identify what may cause the break. Try and use DNS66 or Blokada to determine the cause.
Size - Average `10-15 MB`, depending on dead entries.
::Will be revamped or removed, depending on the time I get and the time taken to make this file, what it is... Soon..

02. **Large** > Contains almost all blocklists, however, smaller in size compared to `ALL`. Probably `half the size` at times.

03. **Midi** > Contains blockers for Samsung devices as well. However, limited in hosts. Bit smaller in size, but would stay `beyond 5MB` most of the times.

04. **Mini** > Minimal hosts, but with device wide (android only) ads blocked. The Ads-Block-List android blockers are included to cover device wide blocking.
File size - `1.8-2.5 MB`. Caters to all low memory phones, or older version phones. Works on Jellybean too (may break few functions, minimum though).

05. **YouTube** & **YouTube Ultimate** > Special hosts for YouTube advertisements.
Server uses **`s.ytimg.com`** and **`manifest.googlevideo.com`** to push advertisements.
Of late, **`youtube-nocookie.com`** is being used by Alphabet Incorporation to push advertisements, as well as video content, and thus may not work unless this is whitelisted.
Hence, the following should be whitelisted:
**`0.0.0.0 apis.google.com`**
**`0.0.0.0 clients.l.google.com`**
**`0.0.0.0 clients1.google.com`**
**`0.0.0.0 gstatic.com`**
**`0.0.0.0 manifest.googlevideo.com`**
**`0.0.0.0 i.ytimg.com`**
**`0.0.0.0 www.gstatic.com`**
**`0.0.0.0 www.youtube-nocookie.com`**
**`0.0.0.0 youtube-nocookie.com`**

06. **Ads-Block-List** > Completely revamped the list, as was outdated. Moreover, the file now contains just the ad-blocks and advert-blockers. List is made up of "easy-list" host files, and various other hosts from different-different applications, and personal findings.

N.B.: **`youtube.com`** and **`googlevideo.com`** are removed from blacklist.
**`graph.facebook.com`** should be whitelisted if you want to use f**kbook.

07. **Hosts-Tracking** > This is just specially designed list. Contains all the hosts (afaiaa) of tracking actors throughout various app, sites, and what not.

## Supported Operating Systems

***Android:*** For non-rooted devices, GoodbyeAds can be used with [`DNS66`](https://f-droid.org/en/packages/org.jak_linux.dns66/), [`Blokada`](https://f-droid.org/en/packages/org.blokada.alarm/), [`Personal DNS Filter`](https://www.zenz-solutions.de/personaldnsfilter/) or [`Nebulo`](https://nebulo.app/source).
The above softwares are free and open-source ad-blockers.

For rooted devices, one can replace the default **hosts** file with the file of choice from here, after renaming the choice file to "**hosts**". Permissions should be **rw-r--r--** / **644**.

Otherwise, if one does not wish to add it manually, one can use this host file with [`AdAway`](https://f-droid.org/en/packages/org.adaway/), a free and open-source ad-blocker for Android.

***Linux:*** An open-source host file manager called [`hBlock`](https://github.com/hectorm/hBlock).

***Mac OS:*** This host file can be used with [`gasmask`](https://github.com/2ndalpha/gasmask).

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
https://raw.githubusercontent.com/vdbhb59/hosts/master/Ads-Block-List.txt
https://raw.githubusercontent.com/vdbhb59/hosts/master/Hosts-ALL.txt
https://raw.githubusercontent.com/vdbhb59/hosts/master/Hosts-Large.txt
https://raw.githubusercontent.com/vdbhb59/hosts/master/Hosts-Midi.txt
https://raw.githubusercontent.com/vdbhb59/hosts/master/Hosts-Mini.txt
https://raw.githubusercontent.com/vdbhb59/hosts/master/YouTube-Hosts.txt
```

### DNS66
Open DNS66 > swipe to Hosts > Click + button and then copy paste your choice of hosts from the below url.
Then press the refresh icon on the top and press the start button.
```
https://raw.githubusercontent.com/vdbhb59/hosts/master/Ads-Block-List.txt
https://raw.githubusercontent.com/vdbhb59/hosts/master/Hosts-ALL.txt
https://raw.githubusercontent.com/vdbhb59/hosts/master/Hosts-Large.txt
https://raw.githubusercontent.com/vdbhb59/hosts/master/Hosts-Midi.txt
https://raw.githubusercontent.com/vdbhb59/hosts/master/Hosts-Mini.txt
https://raw.githubusercontent.com/vdbhb59/hosts/master/YouTube-Hosts.txt
```

### Adaway
Open Adaway > go to Host Source > Click + button and then copy paste your choice of hosts from the below url.
Then Click enable ad blocking from the home menu.
```
https://raw.githubusercontent.com/vdbhb59/hosts/master/Ads-Block-List.txt
https://raw.githubusercontent.com/vdbhb59/hosts/master/Hosts-ALL.txt
https://raw.githubusercontent.com/vdbhb59/hosts/master/Hosts-Large.txt
https://raw.githubusercontent.com/vdbhb59/hosts/master/Hosts-Midi.txt
https://raw.githubusercontent.com/vdbhb59/hosts/master/Hosts-Mini.txt
https://raw.githubusercontent.com/vdbhb59/hosts/master/YouTube-Hosts.txt
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

[`Ads-Block`](https://raw.githubusercontent.com/vdbhb59/hosts/master/Ads-Block-List.txt)
[`ALL`](https://raw.githubusercontent.com/vdbhb59/hosts/master/Hosts-ALL.txt)
[`Large`](https://raw.githubusercontent.com/vdbhb59/hosts/master/Hosts-Large.txt)
[`Midi`](https://raw.githubusercontent.com/vdbhb59/hosts/master/Hosts-Midi.txt)
[`Mini`](https://raw.githubusercontent.com/vdbhb59/hosts/master/Hosts-Mini.txt)
[`You-Tube`](https://raw.githubusercontent.com/vdbhb59/hosts/master/YouTube-Hosts.txt)

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
