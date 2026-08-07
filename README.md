# Iris

A [Rose Pine](https://rosepinetheme.com/) theme for [Rockbox](https://www.rockbox.org/), made for 320×240 color players.

Comes in four variants. Two in Rose Pine's own palette, and two neutral counterparts that keep the exact same layout with the hue dialled back:

| | Iris | Iris Dawn |
|---|---|---|
| Menu | ![](screenshots/iris-menu.png) | ![](screenshots/iris-dawn-menu.png) |
| Now playing | ![](screenshots/iris-wps.png) | ![](screenshots/iris-dawn-wps.png) |
| Lock screen | ![](screenshots/iris-lock.png) | ![](screenshots/iris-dawn-lock.png) |

| | Iris Night | Iris Morning |
|---|---|---|
| Menu | ![](screenshots/iris-night-menu.png) | ![](screenshots/iris-morning-menu.png) |
| Now playing | ![](screenshots/iris-night-wps.png) | ![](screenshots/iris-morning-wps.png) |
| Lock screen | ![](screenshots/iris-night-lock.png) | ![](screenshots/iris-morning-lock.png) |

## Features

- Lock screen with a big clock and track info
- Sidebar with volume level, clock, and battery, visible on every screen
- Topbar with per-screen titles and the currently playing track info
- Now playing screen with album art, track metadata and seek bar
- [InTofu](fonts/README.md) typeface throughout: [Inter](https://rsms.me/inter/) for Latin, [Noto Sans SC](https://fonts.google.com/noto/specimen/Noto+Sans+SC) for CJK and everything else, merged into one set of Rockbox bitmap fonts

Everything is drawn with skin-engine primitives except two things: a transparent iconset used to indent list rows, and the sidebar clock, which is a set of pre-rendered bitmap strips because the skin engine can only draw text horizontally.

The fonts cover the full Basic Multilingual Plane, so CJK, kana, Hangul-adjacent scripts and more render without tofu. See [fonts/README.md](fonts/README.md) for the font build.

## Installation

Each variant is a self-contained tree, so you only need the one you want:

```
iris/.rockbox          iris-night/.rockbox
iris-dawn/.rockbox     iris-morning/.rockbox
```

1. Copy the `.rockbox` folder from your chosen variant to the root of your player, merging with the existing one.
2. On the player, go to: **Settings → Theme Settings → Browse Themes** and pick `iris`, `iris-dawn`, `iris-night` or `iris-morning`.

Installing several is fine — they ship identical fonts and iconset, so merging them adds no extra space on the player beyond each theme's own skin files.

Made for 320×240 devices (EROS Q / EROS K native, iPod Video / 6G / Color, and others).

## License

Theme is MIT licensed. The bundled fonts are derived from [Inter](https://github.com/rsms/inter) and [Noto Sans SC](https://fonts.google.com/noto/specimen/Noto+Sans+SC), merged into a single typeface ("InTofu") where Inter covers Latin and Noto covers everything else; both remain under the SIL Open Font License (see `.rockbox/fonts/Inter-License.txt` and `.rockbox/fonts/Noto-License.txt`, and [fonts/README.md](fonts/README.md) for how they're built). Color palette by [Rose Pine](https://rosepinetheme.com/).
