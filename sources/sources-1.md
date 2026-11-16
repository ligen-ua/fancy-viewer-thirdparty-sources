# Sources release sources-1

<!-- fingerprint: 86a3941e1378296374cec0b8dbbdc5071ebd88d87716a06150fa9fe1722af101 -->

Release: [sources-1](https://github.com/ligen-ua/fancy-viewer-thirdparty-sources/releases/tag/sources-1), asset `fancy-viewer-lgpl-sources-1.7z`. The Fancy Viewer versions that ship these sources are listed in [VERSIONS.md](../VERSIONS.md).

## ImageMagick build

| Checkout | Repository | Tag | Commit |
|---|---|---|---|
| ImageMagick | https://github.com/ImageMagick/ImageMagick.git | 7.1.2-34 | `a0c4bf729a26a5c2feb28b0365b47a8db736078a` |
| Dependencies | https://github.com/ImageMagick/Dependencies.git | 2026.10.30.1106 | `33692e2e4acb092bcd7c55dc85077521af3e18bf` |
| Configure | https://github.com/ImageMagick/Configure.git | 2026.10.29.1902 | `d3772cc2878efd62e7caddf47c0d7081d05d2abe` |

Configure options: `/dynamic /Q16 /hdri /openCL /includeOptional /VS2022 /noWizard (per arch: /x64, /x86)`.
Local changes, applied before building: `patches/fancy-viewer-configure.patch` (in `Configure`: Windows 7 target for every library except cairo) and `patches/fancy-viewer-cairo.patch` (in cairo: thread-local storage on older MSVC).

## LGPL / MPL libraries shipped as DLLs

| Library | License | Repository | Commit |
|---|---|---|---|
| cairo | MPL-1.1 | https://github.com/ImageMagick/cairo.git | `4334da83d8f44abe5aab1a11956e3f8e6e58eac7` |
| croco | LGPL-2.0-or-later | https://github.com/ImageMagick/croco.git | `178785cdc6faecad555a4e6fe4fda2b625046e8e` |
| de265 | LGPL-3.0-or-later | https://github.com/ImageMagick/de265.git | `5a0bf9f624d810de6af20e41ac3cfd92bf7de508` |
| fribidi | LGPL-2.1-or-later | https://github.com/ImageMagick/fribidi.git | `a51f6765d9bfafab1f7bd3f5f507ccf1eac6be6b` |
| gdk-pixbuf | LGPL-2.1-or-later | https://github.com/ImageMagick/gdk-pixbuf.git | `92a234886a0337480770ef93dc74ea920bf39ab3` |
| glib | LGPL-2.1-or-later | https://github.com/ImageMagick/glib.git | `ea0118ca0d408473d320b21262a1cdc6ce3e5f40` |
| heif | LGPL-3.0-or-later | https://github.com/ImageMagick/heif.git | `498042a72e805c50e5e84b57e15327f3cfdf6a63` |
| lqr | LGPL-3.0-or-later | https://github.com/ImageMagick/lqr.git | `a2e9e8b5b41bf0569f51482707a12d354a086f3a` |
| lzma | LGPL-2.1-or-later | https://github.com/ImageMagick/lzma.git | `131e9a49425f51b8dd8710c57fbaa527baed3989` |
| pango | LGPL-2.0-only | https://github.com/ImageMagick/pango.git | `0b1e4536e0005f3c36b523c17ea12322490efd45` |
| raw | LGPL-2.1-or-later | https://github.com/ImageMagick/raw.git | `71399d76efc3fa915bf3fb01ddede994b549a80a` |
| rsvg | LGPL-2.0-or-later | https://github.com/ImageMagick/rsvg.git | `7415a6765db7554ba6f0f1b3dcb0877f36ff581b` |

Each DLL is `CORE_RL_<library>_.dll` next to `FVHost.exe` and can be replaced by your own build of the same library and version.
