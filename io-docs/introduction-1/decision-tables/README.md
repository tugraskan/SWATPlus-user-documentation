# Decision Tables

Decision tables combine condition rows, alternative columns, and action rows. Each alternative groups conditions that must be satisfied together. For each action, the outcome in a satisfied alternative determines whether that alternative enables the action.

![The four quadrants of a decision table](../../.gitbook/assets/DT_Quadrants.jpg)

For numeric comparisons, use `<`, `>`, `<=`, `>=`, `=`, or `/=`. Quote `/=` as `'/='` in the input file. A hyphen skips the condition for numeric comparisons. Category and probability conditions handle these tokens differently; see [lum.dtl alt](lum.dtl/alt.md). A misspelled condition keyword or action type is ignored without a warning. The general action evaluator considers an action row once if at least one satisfied alternative has a `y` outcome. [`cond_real.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cond_real.f90#L19-L52) · [`cond_integer.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cond_integer.f90#L15-L48) · [`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L99-L109)

- [lum.dtl](lum.dtl/) supplies land use and management rules.
- [scen_lu.dtl](scen_lu.dtl/) supplies scenario update rules.
- [res_rel.dtl](res_rel.dtl/) supplies reservoir and wetland release rules.
- [flo_con.dtl](flo_con.dtl/) supplies flow-control rules for water allocation and saturated buffers.
