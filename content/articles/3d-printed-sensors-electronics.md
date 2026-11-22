---
title: "3D Printed Sensors Electronics: RF Components via Additive Manufacturing"
date: 2026-07-16T06:01:50-06:00
draft: false
description: "How additive manufacturing is used for 3D printed sensors electronics and RF parts: the processes, measured conductor and inductor results, and current limitations."
keywords: ["3D printed sensors electronics", "RF sensors additive manufacturing", "printed inductors 3D printing"]
---

**3D printed sensors electronics** covers a set of techniques for building conductors, coils and sensing elements into or onto a three-dimensional part instead of onto a flat board. For radio frequency components such as inductors and antennas, the appeal is geometric: a coil can be a true solenoid inside a housing, and an antenna can follow a curved surface. This article looks at the processes involved, what published work has actually measured, and where the limits are.

## Why Conductor Quality Matters for RF Parts

The quality factor (Q) of an inductor with a series loss resistance is its reactance divided by that resistance, so a larger series resistance means a lower Q. That makes the conductivity of the printed conductor the central question for any printed coil. The sections below give measured figures for three different approaches.

## Additive Processes for Electromagnetic Components

Not every printing process handles conductive materials the same way.

### Aerosol Jet Printing

Optomec's Aerosol Jet process uses a pneumatic or ultrasonic atomizer to turn an ink into a mist of droplets 2 to 5 microns in diameter, then uses a sheath gas to focus the mist into a tight stream. An I-Connect007 article on the process gives a feature range from 10 microns to a few millimeters, names silver nanoparticle ink as a typical material, and says the stream stays focused over a working distance of up to 5 mm, which is what allows printing on non-planar surfaces. Boise State University's description of its Aerosol Jet system also gives feature sizes as small as 10 microns and notes that the non-contact process can pattern over existing structures, across curved surfaces and into channels.

### Inkjet Printing with Silver Nanoparticle Ink

Silver nanoparticle inks need a sintering step after deposition to remove excess solvent and bring the particles into contact. A Georgia Institute of Technology group that inkjet-printed antennas on paper reported that the conductivity of its ink varied from 0.4 to 2.5 × 10⁷ S/m depending on the temperature and duration of curing, and chose curing at around 120°C for two hours. Bulk silver has a resistivity of 1.59 × 10⁻⁸ Ω·m, so the top of that range is roughly 40 percent of bulk silver's conductivity.

### Extruded Pastes and Filled Channels

Robocasting, which is analogous to direct ink writing, extrudes a shear-thinning paste from a small nozzle while the nozzle moves across a platform, building the object layer by layer.

A related route prints the dielectric first and adds the conductor afterward. In a 2015 paper in Microsystems & Nanoengineering, Wu and colleagues printed polymer structures with hollow channels, dissolved the sacrificial material, and filled the channels with a silver particle suspension that cured at room temperature. The result was embedded resistors, solenoid inductors and parallel-plate capacitors inside a single printed part.

### FDM with Conductive Filaments

Fused deposition modeling with conductive thermoplastic composites is the most accessible approach and carries the steepest electrical tradeoffs. Protopasta lists the volume resistivity of its conductive PLA as 30 ohm-cm for 3D printed parts, rising to 115 ohm-cm through the layers along the Z axis. Copper is 1.68 × 10⁻⁸ Ω·m, or 1.68 × 10⁻⁶ ohm-cm, about seven orders of magnitude lower. That rules these filaments out for RF inductors, but not for sensing. Leigh and colleagues (PLOS ONE, 2012) formulated a carbon black and polycaprolactone composite, printed it on an unmodified low-cost FDM printer, and demonstrated a piezoresistive flex sensor, capacitive buttons, and a mug with embedded tracks whose capacitance varied with the volume of water added. Their glove with embedded flex-sensing strips was printed in a single, un-paused print run.

## Engineering the Inductor: Measured Results

