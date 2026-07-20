# COMSOL Multiphysics Simulation Model for Science Advances Manuscript
Manuscript Title: A biochemical-to-mechanical signal relay orchestrates cell morphogenesis in Arabidopsis
Corresponding Authors: Deshu Lin, Yaolong He
Software Version: COMSOL Multiphysics 6.4

## Repository Contents
This repository contains a single 70 MB COMSOL project file `Main_simulation.mph` which implements the finite element mechanical feedback simulation shown in Figure 4 of the manuscript. Simulations for other figures share the same core model with only modified parameters, whose differences are detailed in the manuscript. No redundant duplicate model files are provided here.

All geometric parameters, material constitutive functions, wall extensibility gradient models, stress feedback constitutive relations are fully embedded inside the project file.

## Model Core Configuration (Matches Figure 4 Simulations 1 to 5)
1. Geometry construction: Fully parameterized axisymmetric hemispherical petal conical cell shell geometry
2. Physics module: Solid Mechanics with membrane module for morphoelastic growth simulation
3. Two sequential study steps:
   - Study 1: Steady-state stationary solving, outputs initial stress & deformation field as initial value for transient calculation
   - Study 2: Time-dependent transient simulation, couples pH-gradient regulated wall extensibility and microtubule-mediated mechanical feedback
4. Post-processing: Pre-configured plot group `Plot` stored in Results branch, directly visualizes cell geometry evolution, circumferential stress anisotropy and wall stiffness distribution across developmental stages 8 to 14.

## Required COMSOL Modules
- Solid Mechanics Module
- Mathematics Module (for custom morphoelastic growth & stress feedback functions)

## Step-by-Step Reproduction Guide
1. Launch COMSOL Multiphysics 6.4 with Solid Mechanics enabled
2. Open `Main_simulation.mph`
3. All adjustable parameters, pH gradient decay functions, mechanical feedback coefficients are preset in **Global Definitions - Parameters** and Component 1 - Definitions
4. Run simulation in fixed order:
   1) Click Study 1 (Stationary) : Compute, generate initial equilibrium field
   2) Click Study 2 (Time Dependent) : Compute, execute full developmental transient growth simulation
5. After computation completes: Navigate to the **Results** folder, open plot group `Plot` to view time-series morphological evolution, circumferential stress anisotropy contour plots matching Fig. 4 in the manuscript.

## Model Scientific Background
This finite element model reproduces the biochemical-to-mechanical signal relay regulatory pathway of Arabidopsis petal conical cell morphogenesis:
1. Apoplastic pH gradient modulates spatial cell wall extensibility to drive differential early cell growth
2. Non-uniform growth generates circumferential tensile stress anisotropy on cell shell
3. Stress-dependent mechanical feedback (mimicking cortical microtubule alignment) dynamically adjusts wall elastic modulus to lock and refine conical cell shape
4. Five simulation scenarios (Simu.1 to Simu.5) are encapsulated in parameter switching to recapitulate WT, ktn1-4 mutant, ost2-2D mutant and oryzalin-treated cell phenotypes in Fig.4.

## License
MIT License, see LICENSE file

## Permanent Archive DOI
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.XXXXXXX.svg)](https://doi.org/10.5281/zenodo.XXXXXXX)
All simulation files to reproduce Figure 4 are permanently archived at Zenodo for citation.
