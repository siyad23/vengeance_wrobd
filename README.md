# Vengeance WRO BD – Future Engineers 2025

Resources, designs, and documentation for the Vengeance team's participation in the World Robot Olympiad (WRO) 2025 Future Engineers (Self‑Driving Cars) category (Bangladesh regional).

> This repository is a work in progress. Many sections are intentionally left as TODO until code, CAD, and documentation are finalized.

---

## Table of Contents

- [Competition Context](#competition-context)
- [Goals & Strategy Overview](#goals--strategy-overview)
- [Repository Structure](#repository-structure)
- [Mechanical Design](#mechanical-design)
- [Electronics & Hardware](#electronics--hardware)
- [Software & Autonomy Stack](#software--autonomy-stack)
- [Datasets & Simulation](#datasets--simulation)
- [Build & Setup](#build--setup)
- [Development Workflow](#development-workflow)
- [Testing & Evaluation](#testing--evaluation)
- [Rules & Compliance](#rules--compliance)
- [Roadmap](#roadmap)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgements](#acknowledgements)

---

## Competition Context

The WRO Future Engineers category challenges teams to create an autonomous, camera-centric robotic vehicle that can navigate a standardized playfield using perception, planning, and control algorithms.  
Key focuses for 2025 include:

- Robust lane detection and path following
- Obstacle avoidance
- Efficient and reliable localization
- Consistency across variable lighting / surface conditions

Official documents included here (PDF/HTML) are provided for reference only. Always verify with the latest rule updates from official WRO sources.

---

## Goals & Strategy Overview

High-level objectives:

1. Reliable baseline autonomy (lane following + stop/turn handling).
2. Modular perception pipeline (camera calibration, color & feature detection).
3. Real-time control loop with smooth actuation and fail-safes.
4. Incremental performance metrics (lap time, deviation, recovery success).
5. Documented design for repeatability and judging transparency.

Strategic pillars:

- Simulate early, iterate quickly.
- Maintain clean abstractions (Perception | Planning | Control).
- Track empirical improvements with versioned test logs.
- Prioritize robustness > premature optimization.

---

## Repository Structure

(Current + Planned)

```
.
├── LICENSE
├── README.md
├── Regional_Rulebook_FE_WROBd_2025.html
├── WRO-2025-Future-Engineers-Self-Driving-Cars-General-Rules.pdf
├── WRO-2025_FutureEngineers_Playfield.pdf
├── mechanicalDesign/          # CAD, STL, assembly notes (to be populated)
├── firmware/                  # Microcontroller code (planned)
├── software/                  # High-level autonomy (vision, planning)
│   ├── perception/
│   ├── control/
│   ├── planning/
│   └── utils/
├── datasets/                  # Collected images / annotations (if allowed)
├── simulation/                # Config for simulators (Gazebo / Webots / custom)
├── calibration/               # Camera / sensor calibration data
├── docs/                      # Generated or extended documentation
└── tests/                     # Automated test cases & logs
```

Sections not yet present will be added as components are developed.

---

## Mechanical Design

Location: `mechanicalDesign/`

Planned contents:

- Chassis CAD (parametric source + exported STL/STEP)
- Exploded assembly diagrams
- Bill of Materials (BOM) with sourcing links
- Mounting guidelines (camera height, angle)
- Weight distribution notes & revision history

Design principles:

- Maintain stable CoG aligned with drive axis.
- Minimize vibration at camera mount.
- Allow rapid battery replacement without disassembly.

Status: TODO – Upload initial CAD and BOM.

---

## Electronics & Hardware

(TODO – populate specifics)

Planned documentation:

- Microcontroller / SBC selection rationale
- Motor driver specs & wiring diagram
- Power system (battery chemistry, regulators, safety)
- Sensor stack (camera model, optional IMU / encoders)
- Pinout tables
- EMI / cable management guidelines

---

## Software & Autonomy Stack

### Architecture (planned)

```
Camera → Perception → World Model → Planning → Trajectory → Control → Actuators
```

### Modules (planned)

- Perception: Color/lane segmentation, line & marker detection, optional object classification
- Localization: (Optional) dead reckoning + lane-relative positioning
- Planning: Finite state machine for maneuver logic
- Control: PID (or hybrid) for steering + speed regulation
- Diagnostics: Telemetry logging, watchdog resets

### Language & Framework Choices

(TBD – likely Python/C++ hybrid or MCU firmware + Python host; update once finalized.)

---

## Datasets & Simulation

Planned:

- Curated image sets under varied lighting
- Augmentation scripts
- Synthetic lane asset generation
- Simulation environment mirroring official playfield geometry

Note: Ensure compliance with privacy and licensing before adding external data.

---

## Build & Setup

To be added once codebase is committed.

Expected sections:

1. Prerequisites (Python version, compiler toolchains, dependencies)
2. Environment setup (virtualenv / venv / conda)
3. Firmware flashing steps
4. Calibration procedures (camera intrinsics, lens distortion)
5. Running a demo (sample command)

Example placeholder:

```
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
python software/perception/demo_lane_detect.py --input sample_frame.jpg
```

---

## Development Workflow

- Branch naming: `feature/<area>-<short-desc>` (e.g., `feature/perception-threshold-tuning`)
- Commit style: Conventional short imperative messages
- Pull request checklist (planned):
  - [ ] Updated docs
  - [ ] Added/updated tests
  - [ ] Passes lint & format
  - [ ] Performance regression checked (if applicable)

Continuous Integration: (TODO – add status once pipeline configured)

---

## Testing & Evaluation

Planned metrics:

- Lane deviation (cm RMS)
- Lap completion rate (%)
- Obstacle avoidance success rate
- Frame latency (ms) per pipeline stage

Test categories:

- Unit tests (math utilities, controllers)
- Integration (full perception-to-control loop)
- Hardware-in-the-loop (HIL) scenarios
- Field test logs (with version tagging)

---

## Rules & Compliance

Embedded documents:

- `WRO-2025-Future-Engineers-Self-Driving-Cars-General-Rules.pdf`
- `WRO-2025_FutureEngineers_Playfield.pdf`
- `Regional_Rulebook_FE_WROBd_2025.html`

Always confirm with the latest official publications. If discrepancies are found:

1. Record issue in tracker
2. Annotate affected design/logic
3. Plan compliance update

---

## Roadmap

| Phase | Focus                             | Status      |
| ----- | --------------------------------- | ----------- |
| 1     | Repo scaffolding & docs           | In progress |
| 2     | Mechanical CAD v1                 | TODO        |
| 3     | Baseline firmware & motor control | TODO        |
| 4     | Perception MVP (lane detection)   | TODO        |
| 5     | Closed-loop control tuning        | TODO        |
| 6     | Simulation & synthetic data       | TODO        |
| 7     | Obstacle avoidance logic          | TODO        |
| 8     | Performance optimization & polish | TODO        |

---

## Contributing

Contributions (internal or external) are welcome as the project opens up.

Suggested steps:

1. Open an issue describing change / enhancement
2. Draft design notes if architectural
3. Submit PR referencing issue
4. Request review from maintainers

Coding standards & lint configs will be added soon.

---

## License

See [LICENSE](LICENSE) for details.  
(Ensure any third-party assets or datasets added are compatible with this license.)

---

## Acknowledgements

- WRO organizers and community
- Open-source robotics ecosystem (to be enumerated as dependencies are added)
- Team mentors, collaborators, and regional coordinators

---

## Status Badge Placeholder

(Add CI and coverage badges here once pipelines are configured.)

---

## Contact

Add a maintainer contact or discussion channel once finalized.  
Example placeholder: `team-email@example.com`

---

### Next Steps

Populate mechanicalDesign/, add initial firmware/software skeleton, and begin documenting calibration + test methodology.

---

> If you are viewing this early and something is missing or unclear, feel free to open an issue with suggestions.
