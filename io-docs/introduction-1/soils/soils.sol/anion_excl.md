---
description: Fraction of porosity (void space) from which anions are excluded
---

# anion\_excl

**Code reference:** `soildb(isol)%s%anion_excl` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/soil_data_module.f90#L68)).

Most soil minerals are negatively charged at normal pH and the net interaction with anions such as nitrate is a repulsion from particle surfaces. This repulsion is termed negative adsorption or anion exclusion. Anions are excluded from the area immediately adjacent to mineral surfaces due to preferential attraction of cations to these sites. This process has a direct impact on the transport of anions through the soil for it effectively excludes anions from the slowest moving portion of the soil water volume found closest to the charged particle surfaces (Jury et al., 1991). In effect, the net pathway of the anion through the soil is shorter than it would be if all the soil water had to be used (Thomas and McMahon, 1972).

#### References

> Jury et al., 1991
>
> Thomas and McMahon, 1972
