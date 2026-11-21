# Third-party notices

VitaSim is closed source, apart from the parts below. The licences' full texts are in [`LICENSES/`](LICENSES/).

## Linked libraries

### vitaGL and vitaShaRK: GNU LGPL 3.0

[vitaGL](https://github.com/Rinnegatamante/vitaGL) (commit 3dddc43, built without its startup splash screen through
its own `NO_SPLASHSCREEN=1` build option, otherwise unmodified) and [vitaShaRK](https://github.com/Rinnegatamante/vitaShaRK)
(v1.5, as packaged by the VitaSDK) by Rinnegatamante, statically linked. Licences:
[`LICENSES/LGPL-3.0.txt`](LICENSES/LGPL-3.0.txt), which builds on [`LICENSES/GPL-3.0.txt`](LICENSES/GPL-3.0.txt).

### pthread-embedded: GNU LGPL 2.1

[pthread-embedded](https://github.com/vitasdk/pthread-embedded) (from Pthreads-win32), as built by the VitaSDK,
statically linked. Licence: [`LICENSES/LGPL-2.1.txt`](LICENSES/LGPL-2.1.txt).

### What each release carries for these libraries

- `VitaSim-vX.Y.Z-lgpl-sources.zip`: the complete source of vitaGL, vitaShaRK and pthread-embedded as linked into
  that release, with the commits and build options.
- `VitaSim-vX.Y.Z-relink-kit.zip`: the app's object files (not its source), the libraries as linked, the link
  command and the steps to make the eboot and the VPK, so you can rebuild the app with modified versions of
  these libraries. Relinked unchanged, it gives the released `eboot.bin` byte for byte.

### math-neon: MIT

[math-neon](https://github.com/andrepuschmann/math-neon). Licence: [`LICENSES/MIT-math-neon.txt`](LICENSES/MIT-math-neon.txt).

### Mbed TLS: Apache License 2.0

[Mbed TLS](https://github.com/Mbed-TLS/mbedtls), used for the update check over HTTPS. Licence:
[`LICENSES/Apache-2.0.txt`](LICENSES/Apache-2.0.txt).

### zlib: zlib License

[zlib](https://zlib.net/) by Jean-loup Gailly and Mark Adler. Licence: [`LICENSES/zlib.txt`](LICENSES/zlib.txt).

## In the engine

### minimp3: CC0 1.0

[minimp3](https://github.com/lieff/minimp3) by lieff, public domain (CC0 1.0). Licence:
[`LICENSES/minimp3-CC0.txt`](LICENSES/minimp3-CC0.txt).

### stb_truetype: public domain

[stb](https://github.com/nothings/stb) by Sean Barrett, used under its public-domain alternative (The Unlicense).

### JUnzip: public domain

[JUnzip](https://github.com/jokkebk/JUnzip) by Joonas Pihlajamaa, released into the public domain.

### CapUnlocker and CoreUnlocker80000H: MIT

The app's kernel module opens the Vita's fourth CPU core for the app's threads the way
[CapUnlocker](https://github.com/GrapheneCt/CapUnlocker) and CoreUnlocker80000H by GrapheneCt do: it hooks the
system's CPU mask check at the same place, only where the code there is the known one (read on firmware 3.65), and
gives it back when the app exits. Licence: [`LICENSES/MIT-CapUnlocker.txt`](LICENSES/MIT-CapUnlocker.txt).

### Niotso: ISC

The decoders for the game's object drawing groups (DGRP) and sprites (SPR2) follow the
[Niotso](https://github.com/daddesio/Niotso) FileHandler implementation (dgrp.c, the SPR2 reference) by Fatbag,
Niotso Project. Licence: [`LICENSES/ISC-Niotso.txt`](LICENSES/ISC-Niotso.txt).

## Certificates

The update check uses the Mozilla CA certificate list (`cacert.pem`, Mozilla Public License 2.0, from
[curl.se/docs/caextract.html](https://curl.se/docs/caextract.html)), shipped unmodified. Licence: [`LICENSES/MPL-2.0.txt`](LICENSES/MPL-2.0.txt).

## Fonts

### Comic Neue: SIL Open Font License 1.1

[Comic Neue](https://github.com/crozynski/comicneue) by Craig Rozynski and Hrant Papazian, shipped unmodified in the
app. Licence: [`LICENSES/OFL-1.1-ComicNeue.txt`](LICENSES/OFL-1.1-ComicNeue.txt).

## The Sims

The Sims, its files and artwork are the property of Electronic Arts Inc. VitaSim contains none of them and is not
affiliated with or endorsed by Electronic Arts or Maxis.
