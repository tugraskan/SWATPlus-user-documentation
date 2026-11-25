---
description: Fraction burned
---

# frac\_burn

**Code reference:** `fire_db(ifireop)%fr_burn` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L43), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_read_fireops.f90#L45)).

Dimensionless fraction (`fraction`; default `0.0`, valid range `0.0–1.0`) of above-ground biomass, surface plant residue, and surface soil organic matter consumed by burning (for example, `1.0` represents complete burning and `0.5` represents half; do not enter a percentage).

In [`pl_burnop.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/pl_burnop.f90#L50-L66), SWAT+ computes burned mass as $f_{\text{burn}} \cdot M$ and scales the remaining plant residue (`rsd`, `rsd_tot`), above-ground plant biomass (`ab_gr`, `stem`, `leaf`, `seed`), and layer-1 slow and passive soil humus (`hs(1)`, `hp(1)`) by $(1 - f_{\text{burn}})$.
