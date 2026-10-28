---
description: "Supplies initial groundwater solute concentrations for groundwater cells when solute transport is enabled."
---

# cell_sol.gw

{% hint style="info" %}
The inspected Editor has an exporter for this filename; generation depends on the relevant feature settings. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Supplies initial groundwater solute concentrations for groundwater cells when solute transport is enabled.

SWAT+ uses the literal filename `cell_sol.gw` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [gwflow_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_read.f90#L1668). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a header record, then a header record.

### Record at line 1672

Source condition/loop: `if(gw_solute_flag == 1) then > if(i_exist) then > if(i_exist) then > do i=1,ncell`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [cell_id](cell_id.md) | Identifier of the groundwater cell whose solute state is initialized by this record | integer | n/a | — | — |
| [conc](conc.md) | Initial solute concentration in groundwater for the identified cell | real | — | — | — |
