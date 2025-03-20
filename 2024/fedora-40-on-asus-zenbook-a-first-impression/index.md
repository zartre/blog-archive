---
title: "Fedora 40 on Asus Zenbook: A First Impression"
date: 2024-06-16
categories:
  - "Thoughts"
tags:
  - "review"
  - "tech"
coverImage: "./images/asus-zenbook-fedora-laid-flat.webp"
public: true
---

I bought a used Asus Zenbook 14 (UM3402YA) for ฿19,000 ($523) because my MacBook Pro 2016 could no longer boot up due to a malfunctioned motherboard. This used Zenbook is in pristine condition. The battery is 89% in health.

<!--more-->

At first I was considering the ThinkPad T14/T14s because I loved the TrackPoint and the rugged yet premium build, and it seemed like Linux would fare better with ThinkPad hardware. I didn't want to spend a grand on a laptop that I would do light work on it so I looked at used ThinkPad, but I found only ThinkPad with 45% NTSC screen option. I knew I would not enjoy that.

This Zenbook popped up at the right time. It came with a 90 Hz OLED display with 99% DCI-P3 and HDR, and a lightweight, premium build.

I chose to run Fedora KDE on this laptop because I was more used to managing PATH and environments on \*nix systems. Privacy and customisability were also my considerations. Also, Windows 11 is just too cluttered and there's a lot of data collection.

# Hardware support

I installed Fedora right away and most things—the 90 Hz display, the keyboard, the keyboard backlight, the touchpad with multi-touch gestures, the camera, the speakers, the microphone, Wi-Fi and Bluetooth—worked right out of the box.

For the number pad, installing [asus-numberpad-driver](https://github.com/asus-linux-drivers/asus-numberpad-driver) made it work.

Sleeping works perfectly with no issues.

However, my Microsoft Bluetooth Mouse would not work. I could get it connect but it just kept blinking. The Keychron keyboard works fine. (At last I managed to get the mouse to connect properly by following this [guide](https://www.youtube.com/watch?v=J-6yq5RMFqA).)

~~Another caveat is that the fingerprint scanner on this laptop is not supported by [fprint]([https://fprint.freedesktop.org]\(https://fprint.freedesktop.org/\)). I was able to find a patch, though, but it has yet to be merged to the main release.~~

Update (Dec 2024): The fingerprint scanner has been working for some months now!

# Performance

Fedora 40 with KDE Plasma 6 is snappy on this machine. I use an M1 MacBook Pro for work and both laptops feel as snappy for my usage. Apps launch quickly. Web pages render quickly. Vite compiles in an instant for a small Svelte project that I'm working on.

This laptop doesn't have a discrete GPU so it relies on the APU of Ryzen 7530U with 512 MB GPU memory. Graphics performance is good both for the UI and 4K video playback. It can connect to a 4K monitor with no issue.

Here is the Geekbench result of this laptop [https://browser.geekbench.com/v6/cpu/6244562](https://browser.geekbench.com/v6/cpu/6244562)

# Power consumption

## On battery

Power consumption was a bit high at around 10 W when idle but after tuning with `tlp` it got better. Actually I didn't need to configure much. `tlp` did most of the tuning work but I also tuned it a little more to make some compromise for performance on battery.

The laptop draws 4-5 W when idle. With light usage (taking notes in Obsidian and browsing the Internet) it goes to 5-7 W. The display takes 1 more Watt when set to 90 Hz.

## On AC

When plugged in it's a different experience. The fan spins up and the laptop gets warmer than on battery even with the same usage. It's not hot but warmer.

# Summary

It's been a month now that I have been using this laptop as my personal daily driver. Overall I'm enjoying Linux on this laptop, especially the customisability and the programming experience.

The out-of-the-box experience was better than I'd expected. Surely, it doesn't match that of macOS and Windows in terms of user experience, especially in power management, but it's a clean and usable OS that will get your job done. Privacy wise, Linux can't be a wrong choice.
