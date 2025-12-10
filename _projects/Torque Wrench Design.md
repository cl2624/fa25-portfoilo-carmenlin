---
layout: project
title: Torque Wrench Design
description: Stress/Strain Analysis
technologies: [Autodesk Fusion 360, ANSYS FEM, MATLAB, Mechanical Design, Stress Analysis]
image: /assets/images/torque_wrench.png
---

For my Mechanics of Materials course (MAE 3270), I designed and analyzed an instrumented torque wrench rated for 600 in-lbf using a combination of analytical calculations and finite element analysis (FEM). The project brought together key concepts in material selection, fracture mechanics, fatigue analysis, strain-gauge instrumentation, and structural optimization to create a design that is both accurate and mechanically reliable.

<div style="clear: both;"></div>

## Design Overview
The project required designing a non-ratcheting 3/8-inch drive torque wrench that measures applied torque using strain gauges bonded to the handle surface. The primary challenge was optimizing the wrench’s geometry and material selection to maximize strain-gauge sensitivity while still meeting safety requirements for static loading, crack-growth, and fatigue failure.

**Key Design Requirements:**
- Minimum 1.0 mV/V output at rated torque (600 in-lbf)
- Safety factor ≥ 4.0 for yield/brittle failure
- Safety factor ≥ 2.0 for crack growth (0.04 inch assumed initial crack)
- Safety factor ≥ 1.5 for fatigue (10⁶ cycles, fully reversed loading)
- Material limited to steel, aluminum, or titanium alloys

With the help of my partner, Laura Ren, we collaboratively developed a torque wrench that met the design requirements. We worked together on the MATLAB, material, and dimensions selection. All CAD modeling, finite element analysis (FEM), and the written documentation following were completed independently by me.

<div style="clear: both;"></div>

## Design Optimization

### Material Selection
I selected **Ti-6Al-4V (aged)** for its combination of high strength and low elastic modulus. 

**Material Properties**
- Young's Modulus: 16.1×10⁶ psi
- Tensile Strength: 148 ksi
- Fracture Toughness: 74.6 ksi√in
- Fatigue Strength (10⁶ cycles): 90 ksi
- Poisson's Ratio: 0.35

### Geometric Design
Through repetitive MATLAB calculations, these were the dimensions that satisfied the objectives:

**Final Design Dimensions**
- Total length: 17.644 in
- Length (L): 16 in
- Width (h): 0.5 in
- Thickness (b): 0.5 in
- Gauge location (c): 1 in

![Dimensions]({{ "/assets/images/torque_wrench_side_view.png" | relative_url }}){: .inline-image-c width="600px"} 
*Figure 1. Dimensions (Side View)*
![Dimensions]({{ "/assets/images/torque_wrench_top_view.png" | relative_url }}){: .inline-image-c width="600px"} 
*Figure 2. Dimensions (Top View)*

In the final design, the overall length remained similar, but the handle dimensions and gauge placement were refined to improve performance. Reducing the width from 0.75 to 0.5 inches raised the bending stress and strain for a given torque, increasing the strain-gauge output without jeopardizing strength. Retaining a 0.5-inch thickness maintained adequate torsional stiffness and avoided unnecessary stress concentrations. Keeping the gauge position at 1 inch ensured it remained in a region of high bending moment, supporting a strong and measurable signal. These combined adjustments improved strain sensitivity while maintaining the required static, fatigue, and fracture safety factors.

<div style="clear: both;"></div>

## Analytical Framework - Hand Calculations

Using beam theory, our hand calculations state the following about our design:
- Deflection at load point is 0.611 inches.
- Max Normal Stress is 28.8 ksi.
- Strain Gauge value is 1.677e-3.
- Voltage Output to Input is 1.68e-3 V/V.

[View MatLab Code](/assets/Materials_Final_HW_MatLab_Code.pdf)

![Total deformation contour]({{ "/assets/images/torque_wrench_deformation.png" | relative_url }}){: .inline-image-c width="600px"} 
*Figure 3. Total deformation contour (FEM).*

**Safety Factor Analysis**
All safety factors comfortably exceeded minimum requirements:
- **Strength**: 5.14 (required ≥ 4.0)
- **Crack Growth**: 6.52 (required ≥ 2.0)
- **Fatigue**: 3.12 (required ≥ 1.5)

Strength emerged as the limiting constraint, consistent with expectations for torque-loaded components. This validated the design approach and indicated that further dimension reduction would risk static failure before fatigue or crack growth.

<div style="clear: both;"></div>

## Finite Element Analysis
Using ANSYS, I developed a detailed finite element model of the final design to verify analytical predictions and identify stress concentrations that are overlooked by simple beam theory.

![Boundary Conditions]({{ "/assets/images/torque_wrench_boundary_conditions.png" | relative_url }}){: .inline-image-c width="600px"} 
*Figure 4. Boundary Conditions (Displacement and Force)*

