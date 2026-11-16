# Fancy Viewer: third-party sources

[Fancy Viewer](https://www.fancy-viewer.com/) is a free image viewer for Windows. It uses ImageMagick, and some of
the libraries ImageMagick loads are licensed under the GNU LGPL or the Mozilla Public License. They ship with
Fancy Viewer as separate DLLs. This repository provides their complete corresponding source code, including the
build changes made for Fancy Viewer, for every Fancy Viewer version that was released.

Fancy Viewer itself is freeware and not open source; its own source code is not part of this repository.

## Where to find the source for your version
The libraries change only when ImageMagick is updated, so many Fancy Viewer versions share the same sources.
Each set of sources is one **release**, tagged `sources-<N>` (for example `sources-1`):

1. Find your Fancy Viewer version (it is in the installed `thirdparty.txt`, which also links to its release)
   in [`VERSIONS.md`](VERSIONS.md). It names the sources release that version ships.
2. The release has `fancy-viewer-lgpl-sources-<N>.7z`: the source of every LGPL/MPL library in that build,
   exactly at the commit that was built, plus ImageMagick's `Configure` tool and the patches below.
3. Its manifest, [`sources/sources-<N>.md`](sources/), lists repository URLs, commits, licenses and build
   options.

## Patches
Applied before building, in [`patches/`](patches/):

- `fancy-viewer-configure.patch` (in `Configure`): targets Windows 7 instead of Windows 10 for every library
  except cairo.
- `fancy-viewer-cairo.patch` (in cairo): uses Windows TLS functions instead of C11 `_Thread_local` on MSVC
  older than 17.8.

## Rebuilding a library
The libraries are built with ImageMagick's Windows build system (https://github.com/ImageMagick/Windows):

1. Clone `ImageMagick`, `Configure` and `Dependencies` at the commits in `sources/sources-<N>.md`, or unpack the
   archive. Apply the patches.
2. Build `Configure` (Visual Studio 2022, toolset v143) and run it with the options in the manifest.
3. Build the generated `IM7.Dynamic.<arch>.sln` in Release.
4. Replace `CORE_RL_<library>_.dll` next to `FVHost.exe` in the Fancy Viewer folder with your build.

## Contact
developers@fancy-viewer.com
