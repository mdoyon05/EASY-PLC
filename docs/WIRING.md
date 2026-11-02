# 🔌 ESP32 16-Channel PLC — Wiring Documentation

## 1. Project Overview

This project uses an ESP32 development board as the main controller for a 16-channel relay-based industrial automation system.

The controller provides 16 digital outputs that can be used to control relays, contactors, solenoid valves, lamps, motors, pumps, and other suitable loads.

```text
                ESP32 PLC Controller
                         │
        ┌────────────────┼────────────────┐
        │                │                │
      Q0-Q5            Q6-Q11           Q12-Q15
        │                │                │
        ▼                ▼                ▼
   Relay Module 1   Relay Module 2   Relay Module 3
        │                │                │
        └────────────────┼────────────────┘
                         │
                    Field Outputs
```

---

## 2. Controller

### Main Controller

- ESP32 Development Board
- 3.3 V GPIO logic
- Wi-Fi enabled
- Arduino framework

The ESP32 is responsible for:

- Reading digital inputs
- Executing control logic
- Controlling relay outputs
- Providing web-based monitoring/control
- Future PLC communication

---

# 3. Digital Output Mapping

The current software configuration uses the following proposed GPIO mapping.

| PLC Address | ESP32 GPIO | Output |
|---|---:|---|
| Q0 | GPIO 4 | Relay 1 |
| Q1 | GPIO 5 | Relay 2 |
| Q2 | GPIO 13 | Relay 3 |
| Q3 | GPIO 14 | Relay 4 |
| Q4 | GPIO 16 | Relay 5 |
| Q5 | GPIO 17 | Relay 6 |
| Q6 | GPIO 18 | Relay 7 |
| Q7 | GPIO 19 | Relay 8 |
| Q8 | GPIO 21 | Relay 9 |
| Q9 | GPIO 22 | Relay 10 |
| Q10 | GPIO 23 | Relay 11 |
| Q11 | GPIO 25 | Relay 12 |
| Q12 | GPIO 26 | Relay 13 |
| Q13 | GPIO 27 | Relay 14 |
| Q14 | GPIO 32 | Relay 15 |
| Q15 | GPIO 33 | Relay 16 |

> ⚠️ This GPIO table is a software default. Verify the actual PCB traces and relay input connections before using the controller with field equipment.

---

# 4. Relay Connection

The basic connection is:

```text
ESP32 GPIO
    │
    ▼
Relay Input
    │
    ▼
Relay Coil
    │
    ▼
Relay Contact
