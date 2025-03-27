---
title: "MultiMaterial-Pliers"
excerpt: "A project for our CHBE 4200 class at Vanderbilt University that focuses on creating print-in-place multimaterial tools"
header:
  overlay_image: "/assets/img/plier/Final.JPG"
  overlay_filter: 0.5
  teaser: "/assets/img/plier/Final.JPG"

categories:
  - Engineering
  - Additive Manufacturing
tags:
  - CAD
  - FDM
meta: "March 27, 2025"

gallery:
  - image_path: /assets/img/plier/FirstIteration.JPG
  - image_path: /assets/img/plier/LongHandles.jpg
  - image_path: /assets/img/plier/Final.JPG

toc: true
toc_label: "Table of Contents"
toc_sticky: true
toc_icon: bars
---

# Project Overview
This project showcases a fully 3D-printed, print-in-place pliers design that requires no special tools to assemble. Print-in-place technique allow for detailed mechanisms, such as hinges, gears, and springs, to be printed in one job without post-processing. It also allows for the mechanisms to be encased which wouldn't be possible without the print-in-place technique.

Print-in-place designs have been used in various applications, including:
* Articulated toys (e.g., flexi dragons, snakes, octopus)
* Mechanical tools (wrenches, pliers, adjustable clamps)
* Mechanical demonstration (gears, bearings, joints)
* Household items (foldable hinges, bottle openers)

For a succesful Print-in-place job, you have to carefully consider the material selected to ensure smooth movement, durability, and minimal post-processing. The best materials depends on the type of mechanism (hinges, gears, springs, etc.) and whether you're using a single material or multi-material printing.

**Most Popular Material for FFF**
1. PLA (Polylactic Acid)
    * ✅ Pros: Easy to print, rigid, good for gears and interlocking parts
    * ❌ Cons: Brittle over time, poor flexibility (can snap on thin hinges)
    * Best for: Low-stress PIP designs (e.g., articulated toys, simple hinges)
2. PETG (Polyethylene Terephthalate Glycol)
    * ✅ Pros: More flexible than PLA, better layer adhesion, impact-resistant
    * ❌ Cons: Slightly stringy, requires tuning for bridging
    * Best for: Functional tools (pliers, wrenches) where slight flex is needed
3. TPU (Thermoplastic Polyurethane, 95A or softer)
    * ✅ Pros: Extremely flexible, excellent for springs and snap-fit parts
    * ❌ Cons: Difficult to print (needs slow speeds, direct drive extruder)
    * Best for: Living hinges, grippers, compliant mechanisms
4. ABS (Acrylonitrile Butadiene Styrene)
    * ✅ Pros: High strength & durability, heat-resistant, slightly flexible
    * ❌ Cons: Prone to warping, Fumes & ventilation needed, tricky layer adhesion, not as elastic as TPU
    * Best for: High-stress PIP parts (e.g., tool handles, mechanical latches), applications needing heat resistance (e.g., automotive, outdoor use)

**Multi-Material Printing**

For printers with dual extrusion, combining materials improves functionality:
1. PLA + TPU - Rigid PLA for structural parts + flexible TPU for hinges/springs.
2. PETG + TPU - More durable than PLA, with TPU providing flexibility.
3. ABS + TPU - High-strength, heat-resistant ABS with elastic TPU.

# Embedded CAD Model
<iframe src="https://vanderbilt643.autodesk360.com/shares/public/SH286ddQT78850c0d8a4d1010e3cb984da3e?mode=embed" width="640" height="480" allowfullscreen="true" webkitallowfullscreen="true" mozallowfullscreen="true"  frameborder="0"></iframe>

<br>

# Design & Iterative 

## Pliers Specifications
* Total Width: 89mm
* Total Length: 137mm

**Spring Mechanism**

The pliers feature an integrated a hinge spring, allowing the jaws to return to their default position. The spring was designed with:
* Holes for snap-fitting the handles and jaws
* Clearence between the jaws for more degree of movement
* Flat bottom and top layer for advanced slicing, which is how I created the spring mechanism in this project
    * By removing the top and bottom solid layer we allow the infill to become a spring 
    * Also make the infill pattern rectilinear for straight and predictable spring motion

**Jaw Specification**
* Jaw Length: 56mm
* Jaw Width: 18.4mm
* Jaw Thickness: 6.6mm
* Jaw Capacity: 13mm (Relaxed)
* Has hooks for snap-fit

**Handle Specification**
* Handle Length: 80mm
* Handle Width: 18mm
* Handle Thickness: 6.6mm
* Has hooks for snap-fit

## Material Selection
* PLA
    * For rigidity in the jaws and handles
* TPU
    * For spring effect in the flexible section of the mult-material pliers
    * Allows for snap-fit with PLA

## Key Iterations
1. First Iteration – First print of handles, jaw, and spring mechanism, but snap-fit joint and jaw print failed
2. Second Iteration – Deeper hole joint on PLA part, more hook joints on the spring mechanism, and thicker parts for better snap-fit. Plier couldn't close all the way due to long handles. Plier also had a weak grip due to spring mechanism's low infill (10%)
3. Final Design – Fix spring mechanism's infill to have enough tension, shortened the handles, and change jaw shape for better grip on resistors.


# Print Settings
* Printer: FFF (Voron)
* Nozzle: 0.6

## Flexible Part Settings
* Material: TPU
* Infill: 15%
* Fill Pattern: Rectilinear
* Bottom Solid Layers: 0
* Top Solid Layers: 0
* Perimeters Count: 4

## Handle and Jaw Settings
* Material: PLA
* Infill: 25%
* Fill Pattern: Gyroid
* Bottom Solid Layers: 3
* Top Solid Layers: 4
* Perimeters Count: 2

# Gallery: Iterations & Final Plier
{% include gallery caption="Iterations and Final Plier" %}

# GIF: Pliers in Action
![inAction](/assets/img/plier/Action.gif){: .align-center}

