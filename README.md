# mineload

```
█▀▄▀█ ▀█▀ █▀▄█ █▀▀ █   █▀█ █▀█ █▀▄
█ ▀ █  █  █  █ █▀  █   █ █ █▀█ █ █
█   █ ▀█▀ ▀  ▀ ▀▀▀ ▀▀▀ ▀▀▀ ▀ ▀ █▄▀
```

mine any video. paste. mine. done.

A Minecraft-styled terminal video downloader. Download videos from
YouTube, X/Twitter, Instagram, Threads, TikTok and 1,800+ other sites —
right from your terminal. Paste a url, pick a resolution (or audio-only
mp3), done. No popups, no fake download buttons, no sketchy redirects.

## Install

```sh
npm install -g mineload
```

Or try it without installing anything:

```sh
npx mineload
```

Requires Node 18+. Everything else (yt-dlp, ffmpeg) is fetched or bundled
automatically.

## Install from GitHub

```sh
git clone https://github.com/callmeahmadnasir-ops/mineload.git
cd mineload
npm install
npm run build
npm link
```

Now run it from anywhere:

```sh
mineload https://youtu.be/dQw4w9WgXcQ
```

## Usage

```sh
$ mineload https://youtu.be/dQw4w9WgXcQ    # straight to the format picker
$ mineload                                 # prompts for a url
$ mineload --theme dark                    # minecraft green palette
```

mineload takes over the terminal (full-screen, centered — and restores
your scrollback on exit). Pick a format with ↑/↓ (or j/k, or number keys)
and hit enter. esc goes back, ^c quits. The mouse works too — the mine
button, the format list and the footer hints are all clickable, and
clicking the logo takes you back home. Files are saved to ~/Downloads,
and the file path is printed to your terminal when you're done.

The default auto theme uses your terminal's own foreground and background.
Press ^t or click the theme control in the footer to cycle through auto,
light, and dark for the current session. The dark theme rocks the classic
Minecraft chat green. Use `--theme auto`, `--theme light`, or
`--theme dark` to choose the starting theme for one launch.

## How it works

Powered by [yt-dlp](https://github.com/yt-dlp/yt-dlp). On first run,
mineload downloads the standalone yt-dlp binary to `~/.mineload/bin` —
no Python required. If you already have yt-dlp installed, it uses yours.
ffmpeg (needed for merging high-res streams and mp3 extraction) is found
on your PATH, with ffmpeg-static as a bundled fallback.

The UI is [Ink](https://github.com/vadimdemedes/ink) — React for the
terminal.

## Development

```sh
npm install
npm run build        # bundle to dist/ with tsup
npm run dev          # rebuild on change
node dist/cli.js <url>
npm run typecheck
```

To try it as a global command without publishing: `npm link`, then run
`mineload` anywhere.

## A note on fair use

mineload is a personal-archiving tool. Downloading content may violate a
platform's terms of service — only download what you have the right to
keep, and be excellent to creators.

## License

MIT
