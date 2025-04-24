---
title: "Bike Phone Mount/Holder"
excerpt: "A project for our CHBE 4200 class at Vanderbilt University that focuses on CADing a Bike Phone Mount using Top-Down Modeling Approach"
header:
  overlay_image: "/assets/img/phoneholder/Front_Render.jpg"
  overlay_filter: 0.5
  teaser: "/assets/img/phoneholder/Back_Render.jpg"

categories:
  - Engineering
  - Additive Manufacturing
tags:
  - CAD
meta: "April 10, 2025"

gallery:
  - image_path: /assets/img/phoneholder/Landscape.jpeg
  - image_path: /assets/img/phoneholder/Portrait.jpeg

toc: true
toc_label: "Table of Contents"
toc_sticky: true
toc_icon: bars

type: Outside Projects
---

A 3D-Printed Phone Holder for Bike Handlebars designed for securely mounting a phone on a bicycle handle.

# Top-Down Modeling Approach
In my design, I used top-down modeling to slowly build the bike phone mount from the clamp base to the phone holder component. 

## Overview of top-down modeling
Top-down modeling is where you design the system from the top level/full assembly and then define each subcomponent based on that. Instead of building individual parts and jointing everything at the end, you can create the design in one file and use a built-in joint to stick everything together.

## How it was applied to this project
Top-down modeling allowed for easier parametric modeling by using projections and variables in a single Fusion file. Establishing a good parametric model allows the design to be easily changed without scrolling through the timeline and editing a feature. In my design, if one part of the design changes, the entire design will also change to accommodate the part.

# Design Rationale
For my design, I tried to create the most modular design possible to prevent reprinting the entire design saving on time and materials.

## Rotation Mechanism
The rotation mechanism I chose was the detent mechanism and overall it worked pretty well. The detent mechanism smoothed out the motion of turning the phone from landscape to portrait and prevented the mechanism from rotating by itself.

## Material & Printing Process
I used SLS printing for this design because it preserves complex features that FFF printing might fail with. The material used for SLS printing is PA12 (nylon), which has stronger properties than PLA, preventing structural failures.

# Assembly & Usage Instructions

## Step-by-step guide for assembly

I separated my bike phone mount into six parts/components:
* Clamp Base Component
  * Purpose: To clamp onto the bike handlebars
  * Attachment: Clamped on the bike handlebars using screws and hex nuts
* Rotator Component
  * Purpose: Base of the divot mechanism (spring, ball bearing)
  * Attachment: Screwed onto the Clamp Base Component by either heat inserts or hex nuts
* Rotate Plate Component
  * Purpose: Rotates using the divot mechanism
  * Attachment: Screwed onto the Clamp Base Component by either heat inserts or hex nuts
* Phone Holder Base Component:
  * Purpose: The base of the phone holder clamp mechanism
  * Attachment: Screwed onto the Rotate Plate Component by heat inserts on the sides of the Phone Holder Base Component
* Stationary Phone Holder Component:
  * Purpose: To hold the phone 
  * Attachment: Screwed onto the Phone Holder Base Component by heat inserts on the base
* Adjustable Phone Holder Component:
  * Purpose: To clamp onto the phone
  * Attachment: Screwed onto the side of the Phone Holder Base component by heat inserts to change the width of the phone holder

## How to attach and use the holder
After assembling the entire design: 
1. Clamp the bike phone mount onto the handlebars by tightening the hex nuts
2. Place your phone into the phone holder and tighten it
3. Orient your phone based on your preference

# Printing Technology & Choices
For all the parts, I used SLS printing to print them because it preserves complex features and is stronger than FFF printing. The design has to be strong enough for it to be able to hold a phone and survive a crash, so Nylon is the preferred material over PLA because Nylon has better strength properties than PLA.


# Interactive CAD Model
<iframe src="https://vanderbilt643.autodesk360.com/shares/public/SH286ddQT78850c0d8a445bece538406afd4?mode=embed" width="640" height="480" allowfullscreen="true" webkitallowfullscreen="true" mozallowfullscreen="true"  frameborder="0"></iframe>

<br>

# Multimedia
{% include gallery caption="Model In Use" %}

![inAction](/assets/img/phoneholder/Action.gif){: .align-center}
*GIF of rotation mechanism in action*
{: .text-center}

![Cast](/assets/img/phoneholder/Back_Render.jpg){: .align-center}{: .figures}

![Cast](/assets/img/phoneholder/Front_Render.jpg){: .align-center}{: .figures}
*High-quality Fusion 360 rendering with phone*
{: .text-center}

![Cast](/assets/img/phoneholder/Internal_Mechanism.png){: .align-center}{: .figures}
*Cross-section view of detent mechanism*
{: .text-center}