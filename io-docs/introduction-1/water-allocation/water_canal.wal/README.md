---
description: "Defines canal features used by the water allocation and routing routines. The file begins with a count of canal records, followed by per-canal geometry, roughness, seepage, evaporation, and decision-table controls, and an optional list of aquifer loss fractions for each canal."
---

# water_canal.wal

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines canal features used by the water allocation and routing routines. The file begins with a count of canal records, followed by per-canal geometry, roughness, seepage, evaporation, and decision-table controls, and an optional list of aquifer loss fractions for each canal.

SWAT+ uses the literal filename `water_canal.wal` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [water_canal_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/water_canal_read.f90#L30). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record.

### Record at line 33

Source condition/loop: `if (i_exist) then > do`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [imax](imax.md) | Total number of canal records that follow in this file | integer | n/a | — | — |

### Record at line 44

Source condition/loop: `if (i_exist) then > do > do ic = 1, imax`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [i](i.md) | Leading integer identifier consumed by this source read | integer | n/a | — | — |
| [name](name.md) | Identifier name of the canal | string | n/a | — | — |
| [w_sta](w_sta.md) | Name of the nearby weather station used for canal meteorology | string | n/a | — | — |
| [init](init.md) | Name of the initial concentrations object assigned to the canal | string | n/a | — | — |
| [dtbl](dtbl.md) | Name of the decision table that determines canal outflow | string | n/a | — | — |
| [ddown_days](ddown_days.md) | Number of days over which canal storage is drawn down to zero | real | — | — | — |
| [w](w.md) | Bottom width of the canal cross section | real | — | — | — |
| [d](d.md) | Depth of the canal cross section | real | — | — | — |
| [l](l.md) | Length of the canal reach | real | — | — | — |
| [s](s.md) | Longitudinal slope of the canal | real | — | — | — |
| [ss](ss.md) | Side slope (horizontal-to-vertical) of the trapezoidal canal section | real | — | — | — |
| [sat_con](sat_con.md) | Saturated hydraulic conductivity used to compute percolation from the canal to groundwater | real | — | — | — |
| [evap_co](evap_co.md) | Coefficient applied to compute evaporation loss from the canal | real | — | — | — |
| [num_aqu](num_aqu.md) | Number of aquifer loss fractions listed for this canal | integer | n/a | — | — |

### Record at line 53

Source condition/loop: `if (i_exist) then > do > do ic = 1, imax`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [i](i.md) | Leading integer identifier consumed by this source read | integer | n/a | — | — |
| [name](name.md) | Identifier name of the canal to which the aquifer loss fractions apply | string | n/a | — | — |
| [w_sta](w_sta.md) | Name of the nearby weather station used for canal meteorology | string | n/a | — | — |
| [init](init.md) | Name of the initial concentrations object assigned to the canal | string | n/a | — | — |
| [dtbl](dtbl.md) | Name of the decision table that determines canal outflow | string | n/a | — | — |
| [ddown_days](ddown_days.md) | Number of days over which canal storage is drawn down to zero | real | — | — | — |
| [w](w.md) | Bottom width of the canal cross section | real | — | — | — |
| [d](d.md) | Depth of the canal cross section | real | — | — | — |
| [l](l.md) | Length of the canal reach | real | — | — | — |
| [s](s.md) | Longitudinal slope of the canal | real | — | — | — |
| [ss](ss.md) | Side slope (horizontal-to-vertical) of the trapezoidal canal section | real | — | — | — |
| [sat_con](sat_con.md) | Saturated hydraulic conductivity used to compute percolation from the canal to groundwater | real | — | — | — |
| [evap_co](evap_co.md) | Coefficient applied to compute evaporation loss from the canal | real | — | — | — |
| [num_aqu](num_aqu_2.md) | Number of aquifer loss fractions listed for this canal | integer | n/a | — | — |
| [aqu_loss_fr(iaq)](aqu_loss_fr_iaq.md) | Fraction of canal seepage loss allocated to each listed aquifer | real | — | — | — |
