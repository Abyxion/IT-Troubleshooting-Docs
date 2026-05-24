# HP OmniBook X Flip 14 — Driver Recovery & WiFi Fix

**Date:** April 2026 (Puerto Rico)
**Device:** HP OmniBook X Flip 14-fm0023dx  
**OS:** Windows 11  
**Status:** Resolved ✅

-----

## Problem

Brand new HP OmniBook X Flip arrived with Windows installed but missing critical hardware drivers:

- ❌ No WiFi
- ❌ No touchscreen
- ❌ No touchpad

The laptop wasn’t broken — Windows had installed without the proper drivers, making the hardware completely non-functional.

-----

## Root Cause

Windows setup did not automatically install the correct drivers for the hardware. This is common with newer laptops where Windows doesn’t include the latest drivers out of the box and relies on Windows Update or manual installation to complete the setup.

Without WiFi there was no way to run Windows Update, creating a catch-22 — the laptop needed internet to get drivers, but needed drivers to get internet.

-----

## Troubleshooting Process

### Step 1 — Identify the wireless hardware

HP’s driver page wasn’t showing the correct drivers so we went directly to the hardware manufacturer instead.

Identified the wireless card as:

- **Intel Wi-Fi 6E AX211**

### Step 2 — Download the driver on a working machine

Since the HP laptop had no internet access, downloaded the official Intel WiFi driver on a Mac:

- **Driver:** Intel WiFi Driver for Windows 11
- **File:** `WiFi-24.30.1-Driver64-Win10-Win11.exe`
- **Source:** Intel’s official website (not HP)

### Step 3 — Transfer via USB (the workaround)

Since the broken laptop couldn’t reach the internet:

1. Copied the driver file onto a USB flash drive from the Mac
1. Plugged the USB into the HP laptop
1. Navigated to the USB drive in File Explorer
1. Ran the Intel WiFi driver installer manually

**Result:** After restarting, WiFi started working ✅

### Step 4 — Connect to WiFi and run Windows Update

With WiFi restored:

1. Connected to WiFi network
1. Opened Settings → Windows Update
1. Checked for updates — a large number of updates were waiting
1. Installed all available updates

**Why this worked:** HP laptops often depend on Windows Update to automatically push the remaining hardware drivers including touchscreen, touchpad, Bluetooth, chipset, and firmware updates.

### Step 5 — Verify remaining hardware

After updates and restart:

- ✅ WiFi working
- ✅ Touchscreen working
- ✅ Touchpad working
- ✅ All remaining drivers installed automatically

-----

## Key Lesson

The laptop wasn’t broken. It was a classic case of **Windows installed without proper hardware drivers**, which is common on newer laptops. The fix was:

1. Identify the specific hardware component
1. Source the driver directly from the hardware manufacturer (Intel) instead of the OEM (HP)
1. Transfer via USB to bypass the no-internet limitation
1. Let Windows Update handle the rest once internet was restored

-----

## Troubleshooting Flow

```
No WiFi → Identify wireless card model → Download driver externally
→ Transfer via USB → Install manually → WiFi restored
→ Run Windows Update → All remaining drivers installed automatically
```

-----

## Skills Demonstrated

- Hardware identification
- Driver sourcing from manufacturer vs OEM
- USB transfer workaround for offline machines
- Windows Update for driver deployment
- Systematic troubleshooting — isolate, fix, verify

-----

## Notes

- Always check the hardware manufacturer’s website (Intel, AMD, Realtek) directly when OEM driver pages are unhelpful
- A USB drive is an essential tool for IT work — being able to transfer files to an offline machine is a fundamental skill
- Windows Update handles most driver installs automatically once internet is restored — don’t always need to manually hunt every driver