# RV2310CGUS (Shark Matrix) — Compatibility Matrix

---

## Actions

| Feature | REST | MQTT | Supported mappings |
|---------|:----:|:----:|--------------------|
| Start cleaning | ❌ | ✅ | MQTT: `sharkiq_v1` |
| Stop | ❌ | ✅ | MQTT: `sharkiq_v1` |
| Return to dock | ❌ | ✅ | MQTT: `sharkiq_v1` |
| Explore / Map | ❌ | ❌ | |
| Get status | ❌ | ✅ | MQTT: `sharkiq_v1` |
| Get event log | ❌ | ❌ | |
| Get robot ID | ❌ | ❌ | |
| Get Wi-Fi status | ❌ | ❌ | |

---

## Status Fields

| Field | REST | MQTT | Supported mappings |
|-------|:----:|:----:|--------------------|
| Operating mode | ❌ | ✅ | MQTT: `sharkiq_v1` |
| Battery level | ❌ | ✅ | MQTT: `sharkiq_v1` |
| Charging status | ❌ | ✅ | MQTT: `sharkiq_v1` |

---

## Operating Modes

| Mode | REST | MQTT | Supported mappings |
|------|:----:|:----:|--------------------|
| `cleaning` | ❌ | ✅ | MQTT: `sharkiq_v1` |
| `returning_to_dock` | ❌ | ✅ | MQTT: `sharkiq_v1` |
| `docking` | ❌ | ✅ | MQTT: `sharkiq_v1` |
| `docked` | ❌ | ✅ | MQTT: `sharkiq_v1` |
| `idle` | ❌ | ❌ | |
| `exploring` | ❌ | ❌ | |

---

## Known Issues / Notes
- **REST API:** Tested both Port 443 (HTTPS) and Port 80 (HTTP). Port 443 is closed/refused; Port 80 is open but does not respond to standard API endpoints. Local web API appears disabled on this firmware.
- **MQTT:** Uses standard `sharkiq_v1` protobuf format. Successfully decodes Battery (Field 9.8) and Charging State (Field 9.1).
