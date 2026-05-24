# L293D Motor Driver PCB

A compact 2-channel DC motor driver PCB built around the L293D IC,
designed from scratch in KiCad. Controls 2 DC motors with direction
and enable inputs. Clean through-hole design with screw terminal outputs.

![3D Render](https://github.com/user-attachments/assets/c587f618-8797-4ebc-97d3-8b1bc895cd51)

## Features

- **Driver IC:** L293D — dual H-bridge motor driver
- **Channels:** 2 independent DC motor channels
- **Motor Outputs:** 4x screw terminals (2 per motor)
- **Motor Inputs:** 4x pin headers (control signals)
- **Power:** 5V VCC input via screw terminal
- **Decoupling:** 100µF capacitor on power rail
- **Mounting:** 4 corner mounting holes
- **Layers:** 2-layer PCB
- **DRC:** 0 errors, 0 warnings
- **ERC:** 0 violations
- **Unrouted:** 0

## PCB Screenshots

| Schematic | PCB Layout | 3D Front |
|---|---|---|
| ![](https://github.com/user-attachments/assets/815d9342-e7c3-4948-acb7-377d30b6bc72) | ![](https://github.com/user-attachments/assets/6bec46e3-caef-42e9-9fe8-e4788388918e) | ![](https://github.com/user-attachments/assets/c587f618-8797-4ebc-97d3-8b1bc895cd51) |

## Schematic Overview

| Block | Components |
|---|---|
| Motor Driver | L293D (DIP-16) |
| Power Input | J1 — GND + 5V screw terminal |
| Motor 1 Output | J2 — 2-pin screw terminal |
| Motor 2 Output | J3 — 2-pin screw terminal |
| Motor 1 Input | J4 — 2-pin header (1A, 2A) |
| Motor 2 Input | J5 — 2-pin header (3A, 4A) |
| Decoupling | C1 — 100µF across VCC/GND |

## L293D Pin Map

| Pin | Name | Connection |
|---|---|---|
| 1 | EN1,2 | Enable Motor 1 (HIGH = enabled) |
| 2 | 1A | Motor 1 Input A |
| 3 | 1Y | Motor 1 Output A → screw terminal |
| 4,5 | GND | GND |
| 6 | 2Y | Motor 1 Output B → screw terminal |
| 7 | 2A | Motor 1 Input B |
| 8 | VCC2 | Motor supply voltage (5V) |
| 9 | EN3,4 | Enable Motor 2 (HIGH = enabled) |
| 10 | 3A | Motor 2 Input A |
| 11 | 3Y | Motor 2 Output A → screw terminal |
| 12,13 | GND | GND |
| 14 | 4Y | Motor 2 Output B → screw terminal |
| 15 | 4A | Motor 2 Input B |
| 16 | VCC1 | Logic supply (5V) |

## How To Control Motors

```
Motor FORWARD:
  1A = HIGH, 2A = LOW, EN1,2 = HIGH

Motor REVERSE:
  1A = LOW, 2A = HIGH, EN1,2 = HIGH


```

## Design Decisions

| Decision | Reason |
|---|---|
| L293D over L298N | Smaller, simpler, sufficient for 600mA/channel |
| Screw terminals for outputs | Easy motor wire connection without soldering |
| 100µF decoupling cap | Motor switching noise suppression on VCC |
| 4 mounting holes | Secure board mounting in enclosures |
| DIP-16 package | Easy hand soldering, through-hole reliability |
| Silkscreen labels | MOTOR INPUTS / MOTOR OUTPUT clearly labeled |

## Specifications

| Parameter | Value |
|---|---|
| Supply Voltage | 5V |
| Output Current | 600mA per channel |
| Peak Current | 1.2A per channel |
| Logic Input | TTL compatible |
| Channels | 2 DC motors |
| Package | DIP-16 through-hole |

## Files

| File/Folder | Description |
|---|---|
| [L293D MOTOR DRIVER.zip](https://github.com/user-attachments/files/28192153/L293D.MOTOR.DRIVER.zip) | Production-ready Gerber files |
| https://github.com/user-attachments/assets/815d9342-e7c3-4948-acb7-377d30b6bc72 | Full KiCad schematic export |
| [MOTOR DRIVER(L293D).csv](https://github.com/user-attachments/files/28192212/MOTOR.DRIVER.L293D.csv) | Bill of materials |

## Bill of Materials

| Reference | Component | Value | Package |
|---|---|---|---|
| U1 | L293D | Motor Driver | DIP-16 |
| C1 | Capacitor | 100µF | Through-hole |
| J1 | Screw Terminal | GND + 5V | 2-pin |
| J2 | Screw Terminal | Motor 1 Output | 2-pin |
| J3 | Screw Terminal | Motor 2 Output | 2-pin |
| J4 | Pin Header | Motor 1 Input | 2-pin |
| J5 | Pin Header | Motor 2 Input | 2-pin |

## Part of #30DaysOfPCB Series

This is part of my daily PCB design challenge.
Follow along on [LinkedIn](https://www.linkedin.com/in/dharahaas-simhadri-b17b4b358?utm_source=share_via&utm_content=profile&utm_medium=member_android)

## Author

**Simhadri Dharahaas** — ECE Undergraduate | PCB Design & Embedded Systems
[LinkedIn](https://www.linkedin.com/in/dharahaas-simhadri-b17b4b358?utm_source=share_via&utm_content=profile&utm_medium=member_android) | [GitHub](https://github.com/dharahaas23)
