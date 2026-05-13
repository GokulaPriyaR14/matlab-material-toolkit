# MATLAB Material Engineering Toolkit

A collection of three interactive MATLAB tools I built to make material selection and failure analysis faster and more visual — the kind of work that usually gets done manually with tables and calculators.

---

## Why I Built This

In mechanical engineering, choosing the right material for a component involves comparing dozens of properties across hundreds of materials. Most students and even early-career engineers do this by flipping through data sheets. I wanted to see if I could make that process visual, interactive, and faster — so I built these three tools.

The material data is referenced from the **ASM International Handbook** and **MatWeb** — the same sources used in industry software like CES EduPack.

---

## What's Inside

### Material Properties Comparison Dashboard
`MaterialDashboard.m`

Select any combination of materials from a list of 20 and compare their mechanical properties side by side. The dashboard generates bar charts, a radar chart showing normalized properties across all six dimensions at once, and a horizontal strength-to-weight ratio chart. There's also a built-in recommender — pick a use case like Aerospace or Biomedical and it suggests the top three materials with reasoning.

**Materials:** Mild Steel, Stainless Steel 304, Tool Steel, Aluminium 6061, Aluminium 7075, Titanium Ti-6Al-4V, Copper, Brass, Cast Iron, Carbon Fibre (CFRP), Magnesium AZ31, Nickel Alloy 718, Polycarbonate, Nylon PA66, ABS Plastic, Bronze, Tungsten, Inconel 625, Glass Fibre (GFRP), Beryllium

**Properties:** Young's Modulus, Yield Strength, Tensile Strength, Density, Hardness, Poisson's Ratio, Strength-to-Weight Ratio

---

### Material Failure Analysis Tool
`FailureAnalysis.m`

Input your material, loading type, cross-section geometry, and dimensions — the tool calculates the actual stress on the component, compares it against the material's yield strength, and gives you a Factor of Safety along with a clear PASS, WARNING, or FAIL verdict.

Supports four loading conditions — axial, bending, torsion, and shear — and four cross-section types — solid circular rod, hollow shaft, rectangular bar, and I-section beam. The exact formula used for each calculation is displayed so you can verify the working.

**Example:** A Titanium Ti-6Al-4V solid rod, 30 mm diameter, under 50 kN axial load with a required FOS of 2.0 — the tool tells you instantly whether it's safe.

---

### Ashby Material Selection Chart
`AshbyChart.m`

An implementation of the Ashby Chart — an industry-standard tool that materials engineers use when they need to pick the best material for a design with competing requirements. Every material is plotted as a bubble on a two-property chart, with a third property encoded in the bubble size.

You can choose any property for the X axis, Y axis, and bubble size. Switch to log scale when property ranges span several orders of magnitude. Filter by material family — metals, light metals, polymers, composites. Click any bubble and the material's full details appear in the info panel.

The reason this chart matters: if you're designing for aerospace, you plot Density vs Tensile Strength. The best candidates — high strength, low weight — sit in the top-left corner. Titanium and Carbon Fibre land exactly there.

---

## How to Run

```matlab
% Set this folder as your Current Directory in MATLAB, then run:

MaterialDashboard    % opens the comparison dashboard
FailureAnalysis      % opens the failure analysis tool
AshbyChart           % opens the Ashby selection chart
```

Tested on MATLAB R2025b. No additional toolboxes required.

---

## Project Structure

```
matlab-material-toolkit/
│
├── MaterialDashboard.m
├── FailureAnalysis.m
├── AshbyChart.m
└── README.md
```

---

## References

- ASM International — *ASM Handbook, Volume 2: Properties and Selection*
- MatWeb — *Material Property Data*, [matweb.com](https://www.matweb.com)
- Ashby, M.F. — *Materials Selection in Mechanical Design*, Butterworth-Heinemann

---

**Gokula Priya R**
B.Tech Mechanical Engineering, NIT Calicut
Minor in Entrepreneurship and Business Analytics
