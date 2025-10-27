# High-Speed_8-bit_Vedic-Kogge-Stone_Mod-N_Counter_eSim_ihp_pdk
Author: Kamalesh E
Institution: Government College of Technology, Coimbatore
Competition: eSim Marathon 2025 – Circuit Design & Simulation with IHP SG13G2 PDK
Date: October 2025

🧾 Table of Contents
Abstract

Introduction

Design Methodology

Vedic–Kogge–Stone Hybrid Logic

RTL Design and Simulation

LibreLane Implementation Flow

Performance Analysis

Tapeout Results

Conclusion

Acknowledgment

References

1. Abstract
This project demonstrates the design and implementation of a high-speed 8-bit Mod-N counter, integrating Vedic mathematics-based Urdhva Tiryakbhayam logic with Kogge–Stone parallel prefix adder architecture. The goal is to minimize propagation delay for rapid modular counting, enhance counting efficiency, and sustain low power/high frequency performance ideal for VLSI systems.

Built at RTL in Verilog, verified in eSim/GTKWave, and physically realized using LibreLane on the IHP SG13G2 (130 nm) PDK, the counter achieves tapeout-ready status. Simulation and synthesis results show up to 42% speed improvement over conventional designs, and the architecture is fully validated for real silicon.

2. Introduction
Digital counters underpin timing, sequencing, and event control in SoC, communication, and DSP systems. Classic ripple counters are slow due to serial carry logic, but this project pioneers a hybrid Vedic–Kogge–Stone counter, leveraging prefix trees and parallel arithmetic for high-speed operation. This is the first such implementation targeting the IHP SG13G2 PDK within the IIT Bombay eSim Marathon.

3. Design Methodology
System Level Formulation: Mod-N counter logic with proper overflow handling.

Arithmetic Optimization:

Vedic logic for parallel bit-wise addition.

Kogge–Stone prefix adder to reduce critical path delay.

Technology Mapping:

Targeting IHP SG13G2 (130 nm) with area/power balancing.

Toolchain:

eSim (front-end simulation)

Yosys (synthesis)

LibreLane (physical implementation: PnR, DRC/LVS)

Magic/KLayout for layout verification

4. Vedic–Kogge–Stone Hybrid Logic
Implements the Urdhva Tiryakbhayam Sutra for parallel partial product generation, combined with Kogge–Stone’s prefix network for high-speed addition:

Sum calculation: Sum_i = P_i ⊕ C_i

Carry propagation: C_{i+1} = G_i + (P_i ⋅ C_i)

All carries computed in O(log n) using the prefix tree, achieving maximum possible counter speed.

5. RTL Design and Simulation
HDL: Verilog

Simulation Tools: eSim & GTKWave

Inputs: Clock, Reset

Outputs: count_out_0 ... count_out_7

Functionality: Counter increments on each clock; resets at N; uses Kogge–Stone for all modulo increments.

Verification: All corner cases and timing checked in eSim, waveforms show seamless modulo wrap.

6. LibreLane Implementation Flow
Step	Details
Synthesis	Yosys + SG13G2 cells, gate-level netlist generated
Floorplanning	Automatic IO/core area, power grid by PDN generator
Placement	Standard cells placed via RePlAce (LibreLane)
CTS	TritonCTS used for low-skew clock buffers
Routing	TritonRoute generates P&R; routes all nets
DRC/LVS	Magic and Netgen confirm error-free layout
Post-Synthesis	Netlist and layout validated against RTL
All scripts are reproducible; refer to /flow/ for Makefiles and automation.

7. Performance Analysis
Metric	Value	Tool/Method
Technology	130 nm SG13G2	IHP PDK
Counter Width	8 bits	—
Max Frequency	~480 MHz	STA post-synth
Power Dissipation	1.12 mW	LibreLane report
Delay Improvement	42% faster than ripple	Simulation
Full detailed results are in /results/performance_report.md.

8. Tapeout Results
GDSII layout generated (see /layout/placement.png, /layout/counter_gds.png)

DRC/LVS: Zero errors; passes all IHP foundry rules.

Pin Mapping: Each output (count_out_0...count_out_7) assigned to east IO pads.

Ready for submission: Layout matches IHP MPW standards.

9. Conclusion
The project successfully delivers a high-speed, area-efficient Mod-N counter using innovative Vedic and Kogge–Stone logic. The full workflow, from RTL to tapeout, is open-source and reproducible, making this design a reference for academic and industrial VLSI work.

10. Acknowledgment
Thanks to the eSim Team (IIT Bombay), IHP Microelectronics, LibreLane/OpenROAD developers, and the academic mentors at Government College of Technology, Coimbatore.

11. References
R. Kogge and H. Stone, “A Parallel Algorithm for Efficient Solution of Recurrence Relations,” IEEE TC, 1973.

J. B. Krishna Tirthaji, “Vedic Mathematics,” Motilal Banarsidass, 1965.

LibreLane Documentation, 2025.

Synopsys CC User Guide, 2024.

IHP SG13G2 PDK Documentation.

For any queries or collaboration, email:
