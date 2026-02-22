# Linear Integrated Circuits Laboratory

## Experiment 1 – Design of Common Source Amplifier using NMOS (TSMC 180nm)

**Name:** Suhas Koushik  
**Branch:** Electronics and Communication Engineering  
**Tool Used:** LTspice  
**Technology Library:** TSMC 180nm  

---

## Problem Statement

Design a Common Source (CS) amplifier using an NMOS transistor in TSMC 180nm technology library using LTspice with the following specifications:

- Supply voltage (VDD) = 1.8V  
- Power constraint P ≤ 1mW  
- Load capacitance CL = 10pF  
- Channel length Ln = 560nm  

Perform DC analysis, transient analysis and AC frequency response analysis and study the effect of load capacitance on gain and bandwidth.

---

## Introduction

The Common Source amplifier is one of the most widely used MOSFET amplifier configurations in analog integrated circuits. It provides high voltage gain and phase inversion between input and output.

MOSFET operates as a voltage-controlled current device where the gate voltage controls the drain current. The amplified output voltage is obtained across the drain resistor.

---

## Theory

For amplification, the MOSFET must operate in the saturation region.

Saturation conditions:

VGS > VTH  

VDS ≥ (VGS − VTH)

In CS configuration:
- Input is applied at gate terminal  
- Output is taken from drain terminal  
- Source is grounded  

Increase in gate voltage increases drain current, producing a larger voltage drop across RD, thereby decreasing output voltage and causing phase inversion.

---

## Circuit Implementation

The CS amplifier was designed in LTspice using NMOS transistor from TSMC 180nm technology library, drain resistor and DC supply.

![CS Circuit](cs_circuit.png)

---

## Design Calculations

Given:

VDD = 1.8V  
Pmax = 1mW  

Maximum allowable current:

Imax = Pmax / VDD  

Imax = 1×10⁻³ / 1.8  

Imax = 555.5µA  

To ensure stable operation, drain current selected:

ID ≈ 200µA  

Power verification:

P = VDD × ID  

P = 1.8 × 200µA  

P = 0.36mW < 1mW  

Gate bias voltage selected:

VGS = 0.9V  

Threshold voltage (from TSMC 180nm model):

VTH ≈ 0.36V  

Overdrive voltage:

VOV = VGS − VTH  

VOV = 0.54V  

Drain resistance:

RD = (VDD − VDS) / ID  

RD = (1.8 − 0.9) / 200µA  

RD = 4.5kΩ  

Channel length used:

Ln = 560nm  

---

## DC Analysis

The DC operating point confirms correct biasing of MOSFET in saturation region.

![DC Analysis](dc_operating_point.png)

Observations:
- Stable operating point achieved  
- MOSFET operates in saturation  

---

## Transient Analysis

A sinusoidal input signal was applied at the gate terminal and output waveform was observed.

![Transient Input](transient_input.png)
![Transient Output](transient_output.png)
![Transient Response](transient_input_output.png)

Observations:
- Output waveform amplified  
- 180° phase shift observed  

---

## AC Frequency Response

The frequency response of the amplifier was analyzed to determine gain and bandwidth.

### Without Load Capacitor

![AC Without Capacitor](ac_without_capacitor.png)

High bandwidth observed and midband gain obtained.

### With Load Capacitor (CL = 10pF)

![AC With Capacitor](ac_with_capacitor.png)

Bandwidth significantly reduced due to load capacitance.

---

## Gain–Bandwidth Observation

As load capacitance increases:
- gain reduces slightly  
- bandwidth decreases significantly  

This verifies the gain–bandwidth tradeoff in practical amplifiers.

---

## Effect of Parasitic Capacitances

MOSFET contains internal capacitances:
- Gate–Source capacitance  
- Gate–Drain capacitance  
- Drain–Body capacitance  

These affect high-frequency behavior and cause deviation from ideal gain-bandwidth product.

---

## Conclusion

The Common Source amplifier was successfully designed using NMOS transistor in TSMC 180nm technology under given power constraints. DC, transient and AC analyses were performed and gain–bandwidth tradeoff was observed with the introduction of load capacitance.
