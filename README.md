# Munset — AI-Enabled In-Ear Acoustics for Early Osteoporosis Screening

Graduation Project (GP2), Umm Al-Qura University — AI Engineering.
**Feasibility study, not clinical validation.** Munset does not measure bone
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

## Repository layout
- `shared/pipeline/` — common ML pipeline (patient-level split, SMOTE+jitter, models, permutation test) used for cross-approach comparison.
- `approach_*/` — per-approach feature extraction and analysis.
- `results/` — generated figures and tables.
- `data/` — **see `data/README.md`. Raw cohort data is NOT in this repo.**
- `docs/` — thesis / report.

## Data availability & ethics
This project uses DXA-confirmed data and in-ear recordings from human
participants. Raw data is **not** publicly distributed.

## Reproducing the analysis (Approach C)
```bash
pip install -r requirements.txt
# place data per data/README.md, then:
# 1. feature extraction  -> approach_c_humming/feature_extraction/
# 2. primary analysis     -> approach_c_humming/analysis/  (LOSO + permutation)
# 3. cross-approach panel -> shared/pipeline/  (controlled comparison)
```

## Method notes (Approach C)
- Primary classifier: logistic regression on 2 band features (`avg_low_dB`, `avg_high_dB`) per sensor.
- Validation: leave-one-subject-out (LOSO). **No oversampling in the primary analysis.**
- Cross-approach comparison uses the shared pipeline (single split + SMOTE) and is reported **separately** from the primary LOSO result — the two use different validation schemes and are not ranked against each other.
