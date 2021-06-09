![Cover Image](https://i.ibb.co/PmYn5c5/image.png)

# Found new channels? ![](https://img.shields.io/github/issues/weareblahs/epg "Current Issue Counter")
[Submit an issue here and tag "Found Channel"](https://github.com/weareblahs/unifi-tv/issues)

# What's this?
This is a m3u8 playlist file for Unifi playTV / Unifi TV. These links don't use normal HLS / MPEG-TS Livestreams, instead, using encrypted ones (MPEG-DASH). Remember, this guide is not used to bypass DRM and doesn't provide Free Links - you need your own unifi TV subscription.  
  
Note that this is also another way to watch Unifi TV through TiviMate through Telekom Malaysia's official servers. It is not required to install the official Unifi TV app.

# Pre-built unifi TV playlist
NOTE: It is strongly recommended for you to get the key by yourself. The playlist below is created with a Free unifi PlayTV account.  
Github Mirror: https://github.com/weareblahs/unifi-tv/raw/main/unifi_prebuilt.m3u8  
Github Mirror (Shortlink, suitable for direct access on TiviMate): https://tinyurl.com/unifi-tv-gh  
Google Drive mirror: https://drive.google.com/uc?export=download&id=1ejdwBwQ71Tsc7b1KJKME9jCwZZC8T7ci  
Google Drive mirror (Shortlink, suitable for direct access on TiviMate): https://tinyurl.com/unifi-tv-gd  

# 503 Service Unavailable?
Change the User-Agent to "" (blank).

# Tested on what device / app?
Works well on Tivimate v2.8.0 and TVirl (Xiaomi Mi Box S).
## What Internet Connection?
Tested on Unifi Air. It will play on multiple resolutions according to the Internet speed (ranging from 576p to 1080p). Unifi Fibre Broadband might get better speeds when playing.

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
- Maximum Resolution is 1920x1080

# Is there cons?
- Unable to record
- DRM-protected Streams (Widevine / PlayReady)
- No timeshift although the link is capable of timeshifting (Timeshifting works on OTT Navigator by changing the setting for days to 1 and type to Auto - only works on free channels for free users, such as free-to-air channels)
- Channel won't follow channel number, but follows the channel sequence on Tivimate (also thanks to @dysoct)
- No Android emulator support (such as Bluestacks, Nox, Memuplay) (thanks to @arscenu for pointing out about this problem)

# Players that can play this playlist
- Tivimate
- TVirl
- PVR Live (Channel Icons needs payment)
- [Native MPEG-DASH / HLS Player](https://chrome.google.com/webstore/detail/native-mpeg-dash-+-hls-pl/cjfbmleiaobegagekpmlhmaadepdeedn?hl=en) (You have to insert your Widevine license URL when requested)
- OTT Navigator (Update to the newest version)

# Known players that can't play this playlist
- Kodi (Can't play even InputStream Adaptive is enabled - my guess is it only plays with add-ons)
- VLC (Unencrypted DASH only)
- IPTV Smarters (HLS / MPEG-TS only)
- CosmiDVR (Signal Weak = 403 Access Denied error)
- Media Player Classic Home Cinema (uses youtube-dl to get mpd playlist, however, there's no option for inserting license ID)
- Televizo
- ZalTV

# Information
Please note that these links can be only accessed through a Widevine Server (for authorizing). Instructions below.  
**Note that the Widevine Server URL changes every 3-7 days**, so you have to follow the steps below regularly if you want to continue using this playlist.

# And now, the ultimate guide for this particular playlist
## RECOMMENDED: Use this script for the playlist.
I made a script for generating the playlist. See [this link](https://github.com/weareblahs/unifi-tv/releases/tag/1.0_20210520) for more information. Note that you still have to follow the "Get Widevine Server URL" part at this guide.
## Get Widevine Server URL
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

## Download the file and modify the inputstream.adaptive.license_key to the Widevine Server URL
1. Download "unifi.m3u8" by [clicking here](https://github.com/weareblahs/unifi-tv/raw/main/unifi.m3u8).
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

# EPG?
EPG Link for partial channels: https://weareblahs.github.io/epg/unifitv.xml  
  Generated through Webgrab+Plus.
## EPG for Polimer and Jaya MAX
Use *http://raw.githubusercontent.com/epgshare01/share01/master/epg_ripper_IN4.xml.gz* for Indian channels on unifi TV, and change the ID of the indian channels to:
 - Polimer: Change "CHN" to "Polimer.TV.in"
 - Jaya Max: Change "CHN" to "Jaya.Max.in"
 - Colors Cineplex (India Time): Change "CHN" to "Colors.Cineplex.HD.in"

## EPG: Important Update
FOUND: unifi PlayTV is powered by Huawei's Envision Video Platform.
 - [Here is an example of the EPG data for this platform.](https://gist.github.com/weareblahs/89fc50e4011094628749b6362187e669)
 - If someone made a SiteIni for unifi TV (Unencrypted), please contact me through [my email](https://gist.github.com/weareblahs/dccd48e74be31ec770a09036d97c02a8) and I will process it as soon as possible to update the unifi TV Guide through unifi.com.my.
   - the SiteIni file will not be uploaded into GitHub.
