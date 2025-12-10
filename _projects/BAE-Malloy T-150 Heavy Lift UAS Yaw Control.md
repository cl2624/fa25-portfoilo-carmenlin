---
layout: project
title: Analysis of the BAE/Malloy T-150 Heavy Lift UAS Yaw Control
description: Yaw Dynamics Modeling and PID Control Design
technologies: [MATLAB, Simulink, Latex]
image: /assets/images/BAE_Malloy_T150_Heavy_Lift_UAS.png
---

For my System Dynamics course (MAE 3260), I worked with a team of four to perform a dynamic analysis of the yaw control system of the BAE/Malloy T-150 Heavy-Lift UAS, a quadcopter widely used in industrial and defense applications. Because multirotor platforms are governed by nonlinear flight dynamics, our team first established a linearized representation of the yaw subsystem under steady, nominal flight conditions to enable classical control design.

My primary contributions to the project included:

- Deriving the governing nonlinear ODEs for yaw rate and yaw angle

- Constructing the state-space model matrix governing the yaw dynamics

- Formulating the transfer function representation of the system

- Developing the block diagram for the yaw control loop, utilizing the PID controller

- Performing Bode plot and frequency-response analysis to evaluate stability margins and tune PID gains, including a comparison of the system’s behavior with payload versus without payload

Using these tools, our team designed and evaluated a PID-based yaw controller that continuously uses the measured output to correct the quadcopter’s orientation, altering motor inputs to minimize yaw error, reject disturbances, and maintain stable flight.

## Project Details

**Course:** MAE 3260 - System Dynamics, Fall 2025 
**Institution:** Cornell University  
**Tools:** MATLAB, Simulink, Latex
**Analysis Methods:** System dynamics modeling, ODE derivation and linearization, state-space formulation, transfer function development, block-diagram modeling, Bode plot and frequency-response analysis, PID controller design and tuning
**Deliverables:** [View Full technical report] (/assets/Systems_Final_HW.pdf)

---

This project integrates system dynamics, control theory, and computational modeling, reflecting the core skill set required for mechanical engineers to design stable, responsive, and high-performance flight-control systems.