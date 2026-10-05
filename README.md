# Tonearm

A lossless player for your own music server, on Android (with Android Auto) and on Linux and Windows. It
can request music you don't have yet through Lidarr and get suggestions from Brainarr.

| Repository | What it is |
| --- | --- |
| [Tonearm-PhoneApp](https://github.com/brab-one/Tonearm-PhoneApp) | the Android app |
| [Tonearm-Desktop](https://github.com/brab-one/Tonearm-Desktop) | the Linux and Windows app |
| [Tonearm-Connect](https://github.com/brab-one/Tonearm-Connect) | the Lidarr plugin that lets the phone control the desktop app |

## Install

1. **Phone:** install the `.apk` from the [phone app releases](https://github.com/brab-one/Tonearm-PhoneApp/releases/latest).
2. **Desktop:** use the [desktop releases](https://github.com/brab-one/Tonearm-Desktop/releases/latest).
   On Windows, run the `.msi`. On Linux, install the `.deb` or unpack the `.tar.gz`. Linux also needs mpv
   (`sudo apt install libmpv2` or `sudo pacman -S mpv`).
3. **Plugin** (optional): in Lidarr, go to **System → Plugins** and enter
   `https://github.com/brab-one/Tonearm-Connect`. Install it, then restart Lidarr.

## Setup

- **Music server** (required): Navidrome or another Subsonic server. In each app, enter its address, your
  username and your password. If the server sits behind an mTLS proxy, import the same `.p12` client
  certificate in each app.
- **Lidarr** (optional): in each app's settings, enter Lidarr's address and its API key (from Lidarr →
  Settings → General). This lets you request artists and albums. YouTube Music songs you play are
  requested too, so the lossless version gets downloaded. Lidarr must save its downloads into the music
  server's library folder.
- **Brainarr** (optional): install [Brainarr](https://github.com/RicherTunes/Brainarr) in Lidarr and add it
  as an import list. Its picks show up under Discover on the phone and Brainarr on the desktop.
- **Maloja** (optional, phone only): enter its address and API key to get recommendations from your
  listening history.
- **Phone controls desktop:** install the plugin, set up Lidarr in both apps and use the same music server
  address in both. The desktop app then appears in the phone's **Devices** screen.
