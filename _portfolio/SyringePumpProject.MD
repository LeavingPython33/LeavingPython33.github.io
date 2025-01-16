---
title: "Syringe Pump Project"
excerpt: "Using"
header:
  overlay_image: https://gardenculturemagazine.com/wp-content/uploads/2019/08/BODY-IMAGE-AQUAPONICS-diagram.jpg
  overlay_filter: 0.5
  teaser: /assets/img/Aquaponics.jpg

categories:
  - Engineering
  - Digital Fabrication
tags:
  - CAD
  - 3D-Printing
  - Electrical
  - Mechanical
meta: "January 12, 2025"

gallery:
  - image_path: assets/img/Aquaponics.jpg
  - image_path: assets/img/Aquaponics2.jpg
  - image_path: assets/img/Aquaponics3.jpg
  
toc: true
toc_label: "Table of Contents"
toc_sticky: true
toc_icon: bars
---

# Introduction
Syringe pumps are motor-driven devices that are made to precisely and consistently transfer fluids with accuracy. They are used in several different scientific domains, such as biotechnology and pharmaceutical research for precise measurements and reproducible experiments due to their continuous and regulated fluid delivery. Syringe pumps main utility comes from their safe handling of biological materials, as they maintain sterility while swapping syringes. In addition, they precisely pump fluids of high viscosities while preserving a continuous flow. These pumps typically include a motor to power the mechanism, a syringe holder to safely hold the fluid, and a push block to enable the plunger to move smoothly and under control. These parts work together as the fundamental building blocks of a syringe pump, giving researchers and practitioners more precision and control over their experiments.

# Syringe Pump CAD

# Design Constraints
The goal of this project is to design a functional syringe pump while meeting several design constraints. First, the pump must be driven by a stepper motor coupled to a lead screw, and the flow rate (in mL/min) should be easily adjustable through an Arduino program. This includes using global variables for the flow rate and syringe pump diameter, allowing for decimal values. The pump needs to be compatible with syringes of different diameters (20 mL to 10 mL), with tool-free switching between syringes. The motor mounts should be printed using ABS. The outside of the stepper motor can reach up to 80 C and ABS does not deflect until 100 C. Additionally, the syringe should be supported at both ends to prevent sagging during operation.

The design must also include an LED indicator to show the pump's operational state: green for running, yellow for paused, and red for empty. A latching button should control the start and pause of the pump's motion, while a limit switch must stop the motion when the plunger reaches its limit. Electrical wiring must be clean, with proper terminations and protected soldered joints. Custom wire harnesses should be created for external buttons and sensors, while jumper wires are used only for breadboard-to-breadboard and breadboard-to-Arduino connections.

To protect parts and users, electrical components must be shielded from liquids and user interference. Core components should be assembled as a single unit, with the electronics enclosure attached to the syringe pump. Unique branding is encouraged to distinguish the pump from other models, and components should be joined using fasteners or non-permanent snap fits, avoiding glue or hammering.

Additional features such as motor movement direction control buttons and a potentiometer for flow rate control should be included. The pump should use the AccelStepper library for motor control, ensuring smooth speed transitions and precise flow rate control. Custom 3D printed parts are required for mounting the motor, holding the syringe, and enclosing the electronics while adhering to safety measures around handling the power supply and preventing electrical hazards. Lastly, the pump's Arduino code should control the stepper motor speed, manage LED indicators, and account for flow rate conversion.

# Instructions on Operating Syringe Pump
1. Flash the arduino with the SyringePumpProgram.ino file if not already
2. Turn on the power supply by plugging it into a 120 V outlet
3. Push the latching button to active the syringe pump, the led on the front board will turn green to indicate that it’s on
4. Watch the syringe pump pump at a specific flow rate (mL/m)
5. You can pause the syringe pump by clicking on the latching button again and the led will turn yellow to indicate that the syringe pump is paused
6. When the syringe is empty, it’ll hit the limit switch. The limit switch will stop the syringe and make the led red to inform you that it’s empty.
7. Push the latching to turn off the syringe pump
8. Reset the syringe pump and do it all over again
9. If you want to change the flow rate go in the .ino file and change the flowRate global variable or you can manually change the flow rate with the potentiometer on the front