### FEM Setup
- **Boundary Conditions**: Fixed constraint on upper 0.4 inches of drive block
- **Loading**: 37.5 lbf (lateral) at handle end (~600 in-lbf torque)

FEM Analysis revealed the following results:
- **Normal stress** in the gauge region: 82.7 ksi (~2.8 times higher than calculated)
- **Peak stress** at drive corner: 145.36 ksi (stress concentration factor ~5×)
- **Load point deflection**: 0.7 inches (approximate to the calculated 0.611 in)
- **Strain at gauge**: 1,677.2 microstrain (mV/V) (approximate to the calculated 1,677 microstrain)

![Normal Stress]({{ "/assets/images/torque_wrench_normal_stress.png" | relative_url }}){: .inline-image-c width="600px"} 
*Figure 5. Normal Stress (FEM)*
![Normal Strain]({{ "/assets/images/torque_wrench_normal_strain.png" | relative_url }}){: .inline-image-c width="600px"} 
*Figure 6. Normal Elastic Strain Contour Map (FEM)*

### Normal Strain Distribution

The normal strain contour plot, oriented in the strain-gauge measurement direction, shows a clear bending strain gradient along the wrench handle. Tensile strain develops on the lower surface (−z direction), with peak values reaching approximately 0.0023 in/in near the drive–handle interface where the bending moment is highest. At the designated gauge location, the FEM-predicted strain is ~1,677 microstrain, matching the analytical result and confirming that beam theory accurately captures strain behavior in the uniform section of the handle. The gradual decrease in strain along the beam length reinforces the benefit of placing the gauge close to the fixed end to maximize measurement sensitivity.

![Max Principal Stress]({{ "/assets/images/torque_wrench_deformation.png" | relative_url }}){: .inline-image-c width="600px"} 
*Figure 7. Max Principal Stress (FEM).*

### Maximum Principal Stress Analysis

The maximum principal stress contour highlights a severe stress concentration at the transition between the handle and the drive block. While the majority of the handle remains in a low-stress state (blue regions, well below 25 ksi), the sharp geometric discontinuity at the drive–handle interface produces a localized peak stress of 145.36 ksi. This represents a stress amplification of nearly five times the nominal bending stress—an effect that simple beam theory cannot capture. Such a concentration makes this corner the most probable site for fatigue crack initiation under repeated loading. This finding emphasizes the importance of including geometric features like fillets in production designs to reduce stress concentration factors and improve fatigue life.

### Strain Gauge Instrumentation
I decided that the OMEGA SGT-1LH/350-TY13 half bridge uniaxial strain gauge would be a good choice to test our torque wrench. Linked [here](https://br.omega.com/omegaFiles/pressure/pdf/SGT_HALF-BRIDGE-UNIAXIAL.pdf) is the spec sheet for this series of strain gauge models.

**Senstivity Calculation**:\\
Using FEM strain data (ε = 1,677 με) and gauge factor (GF = 2.0):
- Output = GF × ε / 2 = 2.0 × 0.001677 / 2 = 1.6772 mV/V
- **Performance**: Exceeds 1.0 mv/V  requirement by 67.72%

![Strain Gauge]({{ "/assets/images/torque_wrench_strain_gauge.png" | relative_url }}){: .inline-image-c width="600px"} 
*Figure 8. Strain Gauge (FEM).*

<div style="clear: both;"></div>

## Key Findings & FEM Comparison
- **Stress Analysis**: FEM predicted significantly higher stresses than beam theory. In the gauge region, the FEM bending stress was 82.7 ksi, roughly 2.8× the analytical value, due to local geometric effects not captured in the simplified hand calculation. More critically, FEM identified a peak stress of 145.36 ksi at the drive–handle transition, corresponding to a ~5× stress concentration. This location represents the most likely site for crack initiation and illustrates why beam theory alone is insufficient for evaluating real components with geometric discontinuities.
- **Deflection Analysis**: The FEM load-point deflection of 0.7 in was close to the analytical prediction of 0.611 in, with the remaining difference attributed to FEM accounting for compliance in the full 3-D structure rather than an idealized fixed support.
- **Strain Measurement**: FEM reported 1,677.2 µε, essentially identical to the analytical value. This confirms that beam theory provides reliable strain predictions in uniform sections away from geometric discontinuities.

<div style="clear: both;"></div>

## Project Details

**Course:** MAE 3270 - Mechanical Properties of Materials, Fall 2025  
**Institution:** Cornell University  
**Tools:** MATLAB, Autodesk Fusion 360, ANSYS FEM  
**Analysis Methods:** Beam theory, fracture mechanics, fatigue analysis, finite element method  
**Deliverables:** Technical report, CAD model, FEM analysis, design calculations

---

This project integrates materials science, solid mechanics, and computational analysis, reflecting the core skill set required for mechanical engineers to design safe, reliable, and high-performance components across all industries. 