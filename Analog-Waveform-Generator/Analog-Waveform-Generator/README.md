# Analog Waveform Generator

An analog waveform generator project designed to produce **square, triangle, and sine waveforms** using op-amp-based circuit stages. This repository tracks circuit simulation, PCB development, and hardware testing.

## Overview

The design uses an op-amp oscillator to generate a square wave, an integrator stage to produce a triangle wave, and a subsequent waveform-shaping stage for a sine-like output. The circuit has been developed and tested with a split **+5 V / −5 V** supply.

> **Project status:** In development. The supplied Multisim design is included; KiCad files and measured results can be added as they become available. Component values and performance should be checked against the latest design revision.

## Repository layout

```text
Analog-Waveform-Generator/
├── simulation/
│   └── multisim/
│       └── waveformgeneratorv2.ms14
├── hardware/
│   ├── kicad/             # .kicad_pro, .kicad_sch, .kicad_pcb and libraries
│   └── exports/           # Gerbers, drill files, PDFs, BOM exports
├── docs/
│   └── images/            # Schematics, scope captures, PCB renders
├── measurements/          # Lab notes and recorded test data
├── assets/                # Additional project resources
├── .gitignore
└── README.md
```

## Tools

- **NI Multisim:** Circuit simulation
- **KiCad:** Schematic capture and PCB layout
- **Bench equipment:** DC power supply, oscilloscope, and multimeter

## Circuit operation

1. **Square-wave oscillator:** An op-amp switching stage with feedback generates a repeating high/low waveform.
2. **Triangle-wave stage:** An op-amp integrator converts the square-wave input into approximately linear rising and falling ramps.
3. **Sine-wave stage:** Further waveform shaping reduces harmonic content to approximate a sine wave.

## Power

The design uses **+5 V, ground, and −5 V** rails. When generating these from two bench-supply channels in series, verify the outputs support series operation and confirm the rail voltages relative to the shared midpoint before connecting the circuit.

## Getting started

1. Open `simulation/multisim/waveformgeneratorv2.ms14` in a compatible version of NI Multisim.
2. Add KiCad files to `hardware/kicad/` when ready.
3. Store circuit screenshots and oscilloscope captures in `docs/images/`.
4. Add hardware measurements and observations to `measurements/`.

## Next steps

- [ ] Add KiCad project and PCB layout
- [ ] Document final component values and operating frequency
- [ ] Add simulation screenshots for each output waveform
- [ ] Add oscilloscope captures and measured performance
- [ ] Export PCB manufacturing files when the design is ready

## Notes

This repository is a project workspace, not a claim that the hardware or PCB design has been finalized.
