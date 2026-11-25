# Longer-Period GWFlow Basin Heat Balance

`gwflow_basin_heat_yr.txt` and `gwflow_basin_heat_aa.txt` share 25 headings/data values. They use the seven standard identifiers, replace daily `ts`, `hbef`, and `haft` with `hdel`, retain the heat-flux headings `recharge`, `gw_et`, `gw_sw`, `sw_gw`, `sat_excess`, `soil`, `lateral`, `dispersion`, `boundary`, `pump_allo`, `pump_ext`, `tile`, `reservoir`, `wetland`, `canal`, `floodplain`, and `pond`, and omit daily `error` and `tavg`. There is no monthly heat file in the inspected source.

{% hint style="warning" %}
Each file has 25 headings/data values but only 24 unit entries. The units row ends before the final `pond` heading. Yearly amounts are in MJ and average-annual amounts are in MJ per simulation year. [Printed units](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L203-L229), [Average-annual divisor](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L2084-L2101)
{% endhint %}

Yearly `hdel` adds each day's `haft − hbef`. The 17 yearly flux fields add the corresponding [daily amounts](daily-basin-heat-balance.md#heat-storage-and-flux-fields), so they carry forward the last-step dispersion behavior and the zero pond heat field. The average-annual writer divides the simulation sums by configured `time%nbyr`. [Daily amounts and accumulation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L1012-L1079), [Average-annual writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L2083-L2112)

The daily routine adds all 18 heat terms directly to both accumulators, so yearly and average-annual results include a final partial month. [Daily accumulation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L1041-L1080) · [Period dispatch](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_simulate.f90#L459-L474)

[Back to the GWFlow Outputs index](README.md).
