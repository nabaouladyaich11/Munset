# Approach C — Closed-Mouth Humming (mine)

Bone-to-air transfer function from a closed-mouth "Emm" hum.

- `feature_extraction/` — ingest → align → segment → transfer function → 2 band features per sensor
- `analysis/` — LOSO + permutation test, classifier robustness, cross-approach comparison
- `notebooks/` — exploratory Colab notebooks

Primary: logistic regression on `avg_low_dB`, `avg_high_dB` (per sensor), LOSO, no oversampling.
