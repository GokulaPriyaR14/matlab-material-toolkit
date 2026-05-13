MATLAB Material Engineering Toolkit

An interactive MATLAB-based toolkit for material selection, comparison, and failure analysis — built for mechanical engineering design workflow.

Overview
This toolkit was developed to assist mechanical engineers and students in making data-driven material selection and component safety decisions. It comprises three standalone MATLAB GUI applications, each targeting a specific stage of the material engineering workflow.
Material property data is sourced from ASM International Handbook and MatWeb — the same databases used in industry tools like CES EduPack.

Tools
1. Material Properties Comparison Dashboard
File: MaterialDashboard.m
An interactive dashboard to visually compare mechanical properties of 20 engineering materials side by side.
Features:

Multi-material selection with dynamic bar charts
Radar chart for normalized multi-property comparison
Horizontal strength-to-weight ratio chart
Use-case based material recommender (Aerospace, Automotive, Biomedical, Construction, Marine, Electronics)
Material info panel showing real-world applications
One-click CSV export of comparison table

Materials covered: Mild Steel, Stainless Steel 304, Tool Steel, Aluminium 6061, Aluminium 7075, Titanium Ti-6Al-4V, Copper, Brass, Cast Iron, Carbon Fibre (CFRP), Magnesium AZ31, Nickel Alloy 718, Polycarbonate, Nylon PA66, ABS Plastic, Bronze, Tungsten, Inconel 625, Glass Fibre (GFRP), Beryllium
Properties compared: Young's Modulus, Yield Strength, Tensile Strength, Density, Hardness, Poisson's Ratio, Strength-to-Weight Ratio

2. Material Failure Analysis Tool
File: FailureAnalysis.m
A stress analysis tool that computes whether a mechanical component will fail under applied loading, based on material strength and geometry.
Features:

Four loading types: Axial (Tension/Compression), Bending, Torsion, Shear
Four cross-section geometries: Solid Circular Rod, Hollow Circular Shaft, Rectangular Bar, I-Section Beam
Computes applied stress using standard mechanics of materials formulae
Von Mises equivalent stress for torsion and shear
Factor of Safety calculation and colour-coded gauge
Clear PASS / WARNING / FAIL verdict
Displays exact formula used for each calculation
User-defined required Factor of Safety

Example use case: Input a Titanium Ti-6Al-4V solid rod of diameter 30mm under 50kN axial load with required FOS of 2.0 — tool instantly tells you if the component is safe.

3. Ashby Material Selection Chart
File: AshbyChart.m
An implementation of the industry-standard Ashby Chart used by materials engineers worldwide for optimal material selection based on multiple competing properties.
Features:

User-selectable X axis, Y axis, and bubble size property
All 20 materials plotted simultaneously as labelled bubbles
Colour-coded by material family: Metals, Light Metals, Polymers, Composites
Log scale toggle for both axes
Material family filter to isolate specific groups
Click any bubble to instantly view full material details
Material labels toggle for clean or detailed view

Why Ashby Charts matter: In aerospace design, engineers plot Density vs Tensile Strength — materials in the top-left (high strength, low density) are optimal. This chart makes that selection process visual and instant.

How to Run

Clone or download this repository
Open MATLAB (R2022 or later recommended)
Set the folder as your Current Directory
Run any tool from the Command Window:

matlabMaterialDashboard    % Launch comparison dashboard
FailureAnalysis      % Launch failure analysis tool
AshbyChart           % Launch Ashby selection chart

Materials Database
FamilyMaterialsMetalsMild Steel, Stainless Steel 304, Tool Steel, Copper, Brass, Cast Iron, Bronze, Tungsten, Inconel 625, Nickel Alloy 718Light MetalsAluminium 6061, Aluminium 7075, Titanium Ti-6Al-4V, Magnesium AZ31, BerylliumPolymersPolycarbonate, Nylon PA66, ABS PlasticCompositesCarbon Fibre (CFRP), Glass Fibre (GFRP)
Data Sources: ASM International Handbook, MatWeb Material Property Database

Project Structure
matlab-material-toolkit/
│
├── MaterialDashboard.m      ← Properties comparison dashboard
├── FailureAnalysis.m        ← Stress and failure analysis tool
├── AshbyChart.m             ← Ashby material selection chart
└── README.md

Technical Details

Language: MATLAB
GUI Framework: MATLAB figure with uicontrol
Tested on: MATLAB R2025b
No additional toolboxes required


Author
Gokula Priya R
B.Tech Mechanical Engineering | NIT Calicut
Minor in Entrepreneurship and Business Analytics

Acknowledgements
Material property data referenced from:

ASM International — ASM Handbook, Volume 2: Properties and Selection
MatWeb — Material Property Data (matweb.com)
Ashby, M.F. — Materials Selection in Mechanical Design, Butterworth-Heinemann