# Design Coverage
Figure 1. Syringe Pump CAD rendering

Figure 2. Syringe Pump Physical Model
	The system utilizes a stepper motor coupled to a threaded rod in order to pump fluid in and out of the syringe. The motor is fastened to a 3D printed ABS motor mount with four M4 bolts which in turn is also bolted down to the 2040 aluminum extrusion. The motor setup is seen below in Figure 3.

Figure 3. Motor setup
The syringe is set up across three components along the actuator: the carriage, the plunger holder, and the nozzle support. All three parts are 3D PLA parts. The plunger holder and nozzle support are secured to the aluminum extrusion, while the carriage remains unfastened as shown below in Figure 4. 

Figure 4. Syringe Setup 
A lead screw with an 8mm lead is embedded into the carriage while bearings are placed in the plunger holder and nozzle support to facilitate linear actuation when the motor turns. A linear rod is sent through all three parts to stabilize the carriage with collars placed to prevent the rod from sliding. The carriage has an inlet cut out for the plunger flange to grip the syringe. Similarly, the plunger holder has an inlet to grip the barrel flange and the nozzle holder has a concave opening to prevent the nozzle from sagging. There is also a limit switch embedded into the plunger holder that closes when the syringe is empty. This occurs when the carriage reaches a certain distance from the plunger holder.
This design is compatible for multiple diameter syringes, as the carriage includes an opening larger than the plungers but smaller than the plunger flanges. The plunger holder follows a similar approach, providing an opening sufficiently large for the barrels while small enough to secure the flange. This accommodation can be seen in Figure 5 below.

Figure 5. Dual Syringe Setup
The button on the syringe pump acts as a start and stop switch. When the button is not pressed, the LED will be yellow, indicating that the pump is in a paused state. Pressing the button turns the LED green, signaling that the pump is active and in a "go" state. Activation of the limit switch turns the LED red and sends a signal to the Arduino, indicating that the syringe has fully pumped out. The red LED also signifies that the syringe is empty and in a stopped mode. Turning the potentiometer counterclockwise increases the pumping speed, and vice versa. Pressing the momentary button on the left causes the syringe to retract, while pressing the button on the right causes the syringe to extrude. The full user interface is shown below in Figure 6 with the wiring diagram in Figure 7.

Figure 6. User interface

Figure 7. Wiring Diagram
The base of the syringe pump protects the electronic components from any water and humans, by fully covering the arduino, breadboard, and power supply. The top piece of the base is designed to hold the syringe pump mechanism, but also to protect all the electronics from water and fingers. The front piece of the base holds all the buttons for the user and hides all the electronics from the user. The base width is smaller than the T-extrusion so if the syringe has any water leaks, the water will spill outside the base. The base also has vents to protect the power supply from overheating.
	The syringe pump is programmed by the Arduino IDE, because it’s easier to compile and upload the program into the Arduino Uno than any other programs. The Arduino IDE includes many libraries, which were used to easily program the stepper motor. The library that was used to program the syringe pump is called AccelStepper. In configuring the motor, the direction must be set to high for clockwise motion. We used all available microstepping, resulting in sixteenth-step resolution microstepping. The high microstepping allows the stepper motor to be more precise in pushing out the fluids, which is important in giving the correct dosage. If you want to change the flow rate of the syringe or turn off some of the functions, you can change the following variables in Figure 8.


| Important Variables    | Data |
| -------- | ------- |
| bool extraCred  | True/False if you want the left and right button to be active |
| const int microStep | The microStep fraction (if it’s 1/16 steps, input 16) |
| const int diameter    | The diameter of the syringe in mm    |
| const int leadScrew  | Lead screw travel distance for every full rotation |
| double flowRate | Desired flow rate in mL/min |
| bool dynamic    | True/False if you want potentiometer to control flow rate    |
Figure 8. Important Variables in SyringePumpProgram.ino

# Operating Limits
The theoretical max flow rate for any syringe size that can be inputted into the program is 320000 steps per second which is 1.36 * 10^10 mL/min, because the max speed set on the stepper motor is 320000 steps per second. The smallest volume of fluid that can be dispensed is 0 mL because the syringe pump can be slowed down to a flow rate of 0 mL/min with the potentiometer or in the flowRate variable. The smallest flow rate that is non zero is 0.043 mL/min, because the stepper motor’s smallest speed is 1 step per second. The range between the maximum and minimum flow rates should be enough in a medical setting, as you don’t want to dispense too slow or too fast.

