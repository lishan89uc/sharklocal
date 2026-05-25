# RV2610BFCA — Compatibility Matrix

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

- **REST API:** Port 443 is closed/refused. Port 80 is open, but `/get/status` and `/get/wifi_status` return `404 Not Found`, and `/` returns a forbidden HTML page.
- **MQTT:** Uses standard `sharkiq_v1` protobuf format. Status requests, passive monitoring, and basic commands work.
- **Observed MQTT status:** `mode=docked`, `battery_level=100`, `charging=true`.
- **Command test:** `start_cleaning` returned `True` and status changed to `cleaning` within about 2 seconds. `stop` returned `True` and status changed to `returning_to_dock` within about 2 seconds. `go_home` returned `True`; the robot reported `docked` about 28 seconds after the first return-to-dock command.
- **Command caveat:** In the current `sharkiq_v1` MQTT mapping, `stop` and `go_home` use the same payload, so both appear to initiate return-to-dock behavior on this model.
