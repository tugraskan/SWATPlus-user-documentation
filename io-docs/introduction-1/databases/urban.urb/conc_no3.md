---
description: Concentration of NO3-N in suspended solid load from impervious areas
---

# conc\_no3

**Code reference:** `urbdb(iu)%tno3conc` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/urban_data_module.f90#L15)).

Nitrate-N concentration in suspended solids from impervious areas, in mg NO3-N per kg of solids. Nitrate load is `conc_no3n × solids / 1e6` (kg/ha), and the rest of the total N goes to organic N ([`hru_urban.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_urban.f90#L148-L168)). It is used only by the build-up/wash-off method.

{% hint style="warning" %}
Suspected defect (source reading): in sub-daily runs the nitrate load is held in an integer variable ([`hru_urbanhr.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_urbanhr.f90#L76), [`hru_urbanhr.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_urbanhr.f90#L113)), so it is truncated to whole kg/ha.
{% endhint %}
