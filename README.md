# Implementation and Figure of Merit Evaluation of a 32-bit MAC in 65-nm CMOS

## Overview
This repository contains the full-custom physical design and schematic implementation of a 32-bit Multiply-Accumulate (MAC) unit, designed using a 65-nm CMOS technology node. The project encompasses the VLSI design flow from transistor-level schematics to physical layout, ensuring DRC and LVS cleanliness. It is structured to evaluate the Figure of Merit (Power, Performance, and Area) of the implemented DSP block.

## Repository Structure
The design follows a strict hierarchical approach, building up from foundational standard cells to the final complete 32-bit MAC architecture. The workspace is formatted for Cadence OpenAccess (`.oa`).

* **`Gates/`**: Fundamental CMOS logic standard cells (`AND`, `NAND`, `XOR`) alongside their respective testbenches.
* **`Inverter/`**: Standard and sized-up inverters optimized for varying capacitive loads.
* **`FullAdder/`**: Transistor-level implementation of the Full Adder block used in the arithmetic stages.
* **`FlipFlop/`**: D-Flip-Flop designs, including standard and asynchronous reset variants (`D_FlipFlop`, `D_FlipFlop_ASynch`).
* **`Project/`**: The core integration directories containing the macroscopic arithmetic and memory units:
  * `RCA_8` & `RCA_64`: 8-bit and 64-bit Ripple Carry Adders.
  * `Reg_8` & `Reg_64`: 8-bit and 64-bit Register blocks.
  * `Mult_Row_32` & `Mult_32x32`: 32-bit multiplier row logic and the fully integrated 32x32 multiplier.
  * `MAC_32`: The top-level 32-bit Multiply-Accumulate unit.

## Tools & Technologies
* **Technology Node:** 65 nm CMOS
* **Design Environment:** Cadence Virtuoso (Schematic Editor & Layout Suite)
* **Physical Verification:** Calibre (Design Rule Check - DRC, Layout Versus Schematic - LVS)

## Methodology
1. **Schematic Capture:** Designed transistor-level implementations of all base cells, followed by logic verification.
2. **Physical Layout:** Custom layout generation for all CMOS gates and buffers, ensuring standard cell height constraints and optimal routing.
3. **Verification:** Rigorous physical design verification run on each cell and hierarchical block to guarantee zero DRC violations and precise LVS matching.
4. **Evaluation:** Extracted parasitics are utilized to analyze VTC curves, delays, and power consumption, culminating in the final Figure of Merit evaluation for the MAC unit.
