---
layout: post
title: How to do torrenting on qBittorrent
categories: how-to
modified_date: 2024-05-19
---

This guide was specifically made for qBittorrent, but the process must be similar to other torrent clients like Transmission or Deluge

## Installing the Torrent Client
Download <a href="https://www.qbittorrent.org/download" target="_blank">qBittorrent</a> and install it according to your operational system

## My recommended approach to torrenting
<div class="alert-success">
✅ This approach is recommended if you prioritize privacy
</div>

<p></p>

I recommend going ```trackerless``` on the torrents you're hosting, and only depend on the DHT network

Because this way you aren't creating a single point of failure in case you suddenly change the IP address for your torrent or change ISPs

I recommend [Mullvad VPN](https://mullvad.net/en/vpn) if you want to start hosting torrents, because at the beginning there's gonna be a lot of uploading on your part, and you don't want your name to be related to that (especially not in North America). Afterwards it'll start to be more dissipated when more seeders start coming in. Because those seeders can maintain your torrent and you don't need to be that involved in the process anymore

## Setting up your own tracker
<div class="alert-danger">
⚠️ This approach is not recommended if you prioritize privacy
</div>

<p></p>

This is for using your own internet as a tracker without depending on public trackers

I also recommend [Mullvad VPN](https://mullvad.net/en/vpn) if you want to set up your own tracker, just so you don't have to share your public IP address with everyone by embedding on the tracker

1. Go to qBittorrent settings
2. Go to Advanced
3. Enable the option ```Enable embedded tracker```
4. Enable the option ```Enable port forwarding for embedded tracker```
5. Go to your router settings
    - To find it, go to your terminal
        - If it's Windows, type ```ipconfig```
        - If it's Linux, type ```ifconfig```
    - Find the Default Gateway of your network
        - It depends if you're using cable or Wi-Fi
    - Type the Default Gateway IPV4 address on your browser
6. Port Foward the port ```9000``` to ```TCP```
    - To check if the port ```9000``` is open, go to this <a href="https://www.yougetsignal.com/tools/open-ports/" target="_blank">website</a>

## Uploading the torrent files
1. Go to ```Tools```
2. Enter on ```Torrent Creator```
3. Input the path for your file/folder
4. Leave everything as default

If you have your own tracker, the Tracker URL should be ```http://your_public_ip:9000/announce```

Right after this, it'll start hosting on the DHT network

You're all set up now, you can start sharing as many torrents as you want, while maintaining privacy with a VPN

To know more about DHT, check this [article](https://www.maketecheasier.com/how-bittorrent-dht-peer-discovery-works/)