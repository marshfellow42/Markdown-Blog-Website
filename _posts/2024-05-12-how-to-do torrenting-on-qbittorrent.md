---
layout: post
title: How to do torrenting on qBittorrent
categories: how-to
permalink: /how-to-do-torrenting-on-qbittorrent/
---

This guide was specifically made for qBittorrent, but the process must be similar to other torrent clients like Transmission or Deluge

## Installing the Torrent Client
Go to this <a href="https://www.qbittorrent.org/download" target="_blank">website</a> and install it according to your operational system

## Setting up your own tracker
This is for using your own internet as a tracker without depending on public trackers

1. Go to qBittorrent settings
2. Go to Advanced
3. Enable the option ```Enable embedded tracker```
4. Go to your router settings
    - To find it, go to your terminal
        - If it's Windows, type ```ipconfig```
        - If it's Linux, type ```ifconfig```
    - Find the Default Gateway of your network
        - It depends if you're using cable or Wi-Fi
    - Type the Default Gateway IPV4 address on your browser
5. Port Foward the port ```9000``` to ```TCP```
    - To check if the port ```9000``` is open, go to this <a href="https://www.yougetsignal.com/tools/open-ports/" target="_blank">website</a>

## Uploading the torrent files
1. Go to ```Tools```
2. Enter on ```Torrent Creator```
3. Input the path for your file/folder
4. Leave everything as default
5. Check ```Start seeding immediately```
6. Check ```Ignore share ratio limits for this torrent```
7. The Tracker URL should be ```http://your_public_ip:9000/announce```