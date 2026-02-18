# Pole-Climbing Robot

## Overview
Designed and developed a wheel-based dual-arm robotic system capable of vertical pole climbing and obstacle navigation for industrial inspection and worker safety applications.

---

## Problem Statement
Manual pole inspection in industries such as utilities and forestry poses significant safety risks and operational inefficiencies. This project aims to automate vertical climbing and obstacle traversal using an electromechanical robotic system.

---

## System Architecture


![System Architecture](media/System_Architecture.png)

- Dual motorized gripping arms
- Wheel-based climbing mechanism
- Sequential arm coordination for obstacle navigation
- Microcontroller-based control logic
- Sensor-based obstacle detection

---

## Control Strategy
- Finite State Machine (FSM) for arm coordination
- Upper-arm release while lower-arm maintains load during obstacle crossing
- Sensor-triggered state transitions
- Synchronized motor control for stable vertical climbing

---

## Technologies Used
- Embedded C / Microcontroller Programming
- DC Motor Drivers
- Electromechanical Design
- Control Systems
- Mechanical CAD

---

## Current Status
Prototype development and system architecture validation in progress.

### Upper Stage Under Test
![Project Demo](media/WPCR_Descending.gif)

---

## Future Improvements
- Closed-loop torque control
- IMU-based stabilization
- Vision-based obstacle detection
- Load analysis and stress optimization
