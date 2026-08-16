# Proposed Research Plan

This document is a work in progress by Robert L. Read to sort out some of the ideas. ChatGPT was used for some of this research.

# Decomposing the Problem

It seems there are fundamentally two problems that we can attempt to address, which synergize to some extent:
1. Building a sensor to tell when the gases are present or have exceeded some threshold.
2. Removing those gases, either by:
- Ventilation out of the room or
- Filtration, or
Some combination.

A team of students at Dundee University ("Team C") has proposed using a passive exhaust into an activated charcoal filter. 

# The Composition of Anesthesia Gases

According to ChatGPT, a combination of the nitrous oxide and an organic anesthesia gas, usually sevoflurane, is used for induction, but pure sevoflurane is used for maintenance of
anesthesia.
Activated charcoal filters cannot remove nitrous oxide, but can absorb sevoflurane.

# Avoiding the Not Invented Here Syndrome....
It would be easy for us to attempt to solve this problem by creating our own Active Gas Scavenging System (AGSS).
However, there is no point in us competing with existing commercial vendors. If we find ourselves creating an open source version 
of an existing tool, we should stop and consider if we are on the right track. 
In some case, and open-source solution can be cheaper and better than proprietary systems---but the difficulty of manufacturing is 
so high that this is generally not true of a simple design, even if the design is a good one.

# What is Unique about This Problem

* According to ChatGPT, modern operating theaters typically have a permanent built-in AGSS station in the floor of the ceiling.
This avoid the trip hazard that is a problem in the KidsOR operating theaters.
* The KidsOR surgical theaters have limited power, sometimes provided by their own solar system. Excess power for air conditioning may be limited.
* However, floor space my also be limited

# Modular Solution 

One obvious solution is to use a fan that can provide adequate suction through a relatively thin tube that can be taped to the floor sufficiently to reduce the trip 
hazard.
This suction can be used to pull the gases through an "open interface" for safety. An activated carbon filter can placed outside the OR to filter sevoflurane. 
Using an active system allows this to be sealed with pressure-release valves so that when not in use the activated carbon filter is not saturated by 
moisture. 
Pressure, flow, and VOC sensors can be added to make this system somewhat safer and more efficient. 

By placing the fan outside and using an "open interface" connection, we reduce the chance of any negative pressure on the breathing circuit, since
the interface will be open to the room air.
One idea is to use an airtight cable cover directly as a duct; these are designed to be less of a trip hazard:
[slit cable cover in 25' sections](https://www.uline.com/Product/Detail/H-9961/Cable-Management/Cord-Protector-25-Standard-Black)
An ["unslit" cabele cover](https://www.filmtools.com/checkers-rubber-duct-protector-10ft-black.htm) version exists which would be airtight for transporting the gases directly. 

Altermatively, round tubing in an 8mm diameter could be placed inside these. In general, the pressure required is proportional to the 4th power of the inverse diameter of the 
tube, so narrowing the tube requires a larger fan, by the Hagen–Poiseuille relation:

The Hagen–Poiseuille relation:

$$
\Delta P = \frac{128 \mu L Q}{\pi D^4}
$$

where:

- $\Delta P$ = pressure drop
- $\mu$ = dynamic viscosity of the gas
- $L$ = length of the tube
- $Q$ = volumetric flow rate
- $D$ = internal diameter of the tube

The important scaling relationship is:

$$
\Delta P \propto \frac{1}{D^4}
$$

Therefore, for the same flow rate and tube length, halving the tube diameter increases the pressure drop by a factor of 16.





Open questions are:
* Does a thin hose have too much resistance, requiring too powerful a fan?
* Can we get "flat rectangular tubes" that have a larger area for less of a trip hazard?
* How do we warn the user of pressure and other problems?
* Can we create a humidity catch?
  
