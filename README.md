Planar CMOS Process Simulation (Victory Process / Silvaco TCAD)
Overview

This project implements a complete planar CMOS fabrication flow using Silvaco Victory Process and Victory Visual. It covers device fabrication, physical parameter extraction, and electrical characterization across multiple process refinements — from shallow junction CMOS to deep trench isolation and SiGe integration.

The objective is to understand and simulate realistic CMOS process integration steps, analyze their impact on device performance, and perform design optimizations to meet threshold and leakage constraints.

Project Structure
planar/
│
├── cmos_shallow/       # Part 1: Base planar CMOS flow
│   ├── planar_cmos_1.in
│   ├── pcmos_1_process.results
│   ├── I-V plots (NMOS/PMOS, linear/saturation)
│
├── cmos_deep/          # Part 2: Deep trench isolation variant
│   ├── planar_cmos_deep_1.in
│   ├── pcmosd_1_n_lin.results
│   ├── pcmosd_1_n_sat.results
│   ├── pcmosd_1_p_lin.results
│   ├── pcmosd_1_p_sat.results
│
├── cmos_sige/          # Part 3: SiGe integration for PMOS S/D
│   ├── planar_cmos_sige_1.in
│   ├── punchthrough_contours.png
│
└── cmos_final/         # Part 4: Optimized CMOS to meet design constraints
    ├── planar_cmos_final.in
    ├── electrical results (.results)
    ├── final_structure_doping.png
    ├── optimization_summary.txt

Tools & Environment:
Silvaco Victory Process (process simulation)
Silvaco Victory Visual (structure visualization, contouring)
TCAD DeckBuild (input deck execution)
Process File Formats: .in, .str, .results

Key Tasks & Outcomes
Part 1 — Shallow Planar CMOS
Simulated full CMOS process flow and verified cross-sections.
Added scalable extractions for deep source/drain junction depths (sd_depth_n, sd_depth_p).
Generated combined I–V curves for NMOS/PMOS under linear and saturation regimes.

Part 2 — Deep Isolation CMOS
Modified trench geometry and well parameters:
Isolation depth → 150 nm
Well drive time → 45 min
Nitride spacer → 11 nm
Extracted electrical results to evaluate trench isolation effects.

Part 3 — SiGe Integration
Introduced selective SiGe epitaxy (28% Ge) for PMOS S/D regions.
Implemented resist masking and silicon recess etching before epitaxy.
Observed punchthrough leakage due to excessive junction depth; verified using hole current contours.

Part 4 — Optimization
Adjusted implant profiles to:
Maintain NMOS performance within ±2%.
Reduce PMOS leakage < 1 nA/µm.
Achieve target threshold and subthreshold slopes.
Final structure verified via net doping contour and IV characterization.

Results Summary
Parameter	NMOS (Target ±2%)	PMOS (Target)
V<sub>th,lin</sub>	✅ Maintained	0.36–0.38 V ✅
I<sub>off,sat</sub>	< 1 nA/µm ✅	< 1 nA/µm ✅
Subthreshold Slope	< 90 mV/dec ✅	< 97 mV/dec ✅
Punchthrough	None	Eliminated ✅

Learning Outcomes
Gained hands-on understanding of CMOS process integration and TCAD-based design of experiments.
Developed skills in parameter extraction, SiGe stress engineering, and device performance optimization.
Learned scalable process coding and modular input deck design in Silvaco.

References
Silvaco Victory Process User Guide
CMOS Integration Flow Lecture Slides (Purdue ECE)
Advanced TCAD Modeling Notes on SiGe Strain Engineering
