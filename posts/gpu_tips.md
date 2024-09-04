---
categories:
- gpu
- linux
date: '2022-04-15'
description: GPU related tips and tricks
layout: post
title: GPU CheatSheet
toc: true

---

## Xorg uses GPU memory

[StackOverFlow answer](https://askubuntu.com/a/1313440).

Solution: comment out everything in `/usr/share/X11/xorg.conf.d/10-nvidia.conf` and then restart the display manager with:
```
sudo systemctl restart display-manager
```

## `nvidia-smi` takes too long to load

One of the reasons could be that persistence mode is disabled. To enable it, run:
```
sudo nvidia-smi -pm 1
```

