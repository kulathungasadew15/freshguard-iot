# FreshGuard

## IoT-Based Smart Fruit Bowl

FreshGuard is an ESP32 project that monitors the environment around stored fruit and aims to give early warnings when conditions need attention. The proposed system combines temperature, humidity, gas-trend and weight sensing with automatic ventilation, local alerts, MicroSD logging and a Wi-Fi dashboard.

**Group 13 · SLIIT · Year 1, Semester 1 · IT1140 Fundamentals of Computing**

**Status:** Prototype in development. This repository currently contains project documentation and images from the progress report. Firmware, dashboard source code and editable simulation files have not yet been added.


*Proposed enclosure concept from the September 10, 2026 progress report. Enclosure construction is listed as a next step in that report.*

## Project goals

- Monitor temperature and humidity using a DHT22.
- Observe changes in gas/VOC readings using an MQ-135.
- Track fruit weight using a load cell and HX711.
- Classify sustained sensor changes as Fresh, Attention or Possible Spoilage.
- Operate a ventilation fan and servo-controlled cover when conditions require attention.
- Show local status through an RGB LED and buzzer.
- Save readings to MicroSD and display live information on a Wi-Fi dashboard.

FreshGuard monitors storage conditions. It does not scientifically determine whether fruit is safe to eat, and MQ-135 readings are intended as relative gas trends rather than exact gas identification or spoilage measurements.

## Planned operation

The ESP32 reads the sensors at regular intervals, filters invalid or noisy readings, and compares sustained changes against selected thresholds. It then updates the system status, controls the outputs, records readings and events, and refreshes the dashboard. Calibration and complete-system testing are part of the development plan.

## Hardware

| Component | Intended purpose |
| --- | --- |
| ESP32 DevKit V1 | Main controller and Wi-Fi communication |
| DHT22 | Temperature and humidity measurements |
| MQ-135 | Relative gas/VOC trend monitoring |
| 5 kg load cell and HX711 | Weight measurements |
| 5V DC fan and MOSFET switching stage | Ventilation |
| SG90 servo | Automatic cover movement |
| RGB LED and buzzer | Local status and warning outputs |
| MicroSD module and card | Reading and event storage |
| 5V supply, breadboard and jumper wires | Prototype power and connections |

The proposal separates the fruit-storage area from the electronics base and uses a MOSFET stage to switch the fan.

## Reported progress

The following status reflects the [progress report](docs/progress-report.pdf), submitted on **September 10, 2026**. It summarizes the team's reported work rather than independent verification.

| Area | Status in the report |
| --- | --- |
| RGB LED, DHT22, MQ-135 and HX711 | Individual hardware tests and Serial Monitor output documented |
| Buzzer, servo and fan | Individual actuation tests documented |
| MicroSD | Module communication and initialization reported; complete logging evaluation remains part of the planned work |
| Wokwi | Proposed wiring documented; repeated server-busy errors prevented simulation verification |
| Physical enclosure and complete integration | Listed as next steps |
| Wi-Fi dashboard | Finalization listed as a next step |

## Documentation

| File | Contents |
| --- | --- |
| [Project proposal](docs/project-proposal.docx) | Problem, objectives, hardware, methodology and evaluation plan |
| [Proposal presentation](docs/proposal-presentation.pptx) | Project overview, planned architecture and milestones |
| [Progress report](docs/progress-report.pdf) | Architecture, work breakdown, component-test evidence and next steps |

These three documents retain the contents of the supplied originals. Their filenames have been shortened for this repository.

## Simulation

[Wokwi project referenced in the report](https://wokwi.com/projects/474755060504718337)

![Proposed Wokwi circuit shown in the progress report](docs/images/wokwi-circuit.png)

*Circuit screenshot from the progress report. The report explicitly states that simulation testing remains pending.*

See [simulation notes](simulation/README.md) for the files still needed to reproduce the simulation locally.

## Source code

The reports include screenshots of component-test sketches, but this repository does not yet include the original `.ino`, `.cpp` or `.h` files. There is currently no complete firmware build or dashboard to run from this repository.

Add the actual Arduino project under `firmware/` and document its board selection, library versions, wiring and calibration before marking it ready to build. See [firmware notes](firmware/README.md).

## Team

| Member | Role |
| --- | --- |
| KULATHUNGA M.A.S.S. | Team leader |
| VINOJA H.W.O. | Team member |
| SUBHASHANA T.O. | Team member |
| PERERA M.K.J.C. | Team member |
| SITHUMINI W.T.I. | Team member |
| DAMAYANTHA H.A.E. | Team member |

## Next milestones

- Add the original firmware and simulation project files.
- Construct the enclosure and integrate the tested components.
- Complete the dashboard and MicroSD logging.
- Calibrate the sensors and tune sustained-reading thresholds.
- Run complete-system tests and record the results.
