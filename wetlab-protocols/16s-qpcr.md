# 16S qPCR using SYBR Green

## Theory
This protocol is for the real time amplification of samples using SYBR Green master mix. 

## Prepare Your Workspace

- [ ] Turn on the PCR Clean Hood blower and white light. 
- [ ] Clean the cabinet with 70% ethanol including work surface and walls. 
- [ ] Turn the dial and run the UV light for at least 10 minutes. 
⚠️ You cannot expect the glass to protect you from UV exposure. You can be in a different part of the lab while the light is running, but do not loiter in front of the cabinet.
- [ ] Once the timer is up and the UV light turns off, you are ready to begin. 

*Remember, before placing any objects in the hood, they must be sprayed with 70% ethanol.*

## Gather Materials
- [ ] Nuclease Free Water
- [ ] PCR Plate/Tube Rack
- [ ] qPCR Adhesive Film
- [ ] qPCR Plate
- [ ] Micropipettes (P1000, P100, P10)
- [ ] Pipette Tips (1000uL, 100uL, 10uL)
- [ ] VWR Marker
- [ ] Sterile 2.0mL Centrifuge Tubes
- [ ] Template DNA
- [ ] Forward and Reverse Primers (0.5uM)
- [ ] PowerUp SYBR Green Master Mix (ThermoFisher Scientific, A25780)

## Master Mix Preparation

1.	Mix PowerUp SYBR Green Master Mix thoroughly.
2.	Thaw DNA samples and primers on ice, vortex to mix and centrifuge briefly. 
3.	In a sterile centrifuge tube labeled “MM” combine *10uL/sample PowerUp SYBR Green Master Mix (2X), 1 uL/sample Forward Primer (0.5uM), 1 uL/sample Reverse Primer (0.5uM), and 3 uL/sample nuclease free water.* 
4.	Reactions should be done in TRIPLICATE, so if preparing a whole plate of DNA samples, you will need to either use a 384-well plate or 3 96-well plates. To prepare master mix for a full 96-well plate, mix as outlined in Table 1. 
5.	Vortex tube and spin down.  

**Table 1. Master mix preparation volumes per 20uL reaction**
Reagent | Volume/Reaction | Volume for 100 Reaction
-----|-----|-----
PowerUp SYBR Green Master Mix (2X)| 10uL | 1000uL
Forward Primer (0.5uM)| 1uL | 100uL
Reverse Primer (0.5uM)| 1uL | 100uL
Nuclease Free Water| 3uL | 300uL

## Plate Preparation

1.	Transfer 15uL of master mix to each well on an optical plate. 
2.	Transfer 5uL of Template DNA to each well. 
3.	Add 5uL of nuclease free water to 3 wells on the plate that have master mix but no DNA. These are your negative controls. 
4.	Seal the plate with optical adhesive cover and spin down. 

## qPCR Reaction

1.	Setup thermocycler for the program appropriate for your primer’s melting temperature (Table 2 or Table 3). Place the plate in the instrument and enter your parameters into the computer program. Ensure that you are collecting data at the correct times. 
2.	Set the instrument to perform a default dissociation step (Table 4). This can be performed up to 24 hours after the RT-PCR run if the plate is exposed to light and up to 72 hours after if the plate is kept in the dark. 

**Table 2. Standard Cycling Mode (Primer Tm ≥ 60C)**
Step | Temperature (C) | Duration | Cycles
----|----|----|----
UDG Activation | 50 | 2 minutes | 1
Dual-Lock DNA Polymerase | 95 | 2 minutes | 1
Denature | 95 | 15 seconds | 40
Anneal/Extend | 60 | 1 minute | 

**Table 3. Standard Cycling Mode (Primer Tm < 60C)**
Step | Temperature (C) | Duration | Cycles
----|----|----|----
UDG Activation | 50 | 2 minutes | 1
Dual-Lock DNA Polymerase | 95 | 2 minutes | 1
Denature | 95 | 15 seconds | 40
Anneal | 55-60 | 15 seconds | 
Extend | 72 | 1 minute | 

**Table 4. Dissociation Curve Conditions**
Step | Ramp Rate | Temperature | Time
----|----|----|----
1 | 1.6C/second | 95 | 15 seconds
2 | 1.6C/second | 60 | 1 minute
3 | 0.15C/second | 95 | 15 seconds



