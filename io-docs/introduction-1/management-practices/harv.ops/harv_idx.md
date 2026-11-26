---
description: Harvest index target specified at harvest
---

# harv\_idx

**Code reference:** `harvop_db(iharvop)%hi_ovr` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L113), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_read_harvops.f90#L44)).

Dimensionless override harvest index (`fraction`, `(kg/ha)/(kg/ha)`; default `0.0`, valid range `0.0–1.0`) specifying the target fraction of above-ground biomass or surface residue removed during biomass and residue harvests.

In biomass harvests (`biomass`, `tree`, `stripper`; [`mgt_harvbiomass.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_harvbiomass.f90#L38-L46), [`#L126-L127`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_harvbiomass.f90#L126-L127)), SWAT+ combines `harv_idx` with `harv_eff` to scale seed, leaf, and stem mass into yield and reduce leaf area index and accumulated heat units by $(1 - 0.5\,HI_{\text{tot}})$:

$$HI_{\text{tot}} = HI_{\text{ovr}} \cdot E_{\text{harv}}$$

where $HI_{\text{tot}}$ is the effective harvest index (dimensionless), $HI_{\text{ovr}}$ is `harv_idx` (dimensionless), and $E_{\text{harv}}$ is `harv_eff` (dimensionless).

In residue harvests (`residue`; [`mgt_harvresidue.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_harvresidue.f90#L51-L53), [`#L61-L64`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_harvresidue.f90#L61-L64)), `harv_idx` scales the residue removal fraction:

$$E_{\text{net}} = E_{\text{harv}} \cdot HI_{\text{ovr}}, \qquad M_{\text{rem}} = E_{\text{net}} \cdot M_{\text{rsd}}$$

where:
- $E_{\text{net}}$ is the net residue removal fraction (dimensionless),
- $E_{\text{harv}}$ is `harv_eff` (or the scheduled efficiency when positive for residue harvest, dimensionless),
- $HI_{\text{ovr}}$ is `harv_idx` (dimensionless),
- $M_{\text{rem}}$ is removed residue mass (`kg/ha`), and
- $M_{\text{rsd}}$ is surface plant residue mass (`kg/ha`). For `grain`/`picker` ([`mgt_harvgrain.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_harvgrain.f90#L40-L48)) and `tuber`/`peanuts` ([`mgt_harvtuber.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_harvtuber.f90#L43-L46)) harvests, `harv_idx` is not used; grain harvests instead use the plant's simulated harvest index from [**plants.plt**](../../databases/plants.plt/README.md) (floored by `wsyf` at [`mgt_harvgrain.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_harvgrain.f90#L43)).
