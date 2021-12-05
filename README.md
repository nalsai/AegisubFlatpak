# Aegisub Flatpak

📦 Flatpak Package of Aegisub for Linux

Aegisub is a free, cross-platform open source tool for creating and modifying subtitles. Aegisub makes it quick and easy to time subtitles to audio, and features many powerful tools for styling them, including a built-in real-time video preview.

This is the fork by wangqr packaged as a flatpak: https://github.com/wangqr/Aegisub/
You can find the upstream version here: https://github.com/Aegisub/Aegisub/

There is also an old upstream version with some patches packaged as a flatpak: https://github.com/scx/aegisub-flatpak
This is not affiliated with it and completely made from scratch.

## Differences compared to https://github.com/scx/aegisub-flatpak

- fully based on wangqr fork (https://github.com/wangqr/Aegisub)
- more up to date dependencies
- latest freedesktop runtime (21.08) instead of old gnome (3.34)
- looks nicer (follows gtk theme on gnome if available for flatpak)
- smaller size (bundle: 12MB vs 82MB)
- can actually be built

## Known issues

- Weird issues with some video/audio files (bad quality, out of sync), also happens for me when built from source (https://github.com/wangqr/Aegisub), from the AUR: aegisub-git (https://github.com/Aegisub/Aegisub) and in the package on RPM Fusion

- Aegisub uses the default Adwaita theme on KDE

Let me know if you can help or have any other issues: https://github.com/Nalsai/AegisubFlatpak/issues

## Installing

I'm hosting this Aegisub Flatpak on my own Flatpak Repo. You can install it from there like this:

```bash
flatpak install https://flatpak.nils.moe/org.wangqr.Aegisub.flatpakref
```
Or you can install it from the bundle in Releases on GitHub, but you won't get updates that way.

I want to submit Aegisub to Flathub too, but with the situation Aegisub is currently in, I'm not sure what to do.

## Building

### Install SDK and Platform

```bash
flatpak install flathub org.freedesktop.Sdk//21.08
flatpak install flathub org.freedesktop.Platform//21.08
```

### Build

```bash
flatpak-builder --repo=repo --force-clean build-dir org.wangqr.Aegisub.yml
```

### Make single-file bundle

```bash
flatpak build-bundle repo aegisub.flatpak org.wangqr.Aegisub stable --runtime-repo="https://flathub.org/repo/flathub.flatpakrepo"
```

## Update submodule (shared-modules)

```bash
git submodule update --remote --merge
```

