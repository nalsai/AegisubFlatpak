# Aegisub Flatpak

> [!CAUTION]
>
> Aegisub is now on Flathub (<https://flathub.org/apps/org.aegisub.Aegisub>).  
> Therefore this repository is no longer maintained.

📦 Flatpak Package of Aegisub for Linux

Aegisub is a free, cross-platform open source tool for creating and modifying subtitles. Aegisub makes it quick and easy to time subtitles to audio, and features many powerful tools for styling them, including a built-in real-time video preview.

This is the fork by wangqr packaged as a flatpak: <https://github.com/wangqr/Aegisub/>  
You can find the upstream version here: <https://github.com/Aegisub/Aegisub/>

## Installing

I'm hosting this Flatpak on my own Flatpak Repo. You can install it from there like this:

```bash
flatpak install https://flatpak.nils.moe/repo/appstream/org.wangqr.Aegisub.flatpakref
```

You also need to install the ffmpeg-full extension:

```bash
flatpak install flathub org.freedesktop.Platform.ffmpeg-full//22.08
```

## Building

```bash
flatpak install flathub org.freedesktop.Platform.ffmpeg-full//22.08
flatpak-builder --install-deps-from=flathub --force-clean build-dir org.wangqr.Aegisub.yml
```

## Update shared-modules

```bash
git submodule update --remote --merge
```
