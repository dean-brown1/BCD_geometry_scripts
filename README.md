# BCD Calabi-Yau: Computational Verification Scripts

Companion scripts for the paper:

> **Topology of the Braun–Candelas–Davies Calabi–Yau: Intersection Ring and Enumerative Invariants**
> Dean Brown (2026). Zenodo. https://doi.org/10.5281/zenodo.18985060

These 12 self-contained Python scripts reproduce every computational
claim in the paper. Each script prints a derivation narrative to stdout
with numbered `[PASS]`/`[FAIL]` assertions and a final summary line.

## Requirements

- Python 3.10+
- NumPy
- SciPy
- mpmath (for Picard-Fuchs / high-precision arithmetic)

No virtual environment or build system is required.

## Running

Every script is standalone with no local imports:

```bash
python <scriptname>.py
```

All assertions should print `[PASS]`. A summary line at the end
reports the total, e.g. `ALL 27 ASSERTIONS PASSED.`

## Script Inventory

| Script | Assertions | Verifies |
|--------|-----------|----------|
| `compute_d111.py` | 5/5 | d₁₁₁ = 18 (two methods) |
| `derive_covering_dabc_reptheory.py` | 22/22 | Covering ring, Dic₃ reps |
| `derive_d333_HRR_unique.py` | 13/13 | d₃₃₃ = 12 (Schur + HRR, no MUM) |
| `derive_dabc_pure_geometry.py` | 9/9 | d₂₂₃ = 2 (GL(3,ℂ) multi-point) |
| `derive_dabc_discriminant_orbit.py` | 11/11 | Δ₂ exclusion of d₂₂₃ ≠ 2 |
| `derive_d1AB_from_covering.py` | 14/14 | d₁₄₄ = 6 |
| `derive_c2_covering_adjunction.py` | 10/10 | c₂ = (12, 0, 0, 0) (Schur) |
| `derive_mirror_quotient_compatibility.py` | 15/15 | C4 external theorem (6/6 hyp.) |
| `derive_BCD_picard_fuchs.py` | 20/20 | ₇F₆ periods |
| `derive_monodromy_mirror_map.py` | 27/27 | Monodromy, integral basis |
| `derive_Dic3_deformation_space.py` | 34/34 | Dic₃ action, irrep decomposition |
| `derive_BCD_vacuum_uniqueness.py` | 15/15 | σ involution, tadpole |
| **Total** | **195/195** | |

## The BCD Manifold

The Braun–Candelas–Davies (BCD) Calabi–Yau threefold X is defined as
the free quotient Y / Dic₃, where Y is a CICY embedded in (ℙ²)⁴ and
Dic₃ is the dicyclic group of order 12. The Hodge numbers are
(h¹'¹, h²'¹) = (1, 4), Euler characteristic χ = -6, and the toric
triple intersection number is d₁₁₁ = 18.

The intersection ring on the mirror has 5 nonzero entries out of 20:

| Entry | Value | Method |
|-------|-------|--------|
| d₁₁₁ | 18 | Adjunction formula |
| d₂₂₃ | 2 | GL(3,ℂ) Yukawa + discriminant orbit |
| d₂₃₃ | {6, 8}, nominal 8 | Wronskian-constrained mirror map (weakly preferred) |
| d₃₃₃ | 12 | HRR integrality + Schur's lemma |
| d₁₄₄ | 6 | Covering CICY + Dic₃ irrep projection |

## License

These scripts are provided for scientific reproducibility. If you use
them in your own work, please cite the accompanying paper:

Brown, D. (2026). Topology of the Braun–Candelas–Davies Calabi–Yau:
Intersection Ring and Enumerative Invariants. Zenodo.
https://doi.org/10.5281/zenodo.18985060