# Calculations in Converting Volumetric Flow Rate to Steps
For the syringe project, the desired flow rate needs to be converted from mL/min to steps per second for the stepper motor to use. The equation to turn flow rate into steps per second is:	flowRate (mL/min)* 1min60s*1000mm31mL*1r2(mm2)*1revleadScrew(mm)*200 * microStep (steps)1rev=stepPerSec (st/s)  

## Example:
1. Lets input a flow rate of 1 mL/min, the diameter of the syringe to 19mm, no micro stepping, and 8mm lead screw
2. Set the flow rate to seconds so divide the flow rate by 60 seconds = 1/60 (ml/s)
3. Multiply the flow rate by 1000mm^3/1mL, so the flow rate in terms of mm^3 is = 1000/60 (mm^3/s)
4. Calculate the area of the syringe by inputting 19mm into (d/2)2  to get 283.53 mm^2
5. Then divide the flow rate by the syringe’s area to get the flow rate’s speed in one axis = 5.88e-2 mm/s
6. Take the speed and divide it by the lead screw (8mm) to get the amount of revolution it needs to take = 7.35e-3 rev/s
7. Take the distance travel per full rotation and multiply it by the amount of steps it takes for the stepper motor make a full rotation including microstepping will get us  7.35e-3 rev/s * 200 * 1 = 1.47 steps/s
8. The program will set the speed of the stepper motor to 1.47 Steps/s to produce 1 mL/min in a syringe with a diameter of 19mm

# 3D Printing Issues
Several issues were encountered while 3D printing parts of the syringe pump. The first issue was printing toppers that would hold the syringe to go on top of the existing supports for testing. Determining the tolerance was difficult as a topper that was too small would either break the sides or require permanent alterations with a heat gun to expand the inserts which did not follow the design constraints. Determining the print orientation was also difficult as placing it on the bottom side made it hard to cleanly remove supports while a cleaner finish was desired on the syringe profiles. The failed parts can be seen in Figure 9 below. 

Figure 9. Toppers with Too Small Tolerances 
Expanding the tolerance any more resulted in the setup becoming wobbly and an insecure setup as seen in Figure 10 below. 

Figure 10. Unstable Setup due to High Tolerance
To solve this, the syringe holders were embedded into the existing setup. This eliminated the interfacing between the toppers and the existing setup bypassing the need for support placements, awkward print orientations, and strict fitting tolerances as seen in the full setup in Figure 11 below.

Figure 11. Embedded Supports
Another issue that was encountered was printing the decal onto our enclosure. Using the text tool in the sketch toolbox, Resin Rebels was engraved onto the top. This however resulted in floating pieces in the ‘R’s and ‘B’. To solve this issue, each floating piece was bridged with an extra material in the original CAD as shown in Figures 12 and 13 below. In addition to functionality, the name plate after bridging the text had more of a sleek appeal. 

Figure 12. Original Name Plate

Figure 13. Post Bridge Name Plate

# Conclusion
In conclusion, this project provided the opportunity to determine whether designing, manufacturing, wiring, and coding a syringe pump from scratch is a cost-effective alternative to commercial products, while having comparable performance. Throughout the project, there were several different challenges that were encountered and addressed. Manufacturing wise, there were many issues that were encountered whether it was a flipped sketch or a wrong dimension, which required the part to be printed again. This delay in the timeline pushed back testing code and electronics. Software wise, there were a lot of small mistakes from putting the wrong pin numbers, incorrect if statements, or not executing the right function. The mistake in the software had to go through thorough testing, removing time off from the paper. Looking back on the project, it was key that the team tested far in advance to prevent work out any kinks. Future improvement could include customizing the length of the aluminum base, threaded rod, and linear rod for a streamlined design. Overall, the project demonstrated a valid proof of concept with the given materials and displayed the potential of a budget friendly and high performance syringe pump. 
	


Appendix A.
# Arduino Code (SyringPumpProgram.ino)
These are the following variables of the program:

# Drawings
