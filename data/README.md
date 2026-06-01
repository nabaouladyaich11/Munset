# Data — Access & Ethics

**Raw cohort data is NOT included in this repository.**

This project uses DXA-confirmed data and in-ear acoustic recordings from human
participants (osteoporosis screening). Voice/humming recordings and health
status are sensitive and potentially re-identifying, so the raw dataset is not
publicly distributed.

## Availability
De-identified data may be available from the authors on reasonable request,
subject to approval by the project supervisor and the relevant ethics committee.

## What lives here
- `sample/` — a tiny de-identified or synthetic example only, for code demonstration.

## Cohort summary (for reference, no raw data)
- n = 8 women, DXA-confirmed.
- Healthy: P01, P03, P04, P05.  Osteoporosis: P06, P07, P08, P09.
- P02 excluded (anterior dental prosthetics — pre-specified criterion).

## Feature data dictionary (Approach C)
| Column | Meaning |
|--------|---------|
| `patient_id` | Participant ID (de-identified) |
| `condition`  | healthy / osteoporosis |
| `session_id` | Session within participant |
| `avg_low_dB`  | Mean transfer, 150–500 Hz band (stiffness-dominated) |
| `avg_high_dB` | Mean transfer, 800–1500 Hz band (damping-dominated) |
| `attenuation_dB` | avg_low_dB − avg_high_dB (exploratory) |

Bone-sensor columns mirror these with a `bone_` prefix.
