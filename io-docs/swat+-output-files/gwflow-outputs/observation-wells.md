# GWFlow Observation Wells

`gwflow_obs_day.txt`, `gwflow_obs_mon.txt`, `gwflow_obs_yr.txt`, and `gwflow_obs_aa.txt` share the headings `jday`, `mon`, `day`, `yr`, `unit`, `gis_id`, `name`, `head`, `wt_depth`, `temperature`, `no3`, and `p`. Units are m, m, degC, mg/L, and mg/L for the final five fields. A value of -99 marks a disabled temperature/solute calculation. `unit` is the observation index, `gis_id` is the observed cell index, and names are generated as `obs_####`. Select cells with `observation_cell` in [outputs.gw](../../introduction-1/gwflow/outputs.gw/README.md). All four file openers default to on if `gwflow_obs` is absent. With no observation cells, the files contain only their preambles.

{% hint style="warning" %}
The monthly and yearly temperature and solute averages are reset before these values are read for observation output. The yearly zeros are also added to the observation AA accumulators. Enabled temperature, NO3, and P columns can therefore contain zero/default-derived values rather than valid period averages; the -99 marker alone does not establish validity.
{% endhint %}

Head is reset after writing and is not affected by this particular ordering defect. AA head uses yearly mean heads divided by configured `time%nbyr` ([monthly reset and write](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L1300); [yearly reset](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L1569); [yearly observations](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L1659)).

The observation reports use the same head and depth calculations as the cell water balance, including its [partial reporting periods and warm-up behavior](cell-water-balance.md#partial-reporting-periods).

[Back to the GWFlow Outputs index](README.md).
