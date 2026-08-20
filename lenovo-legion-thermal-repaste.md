# Lenovo Legion Y7000P-1060 — Thermal Repaste & Fan Cleaning

**Date:** August 2026  
**Device:** Lenovo Legion Y7000P-1060  
**OS:** Windows 11  
**Status:** Resolved ✅

---

## Problem

After extended use the laptop developed two issues:

- **Fan noise** — one fan making a grinding/rough sound, especially noticeable in quiet environments and when slight pressure was applied to that side of the laptop
- **High CPU temperatures** — CPU hitting 80s-90°C under gaming load, suggesting degraded thermal paste from the original factory application

---

## Root Cause

**Two separate issues identified:**

1. **Worn fan bearing** — the CPU fan bearing had degraded over time causing a grinding noise under load. Cleaning removed debris contributing to the noise.

2. **Dried thermal paste** — the original factory thermal paste had dried out and hardened over the years, significantly reducing heat transfer between the CPU/GPU and the heatsink. This caused the CPU to run 15-20°C hotter than it should under load.

Both issues are common on laptops that are several years old and are part of normal hardware maintenance.

---

## Parts & Tools Used

| Item | Purpose |
|---|---|
| Arctic MX-4 Thermal Compound | Replacement thermal paste |
| Isopropyl Alcohol 90%+ | Cleaning old paste off CPU/GPU and heatsink |
| Lint free cloth | Applying IPA without leaving fibers |
| Phillips screwdrivers | Laptop disassembly |
| Compressed air | Cleaning dust from fans and vents |

---

## Repair Process

### Step 1 — Identify the issues
- Fan noise started after extended use, not immediately on startup
- Noise changed when slight pressure applied to left side of laptop
- Confirmed worn bearing diagnosis — bearing noise changes under physical pressure
- Downloaded HWMonitor (CPUID) to monitor temps and confirm thermal paste degradation

### Step 2 — Research correct parts
- Identified fan part numbers directly from stickers on original fans:
  - **CPU Fan:** DC28000DMF0
  - **GPU Fan:** DC28000DMF1
- Attempted to source replacement fans — limited availability for this specific model
- Decision made to clean existing fans and proceed with thermal repaste

### Step 3 — Disassembly
- Powered off laptop and unplugged charger completely
- Removed all bottom panel screws
- Carefully lifted bottom panel
- Disconnected battery connector before touching any components
- Took note of fan cable routing and connector positions

### Step 4 — Fan cleaning
- Disconnected both fan connectors carefully
- Used compressed air to blow out dust from fan blades and heatsink fins
- Cleaned fan blades manually to remove built up debris
- Reconnected fan cables ensuring proper orientation

### Step 5 — Thermal paste replacement
- Removed heatsink screws in X pattern to ensure even pressure release
- Lifted heatsink away from CPU and GPU
- Cleaned old dried thermal paste completely off:
  - CPU die
  - GPU die
  - Heatsink contact surfaces
  - Used IPA and lint free cloth until surfaces were clean
- Applied pea sized amount of Arctic MX-4 to center of CPU
- Applied pea sized amount of Arctic MX-4 to center of GPU
- Reattached heatsink — paste spreads naturally under heatsink pressure, no manual spreading needed
- Tightened heatsink screws in X pattern for even pressure

### Step 6 — Reassembly
- Reconnected battery connector
- Reattached bottom panel
- Replaced all screws

### Step 7 — Testing
- Booted system — confirmed successful POST and Windows load
- Monitored idle temps immediately after boot
- Ran gaming load (Roblox) for 10+ minutes to stress test
- Monitored temps throughout using HWMonitor

---

## Results

### Temperature Comparison

| Component | Before Repaste | After Repaste | Improvement |
|---|---|---|---|
| CPU (max under load) | 85-90°C | 67°C | ~18-20°C drop ✅ |
| GPU (max under load) | Not recorded | 54°C | Healthy range ✅ |
| Airflow temp | Not recorded | 33°C | Cool ✅ |
| CPU (idle) | Not recorded | 35-45°C | Excellent ✅ |

### Fan Results
- Both fans spinning confirmed post reassembly
- Fans running quietly and efficiently
- Cool air confirmed blowing from vents
- Original grinding noise significantly reduced after cleaning
- Fan bearing still worn — replacement fan (DC28000DMF0) on order when available

---

## Outstanding Issue

**CPU fan bearing** is still worn and will need replacement when the correct part becomes available:
- Part number needed: **DC28000DMF0**
- Fan is functional but has slight roughness noticeable in quiet environments
- Not urgent — temps are healthy and fan is spinning correctly
- Will replace during next teardown

---

## Key Lessons

- **Thermal paste should be replaced every 3-5 years** on laptops, especially gaming laptops that run hot regularly. Dried paste is one of the most common causes of overheating in older laptops.
- **Always identify exact part numbers** from the component sticker before ordering replacements — laptop variants can look identical but have different mounting patterns.
- **Fan bearing wear** is diagnosed by noise that changes under physical pressure — the bearing shifts slightly when pressed causing the sound to change.
- **Heatsink screws should be tightened in an X pattern** to ensure even pressure distribution across the CPU/GPU surface.
- **Disconnect the battery first** before touching any internal components to prevent shorts or damage.

---

## Skills Demonstrated

- Laptop hardware disassembly and reassembly
- Thermal paste application
- Hardware diagnostics using HWMonitor
- Fan diagnosis and cleaning
- Part number identification for component sourcing
- Temperature monitoring and performance validation
