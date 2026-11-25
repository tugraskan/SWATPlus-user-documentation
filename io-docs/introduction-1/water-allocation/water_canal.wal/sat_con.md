---
description: "Canal seepage conductivity"
---

# sat_con

**Code reference:** `canal(ic)%sat_con` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L205), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_canal_read.f90#L46,L55)).

Canal bed hydraulic conductivity for seepage (`mm/day`). In [`wallo_canal.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_canal.f90#L35), daily canal seepage is computed as:

$$V_{\text{seep}} = K_{\text{sat}} \cdot d \cdot L$$

where $V_{\text{seep}}$ is daily canal seepage ($\text{m}^3\text{/d}$), $K_{\text{sat}}$ is `canal(ican)%sat_con` (`mm/day`), $d$ is canal depth (`m`), and $L$ is canal length (`km`) (note that $1\text{ mm/d} \times 1\text{ m} \times 1\text{ km} = 1\text{ m}^3\text{/d}$). Also copied into `gwflow` canal bed conductivity structures in [`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1263,L1272,L1374).
