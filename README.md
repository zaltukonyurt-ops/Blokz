# BLOKZ

A mobile-first, Roblox-style 3D game platform that runs entirely in the browser — and now as an Android app.
Single-file HTML5 + [Three.js](https://threejs.org/) (r128), no server, fully offline once installed.

> **Disclaimer:** BLOKZ is an independent fan-made project. It is not affiliated with, endorsed by, or sponsored by Roblox Corporation.

## Features

- **Home dashboard** with friends row, game cards, avatar editor and shop
- **10 playable worlds** across different genres: horror hallway, roleplay town, shooter arena, obstacle course, natural disasters, bed defense, tornado survival and more
- **Bots and chat** — bot players roam each world and talk in the chat
- **Avatar shop** — hats, hair, shirts, jackets, pants and skin tones; purchases show up on the 3D character
- **Camera system** — smooth zoom, first-person view when fully zoomed in, and Roblox-style **Shift Lock**
- **Touch-friendly UI** — virtual joystick, jump and action buttons; works on phones and tablets (landscape recommended)
- **Desktop support** — keyboard and mouse, including pointer lock
- **Graphics** — PBR materials, day/night cycle, bloom, instanced vegetation, 4 quality levels
- **Progress is saved** locally (balance, owned items, settings)

## Install (Android)

1. Open the [latest release](../../releases/latest) on your phone or tablet.
2. Download `blokz.apk`.
3. Open the file and allow installing from this source when Android asks.
4. If Play Protect warns about the app, choose **Install anyway** (the APK is debug-signed).

Requires Android 7.0 (API 24) or newer.

## Controls

| Action | Touch | Keyboard / Mouse |
| --- | --- | --- |
| Move | Left joystick | `W` `A` `S` `D` / arrow keys |
| Look | Drag on screen | Mouse drag (or mouse move when locked) |
| Zoom | Pinch | Mouse wheel, `I` / `O` |
| First person | Zoom all the way in | Zoom all the way in |
| Shift Lock | Lock button | `Shift` |
| Jump | Arrow button | `Space` |
| Interact | Green button | `E` |
| Attack / fire | Attack button / tap | `F` / left click (when locked) |
| Sprint | Lightning button | `Q` |
| Reload | — | `R` |
| Chat | Chat button | `Enter` |
| Menu | Menu button | `Esc` |

**Shift Lock:** the cursor is locked to the screen center, the character always faces the camera direction, and the camera moves to the right shoulder. `Esc` opens the menu and releases the mouse. You can disable the `Shift` shortcut in Settings (then `Shift` becomes sprint).

## Build the APK

The Android project is a [Capacitor](https://capacitorjs.com/) wrapper around the game and is stored in `blokz-android.zip`.

**With GitHub Actions (no local setup):**
push to `main`, or run the **BLOKZ APK** workflow manually from the **Actions** tab. The workflow unpacks the project, builds a debug APK and publishes it as a release asset.

**Locally** (Node 22+, JDK 21, Android SDK):

```bash
unzip blokz-android.zip -d blokz-android
cd blokz-android
npm ci
npm run apk
# output: android/app/build/outputs/apk/debug/app-debug.apk
```

To update the game, replace `www/index.html` and run `npx cap sync android`.

## Tech

HTML5 · CSS3 · JavaScript · Three.js r128 · Web Audio · Capacitor 8 (Android)

## Status

Early prototype. Performance varies by device; if the game feels slow, lower **Settings → Graphics quality**.
