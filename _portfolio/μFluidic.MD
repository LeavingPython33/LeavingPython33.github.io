---
title: "μFluidic Device"
excerpt: "A project for our CHBE 4200 class at Vanderbilt University that focuses on sorting different small particles with no moving parts"
header:
  overlay_image: "/assets/img/PlasmaClose.jpeg"
  overlay_filter: 0.5
  teaser: "/assets/img/ModelDevice.jpeg"

categories:
  - Engineering
  - Additive Manufacturing
tags:
  - CAD
  - Resin-Printing
meta: "January 12, 2025"

gallery:
  - image_path: /assets/img/syringe/image3.png

toc: true
toc_label: "Table of Contents"
toc_sticky: true
toc_icon: bars
---

# Introduction

## What are μFluidic Devices?
A μfluidic (microfluidic) device is like a circuit board for liquids, designed to precisely control and manipulate small volumes of fluids, often at the micrometer scale. These devices use a network of tiny channels, valves, and pumps to direct fluid flow, similar to how electrical circuits control the movement of electrons. Microfluidic devices are widely used in medical diagnostics, DNA sequencing, tissue engineering, and environmental testing.

## What is pinch flow fractionation? 
Pinch Flow Fractionation (PFF) is a microfluidic technique used to separate particles based on their size by estimating the particles position through a narrowing (pinch) region. In a PFF device theres two inlet channels, one carrying the particles and another acting as a sheath flow—merge and enter a pinch region. The sheath flow directs smaller particles closer to the channel walls while larger particles remain near the center due to their larger size. At the end of the PFF device there's multiple outlet channels that collects the separated particles based on their flow trajectories and for the sheat flow. PFF can be used for isolating and analysing biological particles such as cells, viruses, and extracellular vesicles.

## Application of μFluidic Device Sorting
μFluidic are used for for clinical and therapeutic applications. Microfluidic sorting allows for the separation of specific cell populations, which is important for cell therapy. In this <a href = "https://www.bioprocessintl.com/cell-therapies/microfluidic-cell-sorting-scaling-for-clinical-and-therapeutic-applications
">Article</a> they used Microfluidic sorting to separate and recover stem cells from bonemarrow aspirates for the purpose of manufacturing stem cell therapy. Stem cell therapy is a medical treatment that uses stem cells to repair or replace damaged or diseased tissues.

# Instructions

## CAD Model
The PFF is designed based on the given particle sizes, as it's used to determine where the outlet channels should be positioned at. For CADing the pinch and broad region, it's preferable to have a big ratio between them for effective sorting. The height of channels shouldn't be too big that particles start to stack, inhibiting the sorting process. The outlets should have similar flow rate to prevent the potential of back flow, where a big particle might get sucked in to a high flow rate small particle outlet channel. The flow rate of a channel is determined by its length and width.

<iframe src="https://vanderbilt643.autodesk360.com/shares/public/SH286ddQT78850c0d8a45ceaf2e7a763d7e6?mode=embed" width="640" height="480" allowfullscreen="true" webkitallowfullscreen="true" mozallowfullscreen="true"  frameborder="0"></iframe>

<br>
For my CAD model I created the biggest broad region possible and the smallest pinch possible to create a big ratio for effective sorting. To ensure equal flow rate I created outlets with different width and length to prevent potential backflow.

## Print and Cure Mold
The PFF should be printed on a resin printer to ensure the small channels are preserved from the CAD model

Desired Printer Specifications:
* Laser Spot Size (i.e., Minimum Feature Size): 85 μm
* Minimum XY Resolution: 25 μm
* Minimum Z Resolution: 25 μm
* Build volume: (145 × 145 × 185) mm

Post Processing Steps:
* Wash the device for 5 minutes on the print bed in the FormWash and then remove it from the bed and wash it for another 5 minutes in fresh IPA (the stationary bath to right of the FormWash). Do not exceed 15 total minutes of wash time as the resin can absorb the IPA.
* Let your device dry by leaning it upside down for 30 minutes before curing. Do not let the IPA pool inside the device while drying. Confirm that the inside of the mold has a homogenous sheen. Glossy areas indicate that uncured resin is still present, which will inhibit the crosslinking of PDMS.
* DO NOT TOUCH THE INSIDE OF UNCURED MOLD. Using your finger or paper towel to remove uncured resin will increase the surface roughness of the mold. This roughness will transfer to the PDMS device, likely causing sealing issues.
* Gently blow off any debris between your μFluidic’s channels. With safety glasses on, use compressed air to dislodge any foreign particles/resin that may have been picked up during the washing step.
* Perform a 60 second surface cure with supports on. Curing the model for long durations can cause it to warp. Further, the mold does not require robust mechanical properties to function. Therefore, we will cure either the black or high-temp resin for 60 seconds at room temperature (no heat).
* Remove support material. Once again be careful not to touch the inside of the mood.


