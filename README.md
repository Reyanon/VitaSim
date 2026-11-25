<p align="center">
  <img src="vita/vitasim-logo.png" width="420" alt="VitaSim">
</p>

<div align="center">
  <video src="https://github.com/user-attachments/assets/c03520a9-d736-4b85-93a1-ac1cd0078a6a" controls width="720"></video>
  <p><a href="https://youtu.be/OS17Av9fnv4">Watch on YouTube</a></p>
</div>

<br>

<div align="center">
  <img width="960" height="544" alt="2026-11-24-173219_1" src="https://github.com/user-attachments/assets/917b311f-223a-4421-afa4-1e17489b7be2" />
</div>

<h1 align="center">VitaSim</h1>

<p align="center">
  <b>A life simulation engine for PlayStation Vita, compatible with The Sims Legacy Collection</b><br>
  clean-room C99 &middot; SimAntics interpreter &middot; isometric renderer on vitaGL &middot; all expansion packs
</p>

---

> The VitaSim logo is an original design inspired by The Sims. VitaSim is a fan project. It is not affiliated
> with, endorsed or sponsored by Electronic Arts or Maxis. The Sims is a trademark of Electronic Arts Inc.
> VitaSim contains no game files. To play, buy **The Sims Legacy Collection** on Steam or the Epic Games Store
> and copy your own installed files to the Vita.

## Table of Contents

