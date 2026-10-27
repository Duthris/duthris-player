<div align="center">

<img src="docs/banner.svg" alt="Duthris Player" width="100%">

<br>

[![Latest release](https://img.shields.io/github/v/release/Duthris/duthris-player?style=for-the-badge&logo=github&color=7c4dff&label=release)](https://github.com/Duthris/duthris-player/releases/latest)
[![Downloads](https://img.shields.io/github/downloads/Duthris/duthris-player/total?style=for-the-badge&logo=windows&color=6b6cf0&label=downloads)](https://github.com/Duthris/duthris-player/releases)
[![Platform](https://img.shields.io/badge/Windows-10%20%7C%2011-0078D4?style=for-the-badge&logo=windows11&logoColor=white)](#-install)
[![License](https://img.shields.io/github/license/Duthris/duthris-player?style=for-the-badge&color=10b981)](LICENSE)
[![CI](https://img.shields.io/github/actions/workflow/status/Duthris/duthris-player/ci.yml?branch=main&style=for-the-badge&label=CI)](https://github.com/Duthris/duthris-player/actions/workflows/ci.yml)

**English** · [Türkçe](README.tr.md)

**A local-first player for your own M3U and Xtream playlists.** Live TV with a guide, films and series<br>
with posters and resume, and the formats a browser can't play. No account, no servers, no content included.

<a href="https://github.com/Duthris/duthris-player/releases/latest"><img src="https://img.shields.io/badge/Download%20for%20Windows-7c4dff?style=for-the-badge&logo=windows&logoColor=white" alt="Download for Windows" height="44"></a>

</div>

<br>

<table align="center">
  <tr>
    <td align="center"><img src="docs/screenshots/live.png" width="260" alt="Live TV"><br><sub><b>Live TV</b> with now and next</sub></td>
    <td align="center"><img src="docs/screenshots/movies.png" width="260" alt="Films"><br><sub><b>Films and series</b> as poster grids</sub></td>
    <td align="center"><img src="docs/screenshots/guide.png" width="260" alt="TV guide"><br><sub><b>TV guide</b> on a timeline</sub></td>
  </tr>
</table>

> [!NOTE]
> Duthris Player is a player. It ships no channels, playlists or streams and never will. You add the playlist your provider gave you; the app plays it. Screenshots use a made-up demo library.

## ✨ What it does

| | |
| --- | --- |
| 📺 **Live TV** | Categories, search, a guide-aware channel list, number-key channel entry, previous/next and back-to-last-channel. Falls back from HLS to raw MPEG-TS on its own, because many channels only serve one of the two. |
| 🎬 **Films and series** | Poster grids that stay fast over catalogues in the tens of thousands, resume, automatic next episode, sorting and filtering. Missing posters and descriptions are filled in from TMDB. |
| 🗓️ **TV guide** | XMLTV import with fuzzy channel matching, a scrollable timeline, per-day navigation, timezone correction, and reminders before a programme starts. Uses the panel's own guide when there is no XMLTV. |
| 🎞️ **Plays what browsers can't** | MKV and AVI, AC-3, E-AC-3 and DTS audio go through a bundled FFmpeg and are remuxed on the fly. Video is copied whenever it can be, so usually only the audio is converted. |
| 💬 **Subtitles** | Embedded tracks, your own `.srt` / `.vtt` / `.ass` files, or a search on OpenSubtitles from inside the player. Styling and delay are adjustable. |
| 🧑‍🤝‍🧑 **Profiles** | Separate favourites, history and continue-watching per person, optional PINs, and profiles limited to chosen playlists. |
| 📥 **Offline and archive** | Keep films and episodes on disk to watch later, and play catch-up from the archive where the panel offers it. |
| 🎛️ **Player** | Quality and audio track choice, aspect ratio, speed, sleep timer, picture-in-picture, media keys, or hand the stream to mpv or VLC. |
| 🔄 **Updates itself** | New versions download in the background and install on the next restart. It can also start with Windows and wait in the tray. |

<table align="center">
  <tr>
    <td align="center"><img src="docs/screenshots/player.png" width="260" alt="Player"><br><sub><b>The player</b>, any container</sub></td>
    <td align="center"><img src="docs/screenshots/series.png" width="260" alt="Series"><br><sub><b>Series</b> by season and episode</sub></td>
    <td align="center"><img src="docs/screenshots/welcome.png" width="260" alt="Adding a playlist"><br><sub><b>One form</b> to add a playlist</sub></td>
  </tr>
</table>

## 📥 Install

1. Download from the [latest release](https://github.com/Duthris/duthris-player/releases/latest):
   - **`Duthris-Player-x.y.z-x64.exe`**: installer. Recommended; it **updates itself**.
   - **`Duthris-Player-x.y.z-portable.exe`**: single file, nothing to install.
2. Run it, add your M3U link, M3U file or Xtream login, and start watching.
3. Optionally, download the TV guide from **Playlistler → TV rehberini indir** (Playlists → Download TV guide).

The interface is in Turkish for now; the labels below are given as they appear in the app.

> [!NOTE]
> The executables are not code-signed yet, so Windows SmartScreen may say *"Windows protected your PC"*. Click **More info → Run anyway**. Every release is built from this repository by [GitHub Actions](https://github.com/Duthris/duthris-player/actions/workflows/release.yml).

> [!TIP]
> This app was called **Duthris IPTV** until 1.10. Existing installs update in place and keep their profiles, playlists and history.

## ❓ FAQ

<details>
<summary><b>Where do I get a playlist?</b></summary>

From your provider. Duthris Player doesn't sell, include or point to any playlist; it only plays the one you add.
</details>

<details>
<summary><b>A channel won't play, or plays without sound</b></summary>

Open **Playlistler** and try the other **Yayın protokolü** (stream protocol: HTTP / HTTPS) for that source. Some panels only answer to a known player; the **Kimlik (User-Agent)** field there is for that. If it still fails, export the log from **Ayarlar → Günlükleri dışa aktar** (Settings → Export logs) and open an issue.
</details>

<details>
<summary><b>Is there a version for macOS or the browser?</b></summary>

Windows is the supported target today. The same app also runs as a web build, but a browser can't demux MKV, reach HTTP streams from an HTTPS page or get around DNS blocks on image hosts, so treat it as best effort.
</details>

<details>
<summary><b>How do I move to another PC?</b></summary>

**Ayarlar → Yedek oluştur** (Settings → Create backup) writes an encrypted file with your profiles, playlists, favourites and history. Restore it with **Yedekten geri yükle** on the other machine.
</details>

## 🔒 Privacy

No account, no telemetry, no servers of our own. Everything (profiles, favourites, watch history, the catalogue) stays on your PC. The app only talks to:

- your playlist and guide provider;
- TMDB, for missing posters and descriptions;
- OpenSubtitles, when you search for subtitles;
- YouTube (`youtube-nocookie.com`), when you open a trailer;
- Cloudflare or Google DNS-over-HTTPS, for name lookups in the desktop app;
- GitHub, to check for updates.

## 🛠️ Development

Requires Node.js 22+ and pnpm 11+.

```sh
pnpm install
pnpm dev                          # web app on http://localhost:3000
pnpm --filter @iptv/desktop dev   # desktop shell against it
pnpm -w run verify                # typecheck, lint, build, desktop export
pnpm -w run package:win           # NSIS installer and portable exe in apps/desktop/release
```

Pushing a `v*` tag builds and publishes a release with GitHub Actions; installed copies pick it up through the auto-updater.

Copy `apps/web/.env.example` to `apps/web/.env.local` to bake a TMDB token into a build. It is optional; the token can also be pasted into the settings screen. Icons are generated from one SVG and committed (`pnpm -w run icons`).

```
apps/web        Next.js app, exported statically for the desktop shell
apps/desktop    Electron main process, FFmpeg transcode server, credential storage
packages/core   Framework-free parsers and clients: M3U, XMLTV, Xtream, TMDB
packages/db     Dexie schema and repositories
packages/ui     Design tokens and shared components
packages/config TypeScript and ESLint bases
```

Packages are consumed as source via `transpilePackages`. The `/api/proxy` route of the web build only carries text and JSON (playlists, XMLTV, the Xtream API) and rejects video and images.

**Out of scope on purpose:** hosting or distributing any stream, proxying video through a server, cloud sync, recording, and casting.

## ⚖️ Legal notice

> [!IMPORTANT]
> Duthris Player contains no media, channels or playlists, and is not affiliated with any provider. Users are responsible for having the right to watch whatever they add. The project is shared on an open-source platform for knowledge sharing and software development education.

## 📄 License

[MIT](LICENSE) © Duthris
