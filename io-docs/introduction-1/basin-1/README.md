# Basin

General watershed attributes are defined in two basin input files, [**codes.bsn**](codes.bsn/) (read by [`basin_read_cc.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_cc.f90#L16-L28)) and [**parameters.bsn**](parameters.bsn/) (read by [`basin_read_prm.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_prm.f90#L15-L28) with runtime defaults applied in [`basin_prm_default.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_prm_default.f90#L9-L61)). When dynamic soil carbon ([carbon](codes.bsn/carbon.md) = 2) is enabled, SWAT+ also reads [**carbon.bsn**](../carbon/carbon.bsn/) via [`carbon_bsn_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/carbon_bsn_read.f90#L47-L70) from the `basin` line of [**file.cio**](../master-file-file.cio.md). These attributes control a diversity of physical processes at the watershed level. Users can use the default values set by the interfaces or change them to better reflect what is happening in a given watershed.

{% hint style="info" %}
Even if nutrients are not being studied in a watershed, some attention must be paid to basin nutrient variables, because nutrient cycling impacts plant growth, which in turn affects the hydrologic cycle.

Variables governing bacteria or pesticide transport need to be initialized only if these processes are being modeled in the watershed.
{% endhint %}
