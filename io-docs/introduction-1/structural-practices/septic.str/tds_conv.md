---
description: Conversion factor for plaque from Total Dissolved Solids
---

# tds\_conv

**Code reference:** `sep(isep)%plq` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/septic_data_module.f90#L39)).

Dimensionless conversion factor for biozone plaque accumulation from effluent solids ([`sep_biozone.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sep_biozone.f90#L219)):

$$\Delta M_{\text{plq}} = (R_{\text{mort}} - R_{\text{slg}}) + c_{\text{plq}} \, \frac{Q_{\text{in}} \, C_{\text{tss}}}{1000 \, A_{\text{hru}}}$$

where $\Delta M_{\text{plq}}$ is daily change in plaque mass (kg/ha), $c_{\text{plq}}$ is `tds_conv`, $R_{\text{mort}}$ and $R_{\text{slg}}$ are daily bacterial mortality and sloughing (kg/ha), $Q_{\text{in}}$ is daily effluent inflow ($\text{m}^3$), $C_{\text{tss}}$ is effluent TSS concentration from `septic.sep` (mg/L), and $A_{\text{hru}}$ is HRU area (ha). Note that despite the column name `tds_conv`, SWAT+ multiplies it by total suspended solids (`tssconcs`).
