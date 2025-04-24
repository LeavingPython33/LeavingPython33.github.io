---
title: "HomeLab (Home server)"
excerpt: "Repurposed my old desktop into a homelab for the purpose of hosting my different services"
header:
  overlay_image: https://logovectorseek.com/wp-content/uploads/2021/10/proxmox-server-solutions-gmbh-logo-vector.png
  overlay_filter: 0.5
  teaser: https://vivid-cow-9924242169.media.strapiapp.com/cloudflare_bb657624dc.webp

categories:
  - Computer
  - VMS
tags:
  - IT
  - Proxmox
  - Cloudflare
meta: "January 12, 2025"

gallery:
  - image_path: assets/img/Tower_Pre.jpg
  - image_path: assets/img/Tower.jpg
  - image_path: assets/img/Tower1.jpg
  - image_path: assets/img/Tower2.jpg
  
toc: true
toc_label: "Table of Contents"
toc_sticky: true
toc_icon: bars

type: Personal Projects
---

# Features
* Create Virtual Machines (VMS) for any reason
* Able to access the Server from anywhere with an internet access, by using reverse proxy/tunnel
* Able to host different web services and servers like Minecraft servers, website pages, and homebrew google photos

# Cost and Time
The cost depends on whether you want to use your older desktops or build one for the purpose of running a home server. However, the most important components for the home server to run, is the CPU that can run VMs and have multiple cores. Another important component is the RAM, I recommend atleast or more than 32GB to run several VMs and services.

The amount of time in setting up the home server relies on whether you're tech savvy, as it requires a lot of navigating through bios and reading forums in solving your issues.

# Steps For Setting Up My HomeLab

## Setting Up The HyperVisor
The HyperVisor allows the user to create multiple VMs on a single system making the system more versatile.

The general steps in setting up a HyperVisor:

1. Wipe all the files on the old desktop
2. Install the HyperVisor OS on a thumbdrive (for my server I used ProxMox)
3. Plug the thumbdrive into the desktop and go into BIOs (Don't forget to activate CPU VMs!!!)
4. Boot up the thumbdrive OS
5. Follow the steps in setting up the HyperVisor onto the main drive (If you have a GPU disable it, as HyperVisor crash when interacting with GPUs)
6. After setting up the HyperVisor it will host a dashboard on the local network 
7. Use your own personal device to open the dashboard with the ip they provided

## General Steps for Creating VMs
There isn't any one way in creating VMs, as there's a lot of OS that need different specification. However, the first steps is to upload your osi to your HyperVisor.

## Setting Up The Reverse Proxy
If you aren't in one place at all times, you might want your home server accessible anywhere. However, exposing your local network to the internet can allow hackers to have access to your local network so we have to use reverse proxy services like Nginx and Cloudflare to protect yourself.

This YouTube Video shows how to open a reverse proxy with Cloudflare:

<iframe width="560" height="315" src="https://www.youtube.com/embed/ey4u7OUAF3c?si=vu0EMVXzkQwmT9Bo" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

But with anything involving exposing your network there comes with a risk, SO DO IT AT YOUR OWN RISK!!

# HomeLab Dashboards
This is the following information you'll find in your HyperVisor Dashboard:
* Server Specs
* Server Load
* VM Specs
* VM Load
* Network Traffic
* Storage
* Shell 

The information will help you diagnose or find any problem in your server. However, if you have a lot of different services with different ips and site name you'll have to create your own dashboard to easily navigate all of them. For my home server I use Homer to create a static webpage to easily access my home server services.

<img src="/assets/img/Homer.png" alt="Motor setup" style="width:500px;" class="figures"/>

*My Homer Dashboard*

# Whats Next
Currently I'm hosting Video Game servers, but I hope to host experimental websites that utilizes my server for the back-end of the websites.