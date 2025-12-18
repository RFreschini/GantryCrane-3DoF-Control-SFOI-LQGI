# 3DoF Gantry Crane Control: SFOI (Pole Placement) and LQGI

## Introduction
The model considered in this project is inspired by gantry cranes widely used in naval and industrial applications. Starting from a simplified and schematized version of the original system, we derive the nonlinear equations of motion and subsequently linearize them. Once the linearized model is obtained, we analyze controllability and observability, and then implement and test different control strategies.

This work uses the model presented in the paper:

> **Robust qLPV Tracking Fault-Tolerant Control of a 3 DOF Mechanical Crane**  
> Francisco-Ronay López-Estrada, Oscar Santos-Estudillo, Guillermo Valencia-Palomo, Samuel Gómez-Peñate, Carlos Hernández-Gutiérrez  
> *Mathematical and Computational Applications*, Vol. 25, Issue 3, 2020.  
> DOI: [10.3390/mca25030048](https://doi.org/10.3390/mca25030048)

---

## Control Strategies
Two control approaches have been implemented and compared:

- **SFOI (State Feedback with Observer + Integrator, Pole Placement)**  
  Pole placement design with observer and integral action to ensure zero steady-state error and compliance with performance specifications.

- **LQGI (Linear Quadratic Gaussian + Integrator)**  
  Optimal control design combining LQG with integral action to achieve robustness against disturbances and minimize oscillations.

---

## Objectives and Specifications
The main control objective is to **limit the oscillation of the suspended mass during cart motion** while ensuring accurate tracking of reference positions.

Control specifications are defined as follows:

- **Settling time (Ta):** 18 s for a cart displacement of 1 meter.  
- **Percent overshoot (PO):** ≤ 3% for cart displacement.  
- **Steady-state error:** Zero for both cart position and cable length.  
- **Peak swing (PS):** Maximum pendulum angle ≤ 9°.  

---

## Repository Structure 
- `Scripts/` → Scripts for performance evaluation.  
- `Results/` → Figures showing tracking, oscillation suppression, and control effort.  

---

## Results
Simulation results demonstrate that both controllers achieve the desired specifications, with LQGI providing improved robustness against disturbances, while SFOI offers direct pole placement flexibility. Comparative plots of cart position, cable length, and pendulum swing are included in the `Results/` directory.

---


