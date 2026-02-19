Good. This is your **portable hardware audit command** — one line, full snapshot, reusable on any Mac.

Copy and run this:

```bash
echo "===== HARDWARE =====" && system_profiler SPHardwareDataType && echo "\n===== GPU =====" && system_profiler SPDisplaysDataType && echo "\n===== MEMORY =====" && system_profiler SPMemoryDataType && echo "\n===== STORAGE =====" && system_profiler SPStorageDataType && echo "\n===== DISKS =====" && diskutil list && echo "\n===== THUNDERBOLT =====" && system_profiler SPThunderboltDataType && echo "\n===== T2 / IBRIDGE =====" && system_profiler SPiBridgeDataType
```

---

## What This Captures

* CPU model + cores
* RAM configuration
* GPU model + VRAM
* SSD size + partitions
* Thunderbolt ports (eGPU capability)
* T2 security chip presence

---

## Optional: Add Live Thermal Snapshot (Admin Required)

If you want performance insight too, use this extended version:

```bash
echo "===== HARDWARE =====" && system_profiler SPHardwareDataType && echo "\n===== GPU =====" && system_profiler SPDisplaysDataType && echo "\n===== MEMORY =====" && system_profiler SPMemoryDataType && echo "\n===== STORAGE =====" && system_profiler SPStorageDataType && echo "\n===== DISKS =====" && diskutil list && echo "\n===== THUNDERBOLT =====" && system_profiler SPThunderboltDataType && echo "\n===== T2 / IBRIDGE =====" && system_profiler SPiBridgeDataType && echo "\n===== THERMALS =====" && sudo powermetrics --samplers smc | grep -i "CPU die temperature"
```

(Will prompt for password.)

---

You can now audit **any Mac in under 60 seconds** and know immediately:

* Is it workstation grade?
* Is it virtualization safe?
* Is it eGPU capable?
* Is it resale-worthy?

When you paste results, I’ll interpret them architect-level.
