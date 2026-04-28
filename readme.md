# Orbital Flight Dynamics Simulator

A high-fidelity, browser-based flight telemetry and physics simulator designed to model vehicle ascent profiles through non-linear atmospheric conditions.

[**🚀 Launch Live Simulation**](https://github.io)

## 🛰️ Overview
This project serves as a technical demonstration of **real-time data visualization** and **deterministic physics modeling**. It simulates a vertical ascent from pre-flight configuration through ignition, atmospheric transit, and orbital insertion milestones.

## 🛠️ Technical Architecture

### 1. Physics Engine (Deterministic Integration)
The simulator utilizes a 60Hz Newtonian integration loop to compute vehicle state:
*   **Mass Dynamics:** Models instantaneous mass reduction via fuel consumption based on a constant **Specific Impulse (Isp)** of 311s.
*   **Aerodynamics:** Implements the **Standard Drag Equation** ($F_d = \frac{1}{2} \rho v^2 C_d A$) with an exponential atmospheric density model ($\rho$).
*   **Thrust-to-Weight Ratio (TWR) Validation:** Implements a safety interlock system that prevents sequence initiation if $TWR \le 1.0$.

### 2. Software Architecture
*   **State Machine:** Manages mission transitions (`PREFLIGHT` → `COUNTDOWN` → `POWERED_FLIGHT` → `COASTING`).
*   **Rendering:** High-performance data plotting using the **HTML5 Canvas API** to ensure smooth 60fps telemetry visualization without DOM overhead.
*   **Reactive UI:** Real-time parameter adjustment allows for testing of vehicle structural mass and engine performance during active flight.

## 📊 Mission Event Logging
The system includes a sequential event logger that tracks:
*   **T-Minus Sequence:** Validates system readiness during the final 10 seconds.
*   **Milestone Detection:** Automated triggers for **Max-Q** (Troposphere exit) and the **Karman Line** (Space boundary).
*   **Anomaly Reporting:** High-fidelity impact detection and engine state monitoring.

## 📈 Future Roadmap
- [ ] **Multi-Stage Separation:** Implementing mass-discontinuity logic for stage jettison.
- [ ] **Gravity Turn Modeling:** Shifting from 1D vertical ascent to 2D trajectory plotting.
- [ ] **PID Controller Integration:** Automated throttle management to optimize dynamic pressure.

---
**Author: Jesuino Azevedo 
**Objective:** Technical demonstration of aerospace software principles.
