# Bifilar Coil Array Specifications – IX-Singularis  
*Tesla Resonant Driver System for Harmonic Beam Generation and Stabilization*

---

## 🌀 Overview

This subsystem specifies the **Tesla-style bifilar coil array** responsible for driving:
- Longitudinal harmonic waveforms
- Resonance-matched pulse shaping
- Zero-phase-field beam outputs aligned with 3-6-9 structuring

Each coil feeds directly into its assigned **meta-mirror beam path**, synchronized via the TunerCore harmonic engine.

---

## 🧭 Coil Geometry (Per Node)

| Parameter | Value |
|-----------|-------|
| Wire Type | Oxygen-free copper, 99.99% purity |
| Coil Type | Tesla flat bifilar spiral (double-wound, parallel) |
| Outer Diameter | 7.2 cm |
| Turns per Layer | 18 (×2 bifilar) |
| Layers | 4 |
| Capacitance (inter-coil) | ~19.8 pF |
| Inductance (simulated) | ~148.2 µH |
| Self-resonant Frequency | 2.15 MHz ± 5% (tunable via TunerCore) |

---

## ⚡ Array Configuration

- Total Coil Units: 6 (minimum), expandable to 36 (modular ring)
- Configuration: Toroidal ring + axial spoke array
- Field Shape: Collimated longitudinal harmonic burst
- Driving Signal: Symmetric dual-phase Tesla pulse train
- Envelope Modulation: Controlled by `/control/field-feedback-telemetry.md`

---

## 🔧 Mounting + Isolation

| Feature | Spec |
|--------|------|
| Mount Plate | PEEK or Delrin (non-magnetic, cryo-safe) |
| Vibration Isolation | Piezo-damped standoff rods |
| Cooling Method | Passive + CryoCore-assisted |
| Magnetic Shielding | Mu-metal inner dome surrounding each coil node |

---

## 🔄 Signal Modulation Capabilities

- Phase inversion: Hardware-assisted via twin gate capacitors
- Burst spacing: Configurable 2.5–15 μs via TunerCore
- Pulse shape: Gaussian-like with square-tail suppression
- Frequency sweeping: Optional harmonic sweep mode for dynamic load tuning

---

## 🛠️ Manufacturing Notes

- Wire tension must remain uniform — no stretch deviations >0.2%
- PCB backplane (if used) must be gold-plated, low-inductance
- Spacing between bifilar pairs: ≤ 1.1 mm

---

## 🧠 System Integration

Direct control and modulation from:
- `/control/field-feedback-telemetry.md`
- `/simulation/element115-harmonic-model.sim`

Coil behavior must remain phase-locked during any:
- Beam divergence correction
- Containment spike
- CryoCore feedback loop event

---

## 🧯 Fail-Safes

| Trigger | Response |
|--------|----------|
| Overcurrent (>1.2 A RMS) | Pulse shutoff and coil decoupling |
| Phase drift >4° | Auto-resync pulse + feedback alert |
| Magnetic surge detected | Coil clamp circuit activates, dumps field to ground rail |

---

## 🔖 Licensing

This Tesla-style coil array design may not be used to develop energy weapons, directed-energy propulsion systems, or battlefield energy delivery tools.  
Usage is limited to contained scientific platforms under terms in `/LICENSE`.
