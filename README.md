# Pole Vault Stiffness Project

📍 KTH CM2024 – Technology & Health / Sports Technology  
👥 Student Team Project

---

## Overview
We are building a mobile, field-ready device that measures the relative stiffness of pole vault poles in real time using force–displacement data. The device applies a controlled displacement with a stepper-motor actuator while a force sensor records load, enabling athletes, coaches, and manufacturers to track stiffness over time, compare brands, and evaluate environmental effects (temperature, humidity).

---

## Problem
- Existing stiffness measurement tools are large and lab-based.  
- There is no easy way to monitor how poles evolve across environmental conditions (temperature, humidity) and time/use.  
- Manufacturers use different flex standards, complicating comparison.  
- Field measurements need repeatability and portability.

---

## Concept
A stepper-motor-driven actuator (via DRV8825) applies a controlled displacement to a mounted pole. A force sensor (inline with the rope/load path) measures the applied load. Displacement is derived from step counts and mechanics (lead/microstepping), and paired with force to compute relative stiffness:

$$k = \frac{F}{\Delta x}$$

We store results with metadata (pole brand, length, flex, date, humidity, temperature) to:
- **Save** and organize measurements per pole  
- **Analyze** environmental effects (humidity, temperature, time)  
- **Compare** stiffness across brands and models  
- **Export** results to CSV/JSON for later analysis

---

## Hardware System
- **DC Power Supply** → provides power to electronics and motor  
- **Raspberry Pi Pico** (MicroPython) → motor control & sensor acquisition  
- **DRV8825 Driver** → drives the stepper motor (microstepping)  
- **Stepper Motor + Rope** → applies controlled displacement to the pole  
- **Force Sensor** → measures applied load (via load cell + ADC, e.g., HX711)  
- **Structure/Fixture** → holds the pole, aligns the load path, ensures safety and repeatability

> _Planned_: add a wiring diagram and photo in `hardware/wiring/`.

---

## Software & Data
- **Firmware** (Pico, MicroPython): generates steps, reads force sensor, streams CSV over USB serial  
- **Acquisition** (Python on PC): opens serial port, logs time-stamped force–displacement data to `data/raw/*.csv`  
- **Analysis** (Python/Jupyter): processes and visualizes stiffness curves, compares tests/brands, overlays environment

**Core analyses**:
- Stiffness vs. displacement curve  
- Relative stiffness over time / environment (temperature, humidity)  
- Cross-brand comparisons (same pole length & flex rating)

---

## Features
- Portable, field-ready workflow  
- Real-time streaming + logging (CSV)  
- Per-pole data and metadata storage  
- Plots for stiffness vs. displacement and environment overlays  
- (Planned) BLE/USB app for live display and comparisons

---

## Repository Structure


