# Durability-Test-Rig-Software
A Durability test-rig control application that automates static, dynamic, and combined endurance durability testing of hydro-pneumatic suspension components. It closes the loop between a servo-hydraulic actuator and a suite of sensors (LVDT, load cell, thermocouples) to reproduce field-representative cyclic loading .
**Key Features**
Test Bank — create, track, and archive individual test records with customer and component metadata
**Waveform / Procedure Builder**
Static tests: configurable ramp steps, step length, fine/coarse ramp speed, dwell time
Dynamic tests: sine / square / triangular / sawtooth / programmable waveforms with independently tunable amplitude, frequency, phase, duty cycle, and chainable blocks
Endurance tests: static → dynamic → static composite sequences
**Live Control Station**
Closed-loop PID control (Stroke or Load mode) driving an EP/servo valve
Real-time command-vs-feedback strip chart with pan/zoom and history scrollback
Configurable peak/valley error envelopes on both stroke and load, with automatic fault tripping
Full interlock/fault panel: overloads, limit switches, e-stop, filter chokes, oil temperature/level, single-phase protection
Manual jog / pot control for actuator positioning outside of automated tests
**Reporting**
Searchable test history by date, type, or test number
Before/after cycle comparison tables and load-vs-cycle plots
One-click export to Word, plus direct email delivery
System Architecture
Function/Waveform Generator  ──▶  Saved Test Procedure (block-based)
                                        │
                                        ▼
                              Control Station (PID loop)
                                        │
                     ┌──────────────────┼──────────────────┐
                     ▼                  ▼                  ▼
              EP/Servo Valve      LVDT (Pilot+Main)    Load Cell / TCs
              → Actuator            → Position FB        → Force/Temp FB
                     │                  │                  │
                     └──────── Data Acquisition ───────────┘
                                        │
                                        ▼
                          Logged results (cycles, stroke,
                             load, temperature, timestamp)
                                        │
                                        ▼
                            Report Generator → .docx / Email
**Tech Stack**
LabVIEW — application logic, real-time control loop, PID tuning, HMI
PCI/PXI analog I/O hardware — actuator command output, LVDT/load cell/thermocouple acquisition
SQL backend — test records and time-series result logging
MS Word (COM/report automation) — auto-generated test reports

**My Role**
Designed and developed the complete Test Application as part of a durability-testing product line for hydro-pneumatic suspension components, covering:
Real-time PID control loop design and tuning for both stroke and load control modes
Multi-signal DAQ integration (dual LVDT, load cell, 4-channel thermocouple) with hardware interlock and safety-trip logic
Waveform/function-generator engine supporting sine, square, triangular, sawtooth, and chained programmable test blocks
End-to-end software: login/security, test-case management, live monitoring dashboards, and automated report generation pushed to SQL and exported to Word

**Linkedin**
www.linkedin.com/in/sarita-bhat-b2a85b14Van
