# Tonearm

A lossless player for your own music server, on Android (with Android Auto) and on Linux and Windows. It
can request music you don't have yet through Lidarr and get AI suggestions from your own Ollama.

| Repository | What it is |
| --- | --- |
| [Tonearm-PhoneApp](https://github.com/brab-one/Tonearm-PhoneApp) | the Android app |
| [Tonearm-Desktop](https://github.com/brab-one/Tonearm-Desktop) | the Linux and Windows app |
| [Tonearm-Server](https://github.com/brab-one/Tonearm-Server) | for everyone on your Navidrome: the phone controls the desktop app, Lidarr and Maloja without handing out their keys, AI picks from Ollama |
| [Tonearm-Connect](https://github.com/brab-one/Tonearm-Connect) | the old Lidarr plugin version, no longer used by the apps |

## Install

1. **Phone:** install the `.apk` from the [phone app releases](https://github.com/brab-one/Tonearm-PhoneApp/releases/latest). 
2. **Desktop:** use the [desktop releases](https://github.com/brab-one/Tonearm-Desktop/releases/latest).
   On Windows, run the `.msi`. On Linux, install the `.deb` or unpack the `.tar.gz`. Linux also needs mpv
   (`sudo apt install libmpv2` or `sudo pacman -S mpv`).
3. **Server** (for everything beyond playing): run the [Tonearm server](https://github.com/brab-one/Tonearm-Server)
   in Docker and send your proxy's `/connect-tonearm` to it (step by step in its README).

## Setup

- **Music server** (required): Navidrome or another Subsonic server. In each app, enter its address, your
  username and your password. If the server sits behind an mTLS proxy, import the same `.p12` client
  certificate in each app.
- **Lidarr** (optional): give its address and API key (from Lidarr → Settings → General) to the Tonearm
  server; the apps get it from there. This lets you request artists and albums, and liking a YouTube Music song requests
  its album so the lossless version gets downloaded. Lidarr must save its downloads into the music
  server's library folder.
- **Maloja** (optional, phone only): give its address and API key to the Tonearm server, or enter them in
  the app, to get recommendations from your
  listening history. For Maloja you need a last.fm account (search could also work through tubifarry youtube music search.)
- **Discovery** works by itself once the Tonearm server runs: artists like yours, from Deezer.
- **AI picks** (optional): give the Tonearm server your Ollama's address (`OLLAMA_URL`). They show up under
  Discover in both apps, together with **weekly picks** (a new playlist every week that downloads by itself).
- **Phone controls desktop:** run the server and use the same music server address in both apps. The desktop app then appears in the phone's **Devices** screen.

  ## TODO:
  add ios APP
  move connect to navidrome as plugin
