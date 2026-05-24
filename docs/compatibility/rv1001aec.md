# RV1001AEC (Shark IQ) — Compatibility Matrix

---

## Actions

| Feature | REST | MQTT | Supported mappings |
|---------|:----:|:----:|--------------------|
| Start cleaning | ❌ | ❌ | |
| Stop | ❌ | ❌ | |
| Return to dock | ❌ | ❌ | |
| Explore / Map | ❌ | ❌ | |
| Get status | ❌ | ❌ | |
| Get event log | ❌ | ❌ | |
| Get robot ID | ❌ | ❌ | |
| Get Wi-Fi status | ❌ | ❌ | |

---

## Status Fields

| Field | REST | MQTT | Supported mappings |
|-------|:----:|:----:|--------------------|
| Operating mode | ❌ | ❌ | |
| Battery level | ❌ | ❌ | |
| Charging status | ❌ | ❌ | |

---

## Operating Modes

| Mode | REST | MQTT | Supported mappings |
|------|:----:|:----:|--------------------|
| `cleaning` | ❌ | ❌ | |
| `returning_to_dock` | ❌ | ❌ | |
| `docking` | ❌ | ❌ | |
| `docked` | ❌ | ❌ | |
| `idle` | ❌ | ❌ | |
| `exploring` | ❌ | ❌ | |

---

## Known Issues / Notes
- **Local Control Disabled:** Tested both Port 443 (HTTPS) and Port 80 (HTTP) for REST, and Port 1883 for MQTT. All connections were refused or failed to respond. This specific unit/firmware version appears to have all local communication ports locked down, restricting it to cloud-only control.
