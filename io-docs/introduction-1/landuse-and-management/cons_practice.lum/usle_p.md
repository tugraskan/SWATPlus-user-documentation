---
description: USLE P factor
---

# usle\_p

**Code reference:** `cons_prac(icp)%pfac` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/landuse_data_module.f90#L52), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cons_prac_read.f90#L45)).

Dimensionless USLE support-practice factor (`0.0–1.0`, default `1.0`). Assigned to `hru(iihru)%lumv%usle_p` in [`plant_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_init.f90#L373) and combined with soil erodibility, slope length-steepness, and surface rock cover to form the composite USLE multiplier in [`hydro_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydro_init.f90#L78-L80):

$$\text{USLE}_{\text{mult}} = 11.8 \cdot K_{\text{USLE}} \cdot P_{\text{USLE}} \cdot LS_{\text{USLE}} \cdot \exp(-0.053\,R_{\text{rock}})$$

where $P_{\text{USLE}}$ is `usle_p`, $K_{\text{USLE}}$ is top-layer soil erodibility (`usle_k`), $LS_{\text{USLE}}$ is the topographic factor (`usle_ls`), and $R_{\text{rock}}$ is top-layer rock fragment percent (`rock`). A value of `1.0` represents no support-practice reduction.
