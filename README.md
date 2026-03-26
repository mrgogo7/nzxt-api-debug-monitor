# NZXT API Debug Live Monitor

A live debug monitor built for the NZXT Web Integration API.

---

## Overview

This tool is designed to inspect and analyze real-time data coming from the NZXT API.

It provides a clear and structured view of the monitoring payload while also exposing the raw data, making it easier to debug, validate, and understand what the API actually returns on different hardware setups.

---

## Important

⚠️ This tool only works when opened through **NZXT CAM Web Integration**.

Opening it directly in a browser **will not provide any data**, because the NZXT API is not available outside of CAM.

---

## Features

- 🔴 **Live Data Monitoring**  
  Updates instantly when NZXT API data is received

- 🧩 **Structured Sensor View**  
  CPU, GPU, RAM, and Kraken data in a clean layout

- 🧬 **Flattened Raw Field Explorer**  
  Full payload inspection with path-based field mapping

- 🧠 **Observed Schema Tracking**  
  Builds a live union of all detected fields and types

- 📋 **Copy Tools**  
  Easily copy:
  - Raw JSON
  - Flattened fields
  - Schema map

- 🖥️ **Kraken LCD Mode**  
  `?kraken=1` renders a circular LCD-style interface

- 🔄 **Real-Time Control Sync**  
  Page control via localStorage (Prev / Next / Auto)

---

## How to Use

### ✅ Correct Usage (NZXT CAM)

1. Open **NZXT CAM**
2. Go to **Web Integration**
3. Add or open the following URL:

https://nzxt-esc.pages.dev/debug/ or https://mrgogo7.github.io/nzxt-api-debug-monitor

---

### ⚠️ Browser Usage

Opening this page directly in a browser will result in:

- No sensor data
- No payload updates
- Empty or "waiting" state

This is expected behavior.

---

## How It Works

The page listens to:

```js
window.nzxt.v1.onMonitoringDataUpdate
```

When data is received:

Payload is safely cloned
UI is updated in real time
Data is flattened into path-based rows
A schema map is dynamically built

No mock or fallback data is used — everything shown reflects real NZXT API output.

Notes
Data depends on:
Your hardware (CPU, GPU, AIO, etc.)
NZXT CAM / API version
Current runtime state
Different devices may expose different fields
Use Cases
Debugging NZXT Web Integration
Inspecting real API payloads
Reverse engineering field structure
Building custom LCD overlays
Testing multi-device compatibility
Contributing

Part of the NZXT-ESC ecosystem.

If you discover new fields, edge cases, or device-specific behaviors, feel free to share them.

License

Personal Use License
© 2025 Gökhan Akgül (mRGogo)

Author

Developed by mRGogo
Part of the NZXT-ESC project
