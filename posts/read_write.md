---
categories:
- linux
date: '2024-09-11'
description: Read Write Benchmarking for different filesystems
layout: post
title: Read Write Benchmarking
toc: true
---

# General

## Commands

Device info:
    Try: `sudo smartctl -d megaraid,0 -a /dev/sdX` where `sdX` is the device name. (worked in Ramanujan)
    Else Try: `sudo smartctl -i /dev/sdX` where `sdX` is the device name. (worked in Sustain)
    For NAS: Checked in GUI

Device partitions:
    Try: `lsblk -o NAME,FSTYPE,SIZE,MOUNTPOINT,LABEL,MODEL` to list all partitions.

## Filesystems

| Server            | Device Model                 | Type | Rotation rate (rpm) | SATA version                 | Speed  | Capacity |
| ----------------- | ---------------------------- | ---- | ------------------- | ---------------------------- | ------ | -------- |
| Ramanujan         | INTEL SSDSC2KB076T8          | SSD  | -                   | SATA 3.2                     | 6 Gb/s | 7.68 TB  |
| Sustain (Samsung) | Samsung SSD 860 EVO 250GB    | SSD  | -                   | SATA 3.2                     | 6 Gb/s | 250 GB   |
| Sustain (Seagate) | Seagate ST1000NM0008-2F2100  | HDD  | 7200                | SATA 3.1                     | 6 Gb/s | 1 TB     |
| NAS               | Seagate ST18000NM000J-2TV103 | HDD  | 7200                | SATA but not checked version | 6 Gb/s | 16.37 TB |

# 1000 Images Test

## Unzip
Time taken to unzip 1000 images.

| Server                     | Time (s) | Comment                                                                     |
| -------------------------- | -------: | --------------------------------------------------------------------------- |
| Ramanujan                  |     12.9 |                                                                             |
| Sustain (Samsung)          |     12.0 |                                                                             |
| Sustain (Seagate)          |     12.4 |                                                                             |
| NAS (direct ssh)           |     12.8 |                                                                             |
| NAS (mounted on Ramanujan) |     54.1 | Tested with `sudo su` as well to make sure `sudo` isn't causing the problem |

## Transfer the 2.1 GB zip file from Server to NAS
19.8 seconds (~ 108 MB/s)