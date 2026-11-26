---
description: Fraction burned
---

# frac\_burn

**Code reference:** `fire_db(ifireop)%fr_burn` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L43), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_read_fireops.f90#L45)).

Dimensionless fraction (`fraction`; default `0.0`, valid range `0.0–1.0`) of above-ground biomass, surface plant residue, and surface soil organic matter consumed by burning (for example, `1.0` represents complete burning and `0.5` represents half; do not enter a percentage).

In [`pl_burnop.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_burnop.f90#L40-L73), SWAT+ dev computes burned mass as $f_{\text{burn}} \cdot M$ and scales by $(1 - f_{\text{burn}})$: layer-1 slow and passive soil humus (`hs(1)`, `hp(1)`) once per operation, and each plant's surface residue (`abg_rsd`) and above-ground biomass (`ab_gr`, `stem`, `leaf`, `seed`). The total surface residue is reduced by the amount burned. Burned carbon is counted as soil, residue or plant carbon emission, and burned phosphorus is returned to the passive humus P pool of layer 1. (SWAT+ main burned the humus once per plant and overwrote the residue total with one plant's remaining residue.)