1. [Introduction](#1-introduction)
2. [Status](#2-status)
3. [Requirements](#3-requirements)
4. [Installation](#4-installation)
5. [Controls](#5-controls)
6. [Known Issues](#6-known-issues)
7. [License and Credits](#7-license-and-credits)
8. [Support](#8-support)

---

## 1. Introduction

VitaSim is a new engine, written from scratch for the PS Vita, that plays The Sims (2000) from the files of your
own copy of The Sims Legacy Collection. It aims to look and behave as closely as possible to the original PC game.

Two interfaces, switchable at any time in Settings > Basic (chosen on the first start, with a preview of both):

- **VitaSim UI** - a touch-first interface made for the Vita's screen: large buttons on the screen edges, status
  panels that can become movable windows, a fast item shelf for Buy and Build mode (categories, favourites,
  recent items, custom content, eyedropper, place again) and an eye button that hides the interface.
- **Original** - the original screens drawn 1:1 at 800x600 on the Vita's 960x544 display with a scrollable lot view.

Both are controlled with the Vita's buttons, sticks and touch screen.

## 2. Status

Playable from the neighbourhood through every expansion pack's areas (Downtown, Vacation Island, Old Town,
Studio Town, Magic Town), with live, buy and build modes, Create-A-Family, the family bin, the photo album,
saving and loading.

- 60 fps by default (30 fps can be chosen in Options > Graphics), using all four CPU cores.
- 16 languages: English, French, German, Italian, Spanish, Dutch, Danish, Swedish, Norwegian, Finnish,
  Portuguese, Polish, Japanese, Korean, Simplified Chinese and Traditional Chinese. Japanese and Chinese use the
  Vita's system font; text the game has no translation for is shown in English.
- The app checks GitHub for new releases and can update itself.

This is a work in progress: see [Known Issues](#6-known-issues).

## 3. Requirements

- A PS Vita with HENkaku / Ensō and VitaShell.
- `ur0:data/external/libshacccg.suprx` (the runtime shader compiler used by vitaGL).
- **The Sims Legacy Collection**, bought on Steam or the Epic Games Store (not included). The Complete Collection and other editions are
  not supported.
- About 2.5 GB free on the memory card for your installed files.

## 4. Installation

1. Download `VitaSim_vX.Y.Z.vpk` from the [latest release](../../releases/latest) and install it with VitaShell. **You only need the VPK**: the release's `lgpl-sources` and `relink-kit` zips are there for the LGPL licence of vitaGL / vitaShaRK (see [NOTICES.md](NOTICES.md)).
2. Copy the files of your own Legacy Collection installation (for example
   `C:\Program Files (x86)\Steam\steamapps\common\The Sims Legacy Collection`) to `ux0:data/vitasim/` on the
   Vita, keeping the folder layout: `GameData`, `UIGraphics`, `SoundData`, `Music`, `ExpansionShared`,
   `ExpansionPack` ... `ExpansionPack7`, `Downloads`, the `Template*` folders and `UserData`
   (`UserData2` ... `UserData8` for the other neighbourhoods). `Sims.exe` is not needed.
3. Start VitaSim. The first start builds a few caches and takes longer.

### Fonts (optional, for the original look)

The original game draws part of its text with Windows fonts, which cannot be distributed. Without them VitaSim uses
a free stand-in (Comic Neue, SIL OFL 1.1) and the Vita's own system fonts, so every language works out of the box.
For the original look, copy these files from the `C:\Windows\Fonts` folder of a Windows PC you own to
`ux0:data/vitasim/Fonts/` (create the folder):

| Language | Files | Used for |
|---|---|---|
| All languages | `comic.ttf` (Comic Sans MS) | buttons, labels, most of the interface |
| All languages | `times.ttf`, `cour.ttf`, `lucon.ttf` (Times New Roman, Courier New, Lucida Console) | the few screens that use them |
| Korean | `gulim.ttc` (Gulim) | all Korean text; VitaSim reads its built-in 13-pixel bitmaps, exactly like the original |
| Japanese | none | always drawn with the Vita's Japanese system font |
| English, French, German, Italian, Spanish, Dutch, Danish, Swedish, Norwegian, Finnish, Portuguese, Polish | none beyond the first two rows | most text comes from the game's own bitmap fonts |

Restart VitaSim after copying.

### Custom content (optional)

Custom objects, skins, walls and floors (CC) go into `ux0:data/vitasim/Downloads/`, as on the PC: copy your PC game's
`Downloads` folder (subfolders are fine). The next start indexes them once; they then appear in Buy and Build mode.
With a large folder (thousands of files) the first start and the first lot take a few minutes; later starts are quick.
Hacks that replace game files go where their readme says (usually `GameData/Objects/` or `ExpansionShared/`), as on the PC.

Saves are written to `ux0:data/vitasim/UserData*` in the original format. Port settings are in
`ux0:data/vitasim/UserData/VitaOptions.txt`.

**Updating:** when a newer release is out, the app offers it on the neighbourhood screen (Install / Skip this
version / Later); Settings > Basic > Check for updates works on a lot too, and asks to save the game first. It
downloads the package, exits, and the update is in place the next time you start it.
You can also install the new VPK with VitaShell. Your saves and settings stay in `ux0:data/vitasim/`.

## 5. Controls

| Input | Action |
|---|---|
| Left stick / touch drag | Move the cursor / scroll the lot (assignable in Settings) |
| Cross | Click (confirm button; can be swapped with Circle in Settings) |
| Circle | Back / cancel |
| D-pad | Zoom and rotate (assignable); moves the highlight in menus and pie menus |
| L / R | Floor up-down / wall mode |
| Triangle / Square | Held modifiers for build tools (the original's Ctrl / Shift); Triangle sells the object in hand |
| SELECT | Next game speed |
| START | Pause |
| PS button (or SELECT + START) | Settings: language, controls, graphics, family helpers, cheats, About |

**Touch: direct or trackpad** (switch with the first button of the VitaSim UI's bottom bar, or in Settings > Controls).
Direct touch: tap and drag on the screen itself. Trackpad mode: one finger moves the cursor and taps to click,
two fingers right-click or drag to scroll, three fingers rotate (swipe left/right) and change floors (swipe
up/down); the interface's own buttons and panels stay direct touch. In both modes, pinch with two fingers to zoom.

**Bluetooth mouse and keyboard** (pair them in the Vita's settings; the keyboard is tested, the mouse not yet on a real device): the PC game's controls — right click, hold the
right button to scroll, wheel to zoom, F1-F5 modes, Ctrl+S to save, and typing in name fields.

In dialogs the confirm button answers OK / Yes and the back button No / Cancel.

## 6. Known Issues

VitaSim is a work in progress. Occasional short hitches remain, mostly in the first minute after a lot opens.

Please report problems on the [issue tracker](https://github.com/Reyanon/VitaSim/issues): what you did, on which lot,
and a screenshot if you can.

## 7. License and Credits

VitaSim is closed source. The parts by others and their licences are listed in [NOTICES.md](NOTICES.md); the
licence texts are in [LICENSES](LICENSES).

The Sims, its files and artwork are the property of Electronic Arts Inc. and are not part of this project.

## 8. Support

If you enjoy VitaSim, you can support its development on [Patreon](https://www.patreon.com/Reyanon) or Ko-fi:

<a href="https://ko-fi.com/reyanon"><img src="https://ko-fi.com/img/githubbutton_sm.svg" alt="Support me on Ko-fi"></a>
