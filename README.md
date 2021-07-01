![Cover Image](https://i.ibb.co/PmYn5c5/image.png)
## Before you use this playlist
This playlist won't support emulators (such as Nox and BlueStacks) - mostly due to Widevine issues. See [this discussion thread](https://gist.github.com/weareblahs/89fc50e4011094628749b6362187e669#gistcomment-3770390) for more information. You can use a real device - no matter it's smartphones or TV boxes (sideload TiviMate if your TV Box isn't certified by Google) for this playlist.

Raspberry Pi 4 users? Use KonstaKANG's [Android TV Build](https://konstakang.com/devices/rpi4/) for this playlist. Install / Sideload TiviMate or TVirl on your Raspberry Pi 4 through your flash drive. Subtitle works on both TiviMate and TVirl.

## Channel Searching?
Now finding links for the other unifi Sports channels for Tokyo Olympics 2020 (unifi Sports 6 - unifi Sports 13). Create an issue with the "Found Channels" tag if you found these channels.
# Recommended option: Direct URL for m3u8
You don't have to find the AuthResp_VUID - Use the following URL format on your IPTV client:  
``https://my-iptv.herokuapp.com/m3u8/unifi-tv?userID=(Your Phone Number)&clientPasswd=(Your playtv@unifi Password)``  
Or a more user-friendly version, where you just have to type in your username / password, then click / tap "Generate":  
[``https://unifiplaytvdrm.samsam123.tk/``](https://unifiplaytvdrm.samsam123.tk/) (mantained by @samleong123)  
Or if you prefer to do it manually, see [here](https://github.com/weareblahs/unifi-tv#manual-instructions).  
Mantained and developed by @ohsem, @samleong123 and @weareblahs. [See project here](https://github.com/ohsem/my-iptv).
## Any problem regarding the server?
Before you submit an issue, check the status of the server [here](https://stats.uptimerobot.com/kMzqWFnVqm)

# Found new channels? ![](https://img.shields.io/github/issues/weareblahs/epg "Current Issue Counter")
[Submit an issue here and tag "Found Channel"](https://github.com/weareblahs/unifi-tv/issues)

# What's this?
This is a m3u8 playlist file for Unifi playTV / Unifi TV. These links don't use normal HLS / MPEG-TS Livestreams, instead, using encrypted ones (MPEG-DASH). Remember, this guide is not used to bypass DRM and doesn't provide Free Links - you need your own unifi TV subscription.  
  
Note that this is also another way to watch Unifi TV through TiviMate through Telekom Malaysia's official servers. It is not required to install the official Unifi TV app.

# 503 Service Unavailable?
Change the User-Agent to "" (blank).

# Tested on what device / app?
Works well on Tivimate v2.8.0 and TVirl (Xiaomi Mi Box S).

## What Internet Connection?
Tested on Unifi Air. It will play on multiple resolutions according to the Internet speed (ranging from 240p to 1080p (576p max on SD channels)). Unifi Fibre Broadband might get better speeds when playing.

# Do you have some of the screenshots for these channels?
[Screenshots from TiviMate (Channels with subtitles)](https://github.com/weareblahs/unifi-tv/blob/main/screenshots/tivimate.md)  
[Screenshots from generic MPD player](https://github.com/weareblahs/unifi-tv/blob/main/screenshots/mpd.md)

# Other features?
- Multiple Audio (if any, mostly Malay / Chinese / English / Other Languages)
- Subtitles (Mostly Malay / Chinese),
- Adaptive Resolution (automatic resolution switching according to your Internet connection)
- **NEW!** Channel Categories (thanks to @dysoct)

# Known Technical Specs?
- 128Kbps AAC Audio
- H264 Video (Bitrate depends on resolution)
- Maximum Resolution is 1920x1080 (1024x576 max on SD channels)

# Is there cons?
- Unable to record
- DRM-protected Streams (Widevine / PlayReady)
- No timeshift although the link is capable of timeshifting (Timeshifting works on OTT Navigator by changing the setting for days to 1 and type to Auto - only works on free channels for free users, such as free-to-air channels)
- Channel won't follow channel number, but follows the channel sequence on Tivimate (also thanks to @dysoct)
- No Android emulator support (such as Bluestacks, Nox, Memuplay) (thanks to @arscenu for pointing out about this problem)
  - Will test it on Windows 11 when it start supporting Android apps

# Players that can play this playlist
- TiviMate (Recommended due to it didn't return any errors)
- TVirl
- PVR Live (Channel Icons needs payment)
- [Native MPEG-DASH / HLS Player](https://chrome.google.com/webstore/detail/native-mpeg-dash-+-hls-pl/cjfbmleiaobegagekpmlhmaadepdeedn?hl=en) (You have to insert your Widevine license URL when requested)
- OTT Navigator (Sometimes it got errors regarding license decryption, or 503 error - just refresh or change user-agent)

# Known players that can't play this playlist
- Kodi (Can't play even InputStream Adaptive is enabled - my guess is it only plays with add-ons)
- VLC (Unencrypted DASH only)
- IPTV Smarters (Xtream codes only - no support of MPEG-DASH even if you use a Xtream Codes proxy to fake an Xtream Codes address)
- CosmiDVR (Signal Weak = 403 Access Denied error)
- Media Player Classic Home Cinema (uses youtube-dl to get mpd playlist, however, there's no option for license ID)
- Televizo (HLS / MPEG-TS streams only)
- ZalTV (HLS / MPEG-TS streams only)

# Information
Please note that these links can be only accessed through a Widevine Server (for authorizing). Instructions below.  
**Note that the Widevine Server URL changes every 3-7 days**, so you have to follow the steps below regularly if you want to continue using this playlist.

## RECOMMENDED: 
Use the Direct URL for m3u8 option for automatic updating without getting the VUID manually. See the "Recommended option: Direct URL for m3u8" section.
# Manual Instructions
## Video Guides
[How to get AuthResp_VUID](https://streamable.com/ec7uk7)  
[unifigenerate Walkthrough](https://streamable.com/ii22ji)
## Get Widevine Server URL (Computer)
(Note that the previous instructions usually returns an "This Service Is Temporarily Unavailable. (632116)" error when constantly getting the Widevine key. Here are the new instructions (Thanks @samleong123):  
1. Go to [this page](https://playtv.unifi.com.my/EPG/WEBTV/index.html#/live-tv/).
2. Sign in with your Facebook account / Sign up for unifi playTV through Facebook / phone number / email address.
3. After signing in, follow these steps:
      - Right Click > Inspect Element.
      - Click "Application" > Local Storage > https://playtv.unifi.com.my.
      - Search for "AuthResp_VUID".
      - The result should look like this:  
        ![Result](https://pictr.com/images/2021/05/20/BP13Ex.png)
      - Copy the AuthResp_VUID.
4. Modifying the URL
      - Follow this template for the URL: ``https://ottweb.hypp.tv:8064?deviceId=[AuthResp_VUID]``  
        (Paste the AuthResp_VUID at the part of the URL which says [AuthResp_VUID] and remove the quotes ("").
      - Copy it. we will use the URL at the next step.
## Get Widevine Server URL (Smartphone by using Google Chrome) - Credits to @Arsyad1105
[Follow this method](https://github.com/weareblahs/unifi-tv/issues/11).
## Download the file and modify the inputstream.adaptive.license_key to the Widevine Server URL
1. Download "unifi.m3u8" by [clicking here](https://github.com/weareblahs/unifi-tv/raw/main/manual/unifi.m3u8).
2. Open it with Notepad. (SHORTCUT: Windows key + R > notepad > Enter)
3. In notepad, press "Ctrl + H" (Replace).
      - In "Find What", type in "WIDEVINE_SERVER_URL_HERE".
      - In "Replace With", paste the URL which we got at the previous step.
4. Save it. Now you have a m3u8 file ready to import.

## Importing into compatible IPTV players
### Before we start the importing
NOTE: This playlist only supports TiviMate, PVR Live and TVirl.
1. Upload the file to Dropbox / Github / Any file hosting service that support direct link
     - You can also use HFS. I'm using HFS for m3u8 Transfer through local network. [See the guide by clicking here](https://github.com/weareblahs/unifi-tv/blob/main/guide/hfs.md)
     - Offline options: Use File Commander to transfer the playlist to your TV / TV Box
### Uploading your playlist into Dropbox for Tivimate Access
1. Sign in into Dropbox
2. Upload the saved m3u8 file to your Dropbox.
3. Hover on the file name in Dropbox, click Share, then click Create from "Create then Copy Link".
4.  Click on "Copy Link". (the Dropbox link will be copied in your clipboard)
5. Open any text editor, paste it, then change "dl=0" into "dl=1" (at the end of the link).
     -  (Note that you have to memorize this link OR copy this link to your TV at the next step)
6. Done!
### Importing your playlist into Tivimate
1. After opening the app, select "Add Playlist".
2. Select "Enter URL", then type in the link that you've generated.
3. Select "Next".
4. Follow the steps. EPG should be automatically detected from the m3u8 file.
5. You're ready to watch!

## EPG Credits
EPG for unifi TV in-house channels (such as HyppSensasi, unifi Sports) and some Indian channels (such as SET, Polimer) has been made available on the EPG thanks to @hantu08 (Khalis) on Telegram.
# No EPG?
Check the XMLTV / EPG settings of your IPTV app - is there an EPG source called "https://weareblahs.github.io/epg/unifitv.xml" (or unifitv on some clients)? If not, then manually add "https://weareblahs.github.io/epg/unifitv.xml" to one of your EPG source.
