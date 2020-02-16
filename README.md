# hosts
Curated lists of hosts files with various domain blocks. See "Source" text file for credits and source list.

Following are the list of files present within the repository:

01. Ultimate > Contains blockers for almost all sites.
**`youtube.com`** and **`googlevideo.com`** are removed from blacklist.
**`graph.facebook.com`** is blacklisted, as it is a black redirect.

02. Xtreme > Contains blockers for Samsung devices as well. However, limited in hosts.
I am not planning on updating this too much, but I will try my level best.

03. YouTube > Special hosts for YouTube advertisements.
Server uses **`s.ytimg.com`** and **`manifest.googlevideo.com`** to push advertisements.
Of late, **`youtube-nocookie.com`** is being used by Alphabet Incorporation to push advertisements, as well as video content, and thus may not work unless this is whitelisted. I have whitelisted it as of now.

I am working on a systmd to make it work nightly.

## Supported Operating Systems

***Windows:*** Users for Windows would find it easy to use with [`Hostman`](http://www.abelhadigital.com/hostsman/), a software to manage host file.
     
***Android:*** For non-rooted devices, GoodbyeAds can be used with [`DNS66`](https://f-droid.org/en/packages/org.jak_linux.dns66/), [`Blokada`](https://f-droid.org/en/packages/org.blokada.alarm/), [`Personal DNS Filter`](https://www.zenz-solutions.de/personaldnsfilter/) or [`Nebulo`](https://nebulo.app/source).
The above softwares are free and open-source ad-blockers.
     
For rooted device, this host file can be used with [`AdAway`](https://f-droid.org/en/packages/org.adaway/), a free and open-source ad-blocker for Android.
     
***Linux:*** An open-source host file manager called [`hBlock`](https://github.com/hectorm/hBlock).
       
***Mac OS:*** This host file can be used with [`gasmask`](https://github.com/2ndalpha/gasmask).
   
***Adblockers:*** Use filter format with [`uBlock`](https://github.com/gorhill/uBlock), [`AdGuard`](https://adguard.com/en/welcome.html) or any other extension, software & app.

## Usage guide

### Blokada
Open Blokada > navigate to Hosts List > Click + button and then copy paste your choice of hosts from the below url.
Then press the Shield icon to activate.
```
https://raw.githubusercontent.com/vdbhb59/hosts/master/Hosts-Ultimate.txt
https://raw.githubusercontent.com/vdbhb59/hosts/master/Hosts-Xtreme.txt
https://raw.githubusercontent.com/vdbhb59/hosts/master/YouTube-Hosts.txt
```

### DNS66
Open DNS66 > swipe to Hosts > Click + button and then copy paste your choice of hosts from the below url.
Then press the refresh icon on the top and press the start button.
```
https://raw.githubusercontent.com/vdbhb59/hosts/master/Hosts-Ultimate.txt
https://raw.githubusercontent.com/vdbhb59/hosts/master/Hosts-Xtreme.txt
https://raw.githubusercontent.com/vdbhb59/hosts/master/YouTube-Hosts.txt
```

### Adaway
Open Adaway > go to Host Source > Click + button and then copy paste your choice of hosts from the below url.
Then Click enable ad blocking from the home menu.
```
https://raw.githubusercontent.com/vdbhb59/hosts/master/Hosts-Ultimate.txt
https://raw.githubusercontent.com/vdbhb59/hosts/master/Hosts-Xtreme.txt
https://raw.githubusercontent.com/vdbhb59/hosts/master/YouTube-Hosts.txt
```

## Recommended Whitelist

- __Facebook main app__
- __Facebook Lite Messenger__

## License

Content of the **hosts** is licensed under a [MIT License](https://github.com/vdbhb59/hosts/blob/master/LICENSE).