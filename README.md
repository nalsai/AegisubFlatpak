# Aegisub Flatpak

📦 Flatpak Package of Aegisub for Linux

Aegisub is a free, cross-platform open source tool for creating and modifying subtitles. Aegisub makes it quick and easy to time subtitles to audio, and features many powerful tools for styling them, including a built-in real-time video preview.

This is the fork by wangqr packaged as a flatpak: <https://github.com/wangqr/Aegisub/>
You can find the upstream version here: <https://github.com/Aegisub/Aegisub/>

There is also an old upstream version with some patches packaged as a flatpak.
This is not affiliated with it and completely made from scratch.

Differences compared to <https://github.com/scx/aegisub-flatpak>:

- fully based on wangqr fork (<https://github.com/wangqr/Aegisub>)
- more up to date dependencies
- latest freedesktop runtime (21.08) instead of old gnome (3.34)
- follows gtk theme on gnome if available for flatpak
- smaller size (bundle: 12MB vs 82MB)
- can actually be built

## Known issues

- Weird issues with some video/audio files (bad quality, out of sync), also happens for me when built from source (<https://github.com/wangqr/Aegisub>), from the AUR: aegisub-git (<https://github.com/Aegisub/Aegisub>) and in the package on RPM Fusion

- Aegisub uses the default Adwaita theme on KDE

Let me know if you can help or have any other issues: <https://github.com/Nalsai/AegisubFlatpak/issues>

## Installing

I'm hosting this Flatpak on my own Flatpak Repo. You can install it from there like this:

```bash
flatpak install https://flatpak.nils.moe/org.wangqr.Aegisub.flatpakref
```

You also need to install the ffmepg extension:

```bash
flatpak install flathub org.freedesktop.Platform.ffmpeg-full//21.08
```

## Building

```bash
flatpak-builder --install-deps-from=flathub --force-clean build-dir org.wangqr.Aegisub.yml
```

## Update shared-modules

```bash
git submodule update --remote --merge
```
