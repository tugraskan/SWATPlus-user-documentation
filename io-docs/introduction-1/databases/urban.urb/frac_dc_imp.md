---
description: Fraction of directly connected impervious area in urban land type
---

# frac\_dc\_imp

**Code reference:** `urbdb(iu)%fcimp` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/urban_data_module.f90#L8)).

**Current use:** surface runoff is `pervious runoff × (1 − frac_dc_imp) + impervious runoff × frac_dc_imp` ([`sq_daycn.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sq_daycn.f90#L43-L54)).

Impervious areas can be differentiated into two groups, the area that is hydraulically connected to the drainage system and the area that is not directly connected. As an example, assume there is a house surrounded by a yard where runoff from the roof flows into the yard where it infiltrates into the soil. The rooftop is impervious, but it is not hydraulically connected to the drainage system. In contrast, a parking lot whose runoff enters a storm water drain is hydraulically connected.

When modeling urban areas, the connectedness of the drainage system must be quantified. The best methods for determining the fraction total and directly connected impervious areas is to conduct a field survey or analyze aerial photographs.
