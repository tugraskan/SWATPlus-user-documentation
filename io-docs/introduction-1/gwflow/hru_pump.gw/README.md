---
description: "Defines groundwater pumping observations tied to HRUs; first declares the count of pump observations, then lists per-observation HRU identifiers used to index pump data during simulation."
---

# hru_pump.gw

{% hint style="info" %}
The inspected Editor has an exporter for this filename; generation depends on the relevant feature settings. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines groundwater pumping observations tied to HRUs; first declares the count of pump observations, then lists per-observation HRU identifiers used to index pump data during simulation.

SWAT+ uses the literal filename `hru_pump.gw` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [gwflow_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_read.f90#L933). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

### Record at line 935

Source condition/loop: `if(i_exist) then`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [num_hru_pump_obs](num_hru_pump_obs.md) | Number of HRU groundwater pumping observations to be read and processed | integer | n/a | — | — |

### Record at line 938

Source condition/loop: `if(i_exist) then > do i=1,num_hru_pump_obs`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [hru_pump_ids(i)](hru_pump_ids_i.md) | HRU identifier associated with the i-th groundwater pumping observation | integer | n/a | — | — |