The Wu paper is a useful reference point for what a printed, embedded inductor looks like in practice. Its solenoid coils measured 23 nH, 51 nH and 92 nH at 0.4 GHz for 2, 4 and 6 turns. An LC tank built from a 4-turn solenoid and a parallel-plate capacitor resonated at about 0.53 GHz with a Q of about 13. One embedded resistor measured a conductivity of about 2.8 × 10⁵ S/m.

Planar antennas are more directly printable. The Georgia Tech group presented a compact inkjet-printed UHF passive RFID antenna on paper, a T-match folded-bowtie half-wavelength dipole designed to match the tag IC's impedance.

## Applications in RF Sensing

**Passive wireless sensing:** Wu and colleagues embedded their LC tank in a "smart cap" for a milk package. Liquid in the capacitor gap acts as the dielectric, so changes in the liquid shift the resonance, and an inductively coupled reader detects the shift without opening the package. They reported a 4.3% resonance frequency shift for milk stored at room temperature for 36 hours, against about 0.12% for milk kept at 4°C.

**Conformal antennas and sensors:** The I-Connect007 article cites antennas for smartphones and sensors for the IoT market as Aerosol Jet applications, along with strain sensors printed on GE gas turbine blades using a ceramic ink.

## Current Limitations

- **Conductor quality:** The figures above span a wide range, from about 2.8 × 10⁵ S/m for a paste-filled channel to 2.5 × 10⁷ S/m for well-cured inkjet silver, and all are below bulk silver. Lower conductivity means higher series resistance and lower Q.
- **Feature size in filled channels:** Wu and colleagues found channels of 400 microns or smaller hard to fill, and used 600 microns as the practical size.
- **Filament behavior:** Protopasta notes that its conductive PLA has less layer adhesion than regular PLA and should be kept below 50°C. Leigh and colleagues found that higher carbon black loadings would not pass through a standard heated nozzle.

## Where This Leaves the Field

3D printed sensors electronics is best understood as an extension of conventional electronics manufacturing, not a replacement for it. Published work shows embedded solenoids, LC resonators that can be read wirelessly, printed UHF antennas, and capacitive and flex sensors printed inside plastic parts. The limiting factor in each case is the conductivity of the printed conductor.

## Sources

- [I-Connect007: A Twist on Printed Electronics, Printing on 3D Shapes (Optomec Aerosol Jet)](https://iconnect007.com/article/104716/a-twist-on-printed-electronics-printing-on-3d-shapes/104719/pcb?page=1)
- [Boise State University: Optomec Aerosol Jet AJ 200](https://www.boisestate.edu/coen-imfl/?p=106)
- [Rida, Yang, Vyas and Tentzeris, IEEE Antennas and Propagation Magazine, June 2009 (Georgia Tech)](https://tentzeris.ece.gatech.edu/APMag2009.pdf)
- [Microwaves & RF: Inkjet Printing Produces RFID Antenna](https://www.mwrf.com/components/inkjet-printing-produces-rfid-antenna)
- [Wu et al., 3D-printed microelectronics for integrated circuitry and passive wireless sensors, Microsystems & Nanoengineering (2015)](https://www.nature.com/articles/micronano201513)
- [Leigh et al., A Simple, Low-Cost Conductive Composite Material for 3D Printing of Electronic Sensors, PLOS ONE (2012)](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0049365)
- [MatterHackers: Protopasta Electrically Conductive Composite PLA (manufacturer figures)](https://www.matterhackers.com/store/l/proto-pasta-conductive-pla-1.75mm/sk/MUW33A27)
- [Wikipedia: Electrical resistivity and conductivity](https://en.wikipedia.org/wiki/Electrical_resistivity_and_conductivity)
- [Wikipedia: Q factor](https://en.wikipedia.org/wiki/Q_factor)
- [Wikipedia: Robocasting](https://en.wikipedia.org/wiki/Robocasting)

Fact-checked 2026-11-21
