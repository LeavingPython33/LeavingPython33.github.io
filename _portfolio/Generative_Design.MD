---
title: "Generative Design"
excerpt: "A project for our CHBE 4200 class at Vanderbilt University that focuses on exploring generative design to create efficient, often organic geometries"
header:
  overlay_image: "/assets/img/generative/Front_Mob8.jpeg"
  overlay_filter: 0.5
  teaser: "/assets/img/generative/Side_Mob8.jpeg"

categories:
  - Engineering
  - Additive Manufacturing
tags:
  - CAD
meta: "April 24, 2025"

gallery:
  - image_path: /assets/img/generative/Stock_Mob8.jpg
  - image_path: /assets/img/generative/Side_Mob8.jpeg

toc: true
toc_label: "Table of Contents"
toc_sticky: true
toc_icon: bars

type: Outside Projects
---

# Overview of the Final Part and Application
The final part is the frame of a whoop drone (FPV drone), specifically the Mobula 8 model. The frame is essential for keeping the drone’s components intact during crashes while remaining lightweight for smooth and fast flight. The drone frame's weight is the most important factor in designing a frame, as heavier drones force the motors to work harder than lightweight ones. For whoop-type drones, a difference of just a few grams can significantly impact performance due to their small motors. Drones, once used only for war, are now being utilized in agriculture, construction, and cinematography.

The standard Mobula 8 drone frames are effective at keeping the drone lightweight. However, the frame is flimsy, as even small forces can easily bend the plastic. After several flights, crashes eventually compromised the frame's integrity, breaking plastic connections around the battery mount and prop protector. By generating a new Mobula 8 drone, I would be able to fix my whoop drone while also learning about the generative design process.

# Preserve and Obstacle Geometry
The critical preserve regions in the model are:
* Battery Mount
* Motor Mounting Points
* Prop Protector
* Flight Controller & Video Transmitter Mounting Stands

The obstacle geometry is based on the standard Mobula 8 drone frames and its different components:
* The middle of the drone frame must be open to allow the motor to connect to the flight controller
* There shouldn't be anything around the motor that impedes the propellers from spinning
* The battery mount must be empty
* There shouldn't be anything outside the prop guards 

# Load Case Application and Structural Constraints
By applying forces to the geometry, we instruct Fusion to generate a design that can handle all these forces without failing.

In general, the forces I applied in the generative design are as follows:

* Wind Force  
    * Wind force is prevalent in drone flying, as a gust of wind could push the drone to the side. Therefore, the frame must be sturdy enough to withstand some wind force without breaking apart or flying away.
  
* Movement Force  
    * Drones have three movements: yaw, pitch, and roll, each changing the throttle of the motors. Therefore, the drone's frame must handle sudden force changes from the motors.
  
* Weight Force  
    * The heaviest component of a drone is the battery, so the frame must be capable of holding the battery without breaking the battery holder from the frame.
  
* Impact Force  
    * We want the drone to stop flying at some point, so the drone's frame needs to be able to handle landings without breaking.

I determined the magnitude, direction, and location of each load based on my experience flying drones and the use of a LLM.

I applied structural constraints to the stands of the flight controller and video transmitter, as they shouldn't be experiencing any significant forces. With these structural constraints, the design focuses on generating parts in unconstrained areas and redistributing the load.

By test-flying the generated drone frame, I can observe any failures in the prototype, such as cracks or breaks. By finding the forces that caused the failures and incorporating that forces into the generative study, I can improve the generation of the design.

# Critique of Generative Design

## Benefits/Limitation
Generative design can be useful for prototyping giving you a rough idea of what the object needs to be able withstand the forces for its intended purpose. However, it takes takes hours to generate design that may or may not work, taking valuable time away from further prototyping the design.

* Benefits:
    * Most optimized design for weight
    * Generates multiple designs for prototyping
    * Ensures the integrity of the model for their intended application
    * Looks cool
* Limitations:
    * Takes forever to generate
    * Incorrect forces can make the generated model not look right
    * Difficult to manufacture without a powder printer 
    * Difficult in figuring out the preserve and obstacle geometries 

## Applications
Generative design will be most useful for flight based designs for aerospace or aviation industries, where every gram matters in optimizing the design. However, generative design fall shorts for industry that wants to mass produce a design, due to generative design not being easily manufacturable. 


# Embedded Fusion 360 Model

