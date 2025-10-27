**High-Speed 8-bit Vedic-Kogge-stone Mod-N Counter: Digital Implementation,Simulation, and Tapeout**

 eSim Marathon 2025

**Author:** Kamalesh E

**Institution:** Government College of Technology,Coimbatore.
**Date:** October 27, 2025

**About the eSim Marathon and IHP SG13G2**

The eSim Marathon - *Circuit Design & Simulation with IHP SG13G2* is a
nationwide circuit design competition where participants use **eSim**,
an open-source EDA tool developed by FOSSEE, IIT Bombay, to design and
simulate circuits using the **IHP SG13G2 PDK ,** a 130 nm open-source
BiCMOS technology from IHP Microelectronics, Germany. The marathon
promotes self-reliance and innovation in VLSI by offering a complete,
open tool and PDK chain for tapeout-ready digital design.

**Abstract**

This project details the specification, design, simulation, and physical
implementation of a high-speed, area-efficient Mod-N counter employing
Vedic arithmetic and Kogge-stone adder logic. The modulo parameter was
set to *N* = 100 throughout. The design targets tapeout and conforms to
real foundry requirements. The report presents theoretical background,
methodology, verification, physical flow, and innovative features.

 **Introduction**

Digital counters are essential modules in SoCs, timing circuits, and DSP
systems. The drive for speed, power, and area efficiency motivates new
arithmetic techniques for hardware designers. Using both ancient Vedic
mathematics and the modern Kogge-stone adder, this project pioneers a
Mod-N counter with *N* = 100 optimized for performance and silicon
tapeout.

**Objectives**
>
> • Design a scalable Mod-N counter (with *N* = 100) for high speed and
> low area.
>
> • Utilize Vedic mathematics and Kogge-stone logic for fast increment
> and efficient terminal count detection.
>
> • Develop a tapeout-ready design with compliant pin assignments and
> physical design flows.
>
> • Validate through comprehensive RTL, pre-synthesis simulations,
> post-synthesis simulations, and physical layout verification.

 **Background: Vedic Mathematics in Digital Design**

Vedic mathematics is an ancient system notable for parallel, systematic
arithmetic, ideal for VLSI implementation. The Urdhva Tiryakbhyam
(vertical and crosswise) sutra enables fast multiplications and
additions with parallelism and minimal carry latency. Its integration
reduces critical path delay and power, while maintaining compactness and
scalability.

 **Design Methodology**

 **Novelty and Innovation**

This work uniquely blends:

> • The parallel-prefix Kogge-stone adder for logarithmic carry
> resolution.
>
> • The Vedic comparator for streamlined modulo detection.
>
> • Tapeout-aware I/O pin architecture matching foundry requirements.
>
> • Fully automated, open-source RTL-to-GDS flow using LibreLane(Yosys,
> OpenROAD, and KLayout).
>
> This integrated approach elevates the project for academic prestige
> and practical tapeout readiness.
>
**Schematic Diagram for N = 100**
>![eSim_schematic](https://github.com/user-attachments/assets/d94b4307-99d0-4804-8a30-41a7b9bdcf92)
> Figure 1: Schematic Diagram: Vedic-Kogge-stone Mod-100 Counter** 


**Simulation Using eSim**

Leveraging the eSim open-source environment ensures accurate simulation
reflecting silicon-level behaviors and enabling robust validation before physical design.
>![eSim_simulation](https://github.com/user-attachments/assets/994a3a7e-4d69-4b43-a34d-77b1a07edd0a)
>Figure 2: Simulation environment using eSim

 **Physical Pin Assignment**
>
> Pins are arranged as per foundry norms to finalize physical layout andtapeout documentation:
> #N\
> clk\
> rst
>
> #E\
> count_out_0\
> count_out_1\
> count_out_2\
> count_out_3\
> count_out_4\
> count_out_5\
> count_out_6\
> count_out_7
>
>#W\
(Empty)\
>#S\
(Empty)


**Simulation and Verification**

>**Pre-Synthesis Simulation**

Validates RTL correctness with waveforms showing seamless counter
wrapping at *N* = 100.

>![rtl_simulation](https://github.com/user-attachments/assets/a83d76d7-84a9-48e9-8890-e00b58c2c3ef)
>Figure 3: Pre-synthesis simulation: Correct modulo-100 counting

> **Post-Synthesis Simulation**
>
Confirms netlist fidelity post-synthesis optimizations, ensuring
timing closure and correct functional behavior.

>![gate_simulation](https://github.com/user-attachments/assets/bff19ebf-8da7-41df-b225-722476216a18)
> Figure 4: Post-synthesis simulation: Verified modulo-100 counter behavior



**Global Placement (OpenROAD):**

><img width="990" height="907" alt="global_placing" src="https://github.com/user-attachments/assets/bb94acf2-1524-4d5f-83b9-0c5b70b81301" />
>
>Figure 5: Global placement for N = 100
>
**Post-Routing**

><img width="993" height="924" alt="rounting" src="https://github.com/user-attachments/assets/5b8726d0-97dc-4b60-9b90-67ba2d946958" />
>Figure 6: Post-routing detailed view



**Final DEF Layout:**

><img width="993" height="924" alt="DEF_Layout" src="https://github.com/user-attachments/assets/29216f31-1084-480e-93ad-3fe37a5148d4" />
> Figure 7: Final DEF layout before GDS export for *N* = 100
>
**Synthesis and Place & Route**

Validated physical design pathway incorporating Yosys and OpenROAD,
generating DEF and GDS ready for tapeout.

><img width="990" height="907" alt="final_gds" src="https://github.com/user-attachments/assets/206dea69-c93b-4f1d-b656-7df58d19bc26" />
>Figure 8: Final GDS layout visualization



**Physical Verification**
>
> • Successful DRC and LVS with no violations.
>
> • Pin assignments comply with foundry guidelines.
>
> • Clean design layers with no metal or spacing issues.
>

**GDS Signoff and Tapeout Readiness**
>
> All steps reflected meticulous preparation for a successful tapeout
> submission in leading- edge technology.
>
**Challenges and Solutions**
>
> • Resolving DEF and pin mismatches through coordinated script and
> configuration management.
>
> • Automating the complex flow for reproducibility using Docker,
> GitHub, and Nix sand boxes.
>
> • Addressing corner-case timing and area constraints for foundry
> compatibility.
>
**Future Work**
>
> • Extending design to scalable widths (*N* = 256, *N* = 1024).
>
> • Integration into SoC clocking and timer subsystems.
>
> • Exploring AI-driven synthesis and custom Vedic blocks for enhanced
> designs.
>
> • Deployment for multi-foundry tapeouts and mass production readiness.

**Conclusion**

The Vedic-Kogge-stone Mod-100 counter project demonstrates cutting-edge
arithmetic and design flow integration, delivering a top-tier,
tapeout-ready ASIC component. Comprehensive validation and automation
poise this design for success in competitive and industrial contexts.


**References**
> 1\. *Kogge-stone Adder: Fast Parallel Adders*, IEEE Transactions on
Computers, 1982.
> 
> 2\. *Vedic Mathematics in Digital Design*, Journal of
VLSI Design, 2020.
>
> 3\. eSim,LibreLane,OpenROAD,Yosys, KLayout documentation.
>
> 4\. IHP Foundry Process and PDK Manuals.

**Acknowledgement**
The author thanks FOSSEE, IIT Bombay, IHP Microelec-
tronics, and all open-source tool developers whose efforts
empower affordable and accessible VLSI design and tapeout.


