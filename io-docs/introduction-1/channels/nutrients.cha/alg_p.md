---
description: Fraction of algal biomass that is phosphorus
---

# alg\_p

**Code reference:** `ch_nut(ich)%ai2` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/channel_data_module.f90#L140)).

Fraction of algal biomass that is phosphorus (`mg P/mg alg`, table default `0.02`, range `0.01–0.02`). In [`ch_read_nut.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_nut.f90#L66), values `<= 0.` are replaced with `0.015`.

In [`ch_watqual4.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_watqual4.f90#L327-L328), `ai2` determines dissolved phosphorus uptake by growing algae:

$$z = \alpha_2 \cdot \theta(\text{gra}) \cdot \text{algin}$$

where $z$ is the algal phosphorus uptake rate (`mg P/(L*day)`), $\alpha_2$ is `alg_p` (`mg P/mg alg`), $\theta(\text{gra})$ is the temperature-adjusted algal growth rate (`1/day`), and $\text{algin}$ is incoming algal biomass concentration (`mg alg/L`).

This uptake is subtracted from reach soluble phosphorus over travel duration $t_{\text{day}}$:

$$C_{\text{solP,out}} = C_{\text{solP}} + (x + y - z)\,t_{\text{day}}$$

where:
- $C_{\text{solP,out}}$ is outflow soluble phosphorus concentration (`mg P/L`),
- $C_{\text{solP}}$ is incoming soluble phosphorus concentration (`mg P/L`),
- $x$ is the organic phosphorus mineralization source (`mg P/(L*day)`),
- $y$ is the benthic dissolved phosphorus source (`mg P/(L*day)`),
- $z$ is the algal phosphorus uptake rate (`mg P/(L*day)`), and
- $t_{\text{day}}$ is reach travel duration (`days`).