## Base Model
<iframe src="https://vanderbilt643.autodesk360.com/shares/public/SH286ddQT78850c0d8a48e75f3da001da523?mode=embed" width="640" height="480" allowfullscreen="true" webkitallowfullscreen="true" mozallowfullscreen="true"  frameborder="0"></iframe>

## Generated Design
<iframe src="https://vanderbilt643.autodesk360.com/shares/public/SH286ddQT78850c0d8a4cded18e48e65fa32?mode=embed" width="640" height="480" allowfullscreen="true" webkitallowfullscreen="true" mozallowfullscreen="true"  frameborder="0"></iframe>

<br>

# Force Table

| Name of Force            | Magnitude            | Location of Where It Was Applied                                             | Short Rationale |
|--------------------------|----------------------|------------------------------------------------------------------------------|------------------|
| Coast Load               | 0.5 N                | All Motors                                                                   | When drone is coasting (Staying at the same altitude)                 |
| Throttle Load            | 0.8 N                | All Motors                                                                   | When drone is throttling (Rising altitude)                |
| Battery Load             | 0.3 N                | Battery Holder                                                               | Battery weight                 |
| Landing Load             | 0.5 N                | Bottom of Battery Holder                                                     | When the drone lands                 |
| Strap Load               | 1.0 N                | Battery Holder                                                               | The strap force holding the battery                 |
| ForwardWind Load         | 0.2 N                | Front of Drone Prop Guards + Battery Holder                                  | If there's wind hitting the front of the drone                 |
| SideWind Load 1          | 0.2 N                | Side of Drone Prop Guards + Battery Holder                                   | If there's wind hitting the side of the drone                 |
| SideWind Load 2          | 0.2 N                | Other Side of Drone Prop Guards + Battery Holder                             | If there's wind hitting the side of the drone                 |
| Gust Load                | 0.5 N                | Front of Drone Prop Guards w/ slight downward angle                          | If there's a strong gust hitting the drone                 |
| UpDraft Load             | 0.5 N                | Entire Bottom Frame                                                          | If there's upward wind hitting the drone                 |
| DownDraft Load           | 0.5 N                | Entire Top Frame                                                             | If there's downward wind hitting the drone                 |
| TurnLeft Load            | 0.3 N                | Back Left + Front Right Drone Prop Guards                                    | When the drone change Yaw                 |
| TurnRight Load           | 0.3 N                | Back Right + Front Left Drone Prop Guards                                    | When the drone change Yaw                 |
| Forward Load             | 0.4 N + 0.8 N        | Front Motors + Back Motors                                                   | When the drone change Pitch                 |
| Backward Load            | 0.4 N + 0.8 N        | Back Motors + Front Motors                                                   | When the drone change Pitch                 |
| Left Load                | 0.4 N + 0.8 N        | Left Motors + Right Motors                                                   | When the drone change Roll                 |
| Right Load               | 0.4 N + 0.8 N        | Right Motors + Left Motors                                                   | When the drone change Roll                 |
| Forward-Left Load        | 0.4 N + 0.9 N + 0.6 N| Front Left Motors + Back Right Motors + Back Left/Front Right Motors         | When the drone change Pitch + Roll                 |
| Forward-Right Load       | 0.4 N + 0.9 N + 0.6 N| Front Right Motors + Back Left Motors + Back Right/Front Left Motors         | When the drone change Pitch + Roll                 |
| Backward-Right Load      | 0.4 N + 0.9 N + 0.6 N| Back Left Motors + Front Right Motors + Front Left/Back Right Motors         | When the drone change Pitch + Roll                 |
| Backward-Left Load       | 0.4 N + 0.9 N + 0.6 N| Back Right Motors + Front Left Motors + Front Right/Back Left Motors         | When the drone change Pitch + Roll                 |

# Multimedia

## Images
{% include gallery caption="Stock vs. Generative Mobula 8 Frame" %}

## Motion in Use
![inAction](/assets/img/generative/Drone_Start.gif){: .align-center}
*GIF of Drone Starting*
{: .text-center}

## Generative Design Iterations
![Cast](/assets/img/generative/Generative_Results.png){: .align-center}{: .figures}
*Fusion Generative Design workspace*
{: .text-center}

| ![](/assets/img/generative/GS1.png){: style="height:200px;" } | ![](/assets/img/generative/GS2.png){: style="height:200px;" } |

 ![](/assets/img/generative/GS3.png){: .align-center}{: style="height:200px;" }

*Fusion Generative Design Outcomes*
{: .text-center}
