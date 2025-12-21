---
layout: project
title: Weed Wacker Dissection
description: Fluid Mechanics Analysis 
technologies: [Fluid Mechanics, Four-Stroke Engines, Venturi Analysis, Reynolds Number, Bernoulli's Equation]
image: /assets/images/weedwacker_exploded_view.png
---

[Watch Project Video](https://youtu.be/Y-2mskxOUhQ)

As part of my MAE 3230 (Fluid Mechanics) at Cornell University, our team conducted a full mechanical dissection and fluid-mechanics analysis of a four-stroke weed wacker engine. The objective was to investigate how fundamental fluid mechanics principles, specifically continuity, Reynolds number, and Bernoulli’s equation, govern airflow and fuel within a carburetor venturi.

## Project Overview

At first glance, a weed wacker appears simple: a handheld tool that spins a cutting line at high speed. Beneath this simplicity, however, lies a compact internal combustion engine whose performance is dictated by fluid mechanics. This project explores that hidden complexity through the dissection and analysis of a carburetor venturi, connecting theoretical models to the behavior of a real engineering system.

**Project Objectives:**
- Disassembled a 4-stroke weed wacker engine
- Created an exploded view of the major components
- Measured approximate carburetor venturi dimensions
- Calculated airflow velocities using the continuity equation
- Confirmed a high Reynolds number approximation
- Used Bernoulli's equation to explain how pressure differences drive fuel flow 
- Produced an educational video explaining the fluid mechanics behind the system

<div style="clear: both;"></div>

## System Components

### Cooling Turbine

<div style="display:flex; gap:24px; align-items:flex-end;">

  <div style="text-align:center;">
    <img src="/assets/images/weedwacker_flywheel.png" style="height:260px; width:auto;">
    <div style="font-style:italic; margin-top:6px;">
      Figure 1. Flywheel
    </div>
    </div>
</div>


The cooling turbine directs airflow over the engine to dissipate heat generated during combustion and ignition. The flywheel, with added mass around its perimeter, helps maintain smooth rotational motion while drawing air through the volute—an Archimedean spiral–shaped housing that guides cooling airflow across the engine.

The flywheel also contains a small magnet that generates an ignition spark each time it passes the coil, providing consistent timing for combustion.

### Four-Stroke Engine

<div style="display:flex; gap:24px; align-items:flex-end;">

  <div style="text-align:center;">
    <img src="/assets/images/weedwacker_piston.png" style="height:260px; width:auto;">
    <div style="font-style:italic; margin-top:6px;">
      Figure 2. Piston
    </div>
  </div>

  <div style="text-align:center;">
    <img src="/assets/images/weedwacker_stroke.png" style="height:260px; width:auto;">
    <div style="font-style:italic; margin-top:6px;">
      Figure 3. Four-Stroke Cycle
    </div>
  </div>

  <div style="text-align:center;">
    <img src="/assets/images/weedwacker_cam.png" style="height:260px; width:auto;">
    <div style="font-style:italic; margin-top:6px;">
      Figure 4. Camshaft
    </div>
  </div>

</div>


The weed wacker uses a compact 4-stroke gasoline engine, which comes to life when the flywheel's spark initiates combustion. The engine follows the standard four-stroke cycle, with valve timing controlled by a camshaft mechanically linked to the crankshaft.

- **Intake Stroke:**
The intake valve opens as the piston moves downward, allowing the air–fuel mixture from the carburetor to enter the combustion chamber. The camshaft rotates at a reduced angular velocity relative to the crankshaft to ensure proper valve timing.

- **Compression Stroke:**
The intake valve closes, sealing the combustion chamber while the piston compresses the air–fuel mixture.

- **Power Stroke:**
The spark plug ignites the compressed mixture, forcing the piston downward and converting chemical energy into mechanical work.

- **Exhaust Stroke:**
The exhaust valve opens as the piston moves upward, expelling combustion products through the exhaust port. Minor amounts of unburned fuel may exit due to incomplete combustion.

<div style="clear: both;"></div>

## Carburetor and Venturi Analysis

<div style="display:flex; gap:24px; align-items:flex-end;">

  <div style="text-align:center;">
    <img src="/assets/images/weedwacker_carburetor.png" style="height:260px; width:auto;">
    <div style="font-style:italic; margin-top:6px;">
      Figure 5. Carburetor
    </div>
  </div>

  <div style="text-align:center;">
    <img src="/assets/images/weedwacker_venturi.png" style="height:260px; width:auto;">
    <div style="font-style:italic; margin-top:6px;">
      Figure 6. Venturi
    </div>
  </div>
</div>


A key component is the carburetor, where separate inlet passages regulate the flow of air and fuel. When opened, these streams enter the venturi, a converging passage that accelerates the airflow and reduces static pressure at the throat. Under normal operating conditions, the flow remains subsonic (Mach < 1), and the resulting pressure drop entrains fuel into the airstream. This mechanism enables controlled air–fuel mixing and supports an approximately stoichiometric mixture to the engine.

The venturi therefore serves as the central focus of the fluid mechanics analysis, illustrating how geometry and flow velocity generate the pressure difference required for passive fuel delivery.

<div style="clear: both;"></div>

## Fluid Mechanics Analysis

### Assumptions and Approximations

**Incompressible Flow Model:**
The flow is assumed to remain incompressible, as the Mach number is maintained below 0.3 and density variations are negligible. Under this assumption, density may be treated as constant, allowing the use of simplified continuity and Bernoulli equations.

**High Reynolds Number Approximation:**
As shown in the subsequent analysis, Reynolds numbers at both the inlet and venturi throat exceed 3,000, indicating turbulent flow in which viscous effects are secondary. This justifies the use of inviscid flow equations in the analysis.

### Venturi Geometry

The venturi dimensions obtained are as following:

**Inlet diameter:** d₁ ≈ 5.5 inches = 0.1397 m  
**Throat diameter:** d₂ ≈ 4 inches = 0.1016 m

**Cross-sectional areas:**
```
A₁ = π/4 × d₁² = π/4 × (0.1397 m)² = 0.0153 m²
A₂ = π/4 × d₂² = π/4 × (0.1016 m)² = 0.0081 m²
```

### Continuity Equation Analysis

In the converging section of the venturi, we can use conservation of mass to show that at the throat, the speef of the fluid increases:
```
ρ₁U₁A₁ = ρ₂U₂A₂
```

Because of the incompressible flow assumption, ρ₁ = ρ₂, so the densities cancels each other:
```
U₁A₁ = U₂A₂
```

We know that the throat has a smaller area, therefore the speed at the throat must be greater:
```
U₂/U₁ = A₁/A₂ = 0.0153/0.0081 = 1.89
```

**U₂ is almost twice the value of U₁.**

<div style="clear: both;"></div>

### Flow Rate Calculation

To get the exact values of U₁ and U₂, we calculated the volumetric flow rate from its relationship to the engine RPM, piston area, and cylinder length.

**Engine and Piston Specifications:**
- Piston diameter: D_piston = 1.48 in = 3.76 cm = 0.0376 m
- Cylinder length: L_cylinder = 2.2 in = 5.588 cm = 0.05588 m
- Engine speed: ω_engine = 7000 rpm

**Piston area:**
```
A_piston = π/4 × D² = π/4 × (0.0376 m)² = 0.00111 m²
```

**Volumetric flow rate:**
```
Q = ω_engine × A_piston × L_cylinder
Q = 7000 rpm × (1 min/60 s) × 0.00111 m² × 0.05588 m
Q = 0.00724 m³/s
```

**Inlet velocity:**
```
U₁ = Q/A₁ = 0.00724 m³/s / 0.0153 m² = 0.472 m/s
```

**Throat velocity:**
```
U₂ = 1.89 × U₁ = 1.89 × 0.472 m/s = 0.892 m/s
```

<div style="clear: both;"></div>

### Reynolds Number Validation

We calculated the Reynolds numbers were at two locations to validate the high–Reynolds-number assumption. Let's assume this is prior to the mixture of fuel into air, so the only fluid of interest is air.

**Air properties:**
- Viscosity: μ_air = 1.8 × 10⁻⁵ Pa·s
- Density: ρ_air = 1.225 kg/m³

**Reynolds number at inlet:**
```
Re₁ = (ρ × U₁ × d₁) / μ
Re₁ = (1.225 kg/m³ × 0.472 m/s × 0.1397 m) / (1.8 × 10⁻⁵ Pa·s)
Re₁ = 4,488
```

**Reynolds number at throat:**
```
Re₂ = (ρ × U₂ × d₂) / μ
Re₂ = (1.225 kg/m³ × 0.892 m/s × 0.1016 m) / (1.8 × 10⁻⁵ Pa·s)
Re₂ = 6,171
```

**Both Reynolds numbers are above 3,000**, which allows us to use high Reynolds number approximations. This means we can assume that viscosity is negligible and use inviscid flow equations.

<div style="clear: both;"></div>

## Bernoulli's Equation Application

At high Reynolds number, Bernoulli’s equation is used to describe the pressure variation within the converging section of the venturi:
```
p₁ + ½ρU₁² + ρgz₁ = p₂ + ½ρU₂² + ρgz₂
```

**Key observations:**

Since z₁ = z₂ (no altitude changes), the gravitational terms cancels out:
```
p₁ + ½ρU₁² = p₂ + ½ρU₂²
```

We already know that U₂ ≈ 2U₁ from our continuity analysis. After rearranging Bernoulli's equation:
```
p₂ = p₁ + ½ρ(U₁² - U₂²)
p₂ = p₁ + ½ρ(U₁² - 4U₁²)
p₂ = p₁ - 1.5ρU₁²
```

**Therefore, p₂ < p₁**

The pressure reduction at the venturi throat drives fuel into the airstream. The fuel jet is located at this low-pressure region, allowing atmospheric pressure within the fuel bowl to force fuel through the jet and into the airflow.

**Physical mechanism:**
The pressure differential (p₁ - p₂) provides the driving force for fuel flow. As air accelerates through the converging section of the venturi, its kinetic energy increases while static pressure decreases. This pressure drop induces fuel flow into the airstream without the need for any mechanical pumping mechanism.

<div style="clear: both;"></div>

## Design Considerations

You might wonder—why is the design as it is? Why not a bigger system?

**Size Trade-offs:**
A bigger engine allows for more power, but it would also make the tool heavier and harder to control. Handheld equipment must balance power requirements with user ergonomics and fatigue.

**Internal Geometry:**
The internal geometry matters just as much as the size. The shape and curvature of the carburetor passages control how air and fuel move, mix, and accelerate. 

**Surface Effects:**
Even the surface texture plays a role:
- **Rough surfaces**: Adds turbulence and friction, increasing pressure losses
- **Smoother surfaces**: Support faster, cleaner flow with lower resistance

The venturi dimensions we measured represent an optimized balance:
- Throat area small enough to create sufficient pressure drop for fuel delivery
- But not so small as to excessively restrict airflow and limit power
- Convergence angle gradual enough to avoid flow separation
- Overall size compact enough for lightweight handheld operation

<div style="clear: both;"></div>

## Key Findings

**Velocity Amplification:**
The 1.89× area ratio between inlet and throat produces 1.89× velocity increase, demonstrating the direct relationship between geometry and flow behavior predicted by continuity.

**High Reynolds Number Flow:**
With Re > 4,000 throughout the carburetor, viscous effects are negligible. This validates using inviscid flow models (Bernoulli's equation) for analysis and design.

**Pressure-Driven Fuel Delivery:**
The ~75% pressure drop at the throat (based on Bernoulli's equation with U₂ = 2U₁) creates sufficient suction to draw fuel through calibrated jets without mechanical pumps. This passive fuel metering is reliable and simple.

**Subsonic Choked Flow:**
The converging-diverging venturi maintains Mach < 1 throughout, keeping the flow subsonic. This ensures predictable, controllable fuel delivery across the engine's operating range.

**Design Optimization:**
Every dimension matters—the 5.5" to 4" diameter reduction represents careful optimization balancing fuel delivery requirements, airflow capacity, and manufacturing constraints.

<div style="clear: both;"></div>

## Conclusion

This is just one of the many clever machines hiding in everyday life, and once you start noticing them, the world becomes a toolbox full of fluid mechanics in action.

From the Archimedean spiral cooling volute to the shape of the venturi throat, this compact weed wacker reveals how fundamental fluid mechanics principles, such as continuity, Bernoulli’s equation, and Reynolds number analysis, quietly govern devices we use in our daily lives.

This short 5-minute dissection analysis showed how a pressure drop of only a few hundred pascals, is enough to drive fuel in a machine small enough to hold in one hand. This project demonstrates how fluid mechanics turns simple geometry into powerful, practical engineering.

<div style="clear: both;"></div>

## Individual Contribution
I contributed to the physical dissection of the weed wacker engine and measured key geometric dimensions of the carburetor venturi used in the fluid mechanics calculations. I provided voiceover narration for the project video, explaining the system design, flow behavior, and key fluid mechanics insights. I was responsible for editing the full video, including synchronizing and refining all voiceover recordings, integrating animations, and modifying the animations to remove unnecessary segments and ensure clear alignment between the visuals and the technical narrative. 

## Team Members

**Carmen Lin, Catherine Guo, Gina Liu, Laura Ren, Rochelle Gao**

## Project Details

**Course:** MAE 3230 - Fluid Mechanics, Fall 2025  
**Institution:** Cornell University
**Analysis Focus:** Carburetor venturi fluid mechanics  
**Key Calculations:** Continuity equation, Reynolds number, Bernoulli's equation  
**Deliverables:** Educational video, quantitative analysis, component documentation

---

This project demonstrates how fundamental fluid mechanics principles translate directly from theory to real engineering systems, highlighting the predictive power of first-principles analysis in mechanical design.