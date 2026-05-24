# Lenovo Legion – Secure Boot / Boot Failure Troubleshooting

**Device:** Lenovo Legion Y7000P-1060  
**OS:** Windows 10/11  
**Issue:** `Default Boot Device Missing or Boot Failed` / `Windows Boot Manager has been blocked by the current security policy`

-----

## Symptoms

- Laptop displays **“Default Boot Device Missing or Boot Failed”** on startup
- After navigating Boot Manager, displays **“Windows Boot Manager has been blocked by the current security policy”**
- Often triggered by having an **HDMI or external device plugged in** at boot

-----

## Root Cause

The BIOS Secure Boot setting conflicts with the Windows Boot Manager entry, preventing the system from loading. This can be triggered by external devices (HDMI, USB) interfering with boot order or a BIOS/Windows update toggling Secure Boot unexpectedly.

-----

## Fix

### Step 1 – Remove External Devices

Unplug any HDMI cables, USB drives, or other peripherals before booting.

### Step 2 – Enter BIOS Setup

Power off the laptop (hold power button ~5 seconds), then power back on and immediately spam **F1** to enter the BIOS Setup Utility.

> **Note:** F2 may not work on this model. Use **F1**.

### Step 3 – Disable Secure Boot

1. Use the **left/right arrow keys** to navigate to the **Security** tab
1. Scroll down to **Secure Boot**
1. Use **F5/F6** to change the value to **Disabled**

### Step 4 – Save and Exit

Press **F10** → select **Yes** to save changes and reboot.

### Step 5 – Verify Boot

The system should now boot normally into Windows.

-----

## Quick Reference

|Key           |Action                         |
|--------------|-------------------------------|
|F1            |Enter BIOS Setup (spam on boot)|
|← → Arrow Keys|Navigate BIOS tabs             |
|F5 / F6       |Change values in BIOS          |
|F10           |Save and Exit BIOS             |

-----

## Prevention

- Always **unplug HDMI and USB devices** before shutting down or rebooting
- If Secure Boot must stay enabled, ensure Windows Boot Manager is listed as a trusted entry in the BIOS Security tab
- Set your **internal SSD as the first boot priority** under the Boot tab to prevent external devices from interfering

-----

## System Info (Reference)

|Field    |Value                            |
|---------|---------------------------------|
|Product  |Lenovo Legion Y7000P-1060        |
|CPU      |Intel Core i7-8750H @ 2.20GHz    |
|RAM      |16 GB                            |
|Storage 1|Intel SSD SSDPEKKW256G8L (NVMe)  |
|Storage 2|ST1000LM049-2GH172 (HDD)         |
|BIOS     |InsydeH20 Setup Utility v9VCN15WW|

-----

*Documented from live troubleshooting session — May 2026*