# GWFlow HRU Pumping

`gwflow_hru_pump_day.txt`, `gwflow_hru_pump_mon.txt`, `gwflow_hru_pump_yr.txt`, and `gwflow_hru_pump_aa.txt` use `jday`, `mon`, `day`, `yr`, `unit`, `gis_id`, `name`, and `pump_allo`. Any `y` on a named `gwflow_pump` row enables all four files. With the row absent, the switch defaults to on.

The printed daily unit is m3/day, monthly/yearly rows are totals in m3, and average annual is m3/yr using configured `time%nbyr`. These HRU quantities are positive removed-water diagnostics, unlike negative cell `pump_allo` values. The long-format writers emit only positive records.

{% hint style="warning" %}
The simulator adds `hru_pump` to monthly/yearly arrays and resets it before calling the daily long-format output routine. That routine then tests `hru_pump(i) > 0`; it therefore does not preserve the day's earlier pumping values in this call sequence. An empty daily long-format file is not evidence of no pumping.
{% endhint %}

The allocation routine itself assigns the HRU diagnostic, so repeated requests can also replace it ([accumulate and reset](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_simulate.f90#L108); [daily output call](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_simulate.f90#L460); [daily guard](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L1247)).

[Back to the GWFlow Outputs index](README.md).
