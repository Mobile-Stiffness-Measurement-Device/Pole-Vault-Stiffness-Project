# Pole Vault Stiffness Project

📍 KTH CM2024 – Technology and Health / Sports Technology  
👥 Student Team Project  

---

## Overview
This project aims to design and prototype the world’s first mobile device to measure the relative stiffness of pole vaulting poles in real time.  

Currently, stiffness measurements are only performed during the manufacturing phase, using large and immobile rigs. Athletes and coaches have limited ability to track stiffness changes over a pole’s lifespan or compare across different brands. Our goal is to create a portable, repeatable, and easy-to-use solution for field measurements.  

---

## Problem
- Existing stiffness measurement tools are large and lab-based.  
- There is no easy way to check how poles evolve under different environments (temperature, humidity, time).  
- Manufacturers use different standards for flex numbers, making comparison difficult.  

---

## Concept
The device applies a controlled displacement to a mounted pole using a stepper-motor-driven actuator. A force sensor measures the load applied, while the stepper motor steps give displacement.  

From the force–displacement data, the relative stiffness is calculated:  

\[
k = \frac{ΔF}{Δx}
\]

Data can then be:  
- **Saved** per pole (brand, length, flex rating, date).  
- **Analyzed** for environmental effects (temperature, humidity).  
- **Compared** across different brands and pole models.  

---

## Hardware System
- **DC Power Supply** → provides power to electronics and motor.  
- **Raspberry Pi Pico** → main microcontroller for motor control and sensor acquisition.  
- **DRV8825 Driver** → drives the stepper motor.  
- **Stepper Motor + Rope** → applies controlled displacement on the pole.  
- **Force Sensor** → measures pulling force in real time.  

---

## Software & Data
- **Firmware** (Pico, MicroPython/C): controls motor steps, streams force data.  
- **Acquisition Scripts** (Python, PC): logs force–displacement data to CSV.  
- **Analysis Toolkit** (Python, Jupyter):  
  - Stiffness vs. displacement curves  
  - Stiffness over time/environment  
  - Brand-to-brand comparisons  

---

## Features
- Mobile and field-ready (portable setup).  
- Real-time data display and logging.  
- Save results per pole with metadata (brand, length, flex, date, humidity, temperature).  
- Generate stiffness curves and compare across tests.  
- Future app integration (BLE or USB) for direct display and data management.  

---

## Workstreams
- **Electronics** → Pico firmware, DRV8825 driver control, force sensor integration.  
- **Mechanics** → Frame, stepper mount, rope/pulley system, sensor placement.  
- **Assembly** → Integrating electronics, wiring, and structural parts.  
- **Database** → Organizing test metadata (pole model, brand, flex, temp, humidity).  
- **App** → Mobile interface for live display, saving, and comparing poles.  

---

## Repository Structure

