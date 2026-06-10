# Munsit — AI-Enabled In-Ear Acoustics for Early Osteoporosis Screening

Graduation Project (GP2), Umm Al-Qura University — AI Engineering.
**Feasibility study, not clinical validation.** Munsit does not measure bone
density directly; it measures the mechanical–acoustic response of the
bone–mandible system, which carries bone-state information.

## Team & approaches
The system investigates four acoustic protocols on the OpenEarable v2 platform.

| Approach | Protocol | Stimulus / signal |
|----------|----------|-------------------|
| A1 — FDM        | 14 simultaneous upward chirps (16–20 kHz), passive bone-modified response | `approach_a1_fdm/` |
| A2 — FMCW       | Single 0.5 ms FMCW chirp + 5 ms listening window | `approach_a2_fmcw/` |
| B — Mastication | Surface acoustic waves from controlled teeth-clenching | `approach_b_mastication/` |
| C — Humming     | Closed-mouth "Emm" hum, bone-to-air transfer function | `approach_c_humming/` |


## Data availability & ethics
This project uses DXA-confirmed data and in-ear recordings from human
participants. Raw data is **not** publicly distributed.