![Resin Print](/assets/img/ModelDevice.jpeg){: .align-center}{: .figures}

*Resin Print of PFF Device*
{: .text-center}

## Parylene Device
The PFF mold must be coated with a protective layer because the resin could leech into the cast PDMS causing incomplete features and curing.

The solution is parlyene coating process. The parylene coating process is a way to apply a very thin, protective layer to 3D printed parts. 

The Parylene Process:
1. Clean the 3D print: The part is cleaned to remove dust or oils.
2. Place in a vacuum chamber: The 3D print goes into a special vacuum chamber.
3. Vaporize the parylene: Parylene is heated and turned into a gas inside the chamber.
4. Coating forms: The gas cools and forms a thin, even layer on the 3D print.
5. Solidify: The coating hardens, creating a protective surface.

## Cast PDMS
For casting the mold we use Polydimethylsiloxane (PDMS), which is an elastomeric (i.e., rubber-like) thermoset that is mixed together and poured into the mold.

PDMS Steps
* SYLGARDTM 184 Silicone Elastomer (10:1 mix ratio)
* Heat cure times:
* 24 hours at 23°C, or 4 hours at 65°C, or 1 hour at 100°C, or 15 minutes at 150°C
* Please note: clear resin (Form 4) will crack at 100C

![Cast](/assets/img/Mold.jpeg){: .align-center}{: .figures}

*Cast of PFF Device*
{: .text-center}

## Plasma Bond Glass Slide
The microfluidics needs a glass slide wall to allow viewing of the sorting process. However, glass is very inert and glue is a viable option, as it can fill the features.

The solution is Plasma bonding. Plasma bonding glass slides is a process that uses plasma (ionized gas) to make glass reactive and bond to other materials.

The Plasma Bonding Glass Slide Steps:
1. Clean the glass slide to remove dirt, oils, or contaminants using a solvent like isopropyl alcohol.
2. Place the glass slide inside a plasma chamber.
3. Activate the plasma by applying high voltage to gas (like oxygen or air) in the chamber, turning it into plasma.
4. The plasma reacts with the glass surface, etching it and increasing its surface energy for better adhesion.
5. After plasma treatment, the glass is ready to bond with other materials, as the surface is now cleaner and more reactive.
6. Press the glass onto the microfluidic device cast.

![Plasma](/assets/img/Plasma.jpeg){: .align-center}{: .figures}

*Plasma Cleaner*
{: .text-center}
<br>

![Plasma Close Shot](/assets/img/PlasmaClose.jpeg){: .align-center}{: .figures}

*Plasma Bonding Process*
{: .text-center}

## Testing

Placeholder

# Discussion

> **Why are resin-printed molds coated with parylene prior to casting the PDMS?**
>
> Uncured resin monomers can leach out of the printed device interfering the crosslinking of PDMS, which leads to incomplete curing.

> **What are hypothetical applications of your microfluidic mixer or sorter?**
> 
> My microfluidic sorter can be used to sort blood sample for analysis or uses of specific cells. Certain cells in the blood stream can be used for therapies for people who lack in a specific cell type like stem cell therapy.

> **Why is your geometry conducive to sorting? Discuss specific dimensions (pinch width, outlet width, location of ports, etc.)**
> My Chosen Geometry:
> * Broad Width: 19mm
> * Pinch Width: 0.6mm
> * Three Outlet Ports in a triangle formation with varying paths and width
> * Two Inlet Ports with a width of 1.5mm
> 
> My chosen geometry is conductive to sorting, as it has a big ratio between the broad and pinch width promoting better PFF sorting. The outlets have varying paths and width to stop the issue of flow imbalances between the outlets. However, all the paths have the same path length which is about 19mm. The outlet width is determine by the size of the particle, as the big particle is about 2.5 times bigger than the smaller particle, so the outlet for the big particle should be 2.5 times bigger.

> **Based on the results of testing, could you implement any future changes to improve sorting?**
>
> Based on my results of testing, I would make the beginning of the broad width shorter to prevent eddy currents. In my testing there was signs of eddy currents as some small particles kept moving around in circles which slowed down the sorting process. Unfortunately the testing for my PFF ended short, as there was a leak between the glass slide and cast.

> **Did you attempt the bonus opportunity? If so, describe your approach and success.**
>
> I didn't attempt the bonus opportunity