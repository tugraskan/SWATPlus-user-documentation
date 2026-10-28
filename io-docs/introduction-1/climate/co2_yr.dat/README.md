---
description: "Provides annual atmospheric CO2 concentrations (ppm) and the simulation years they apply to, used to drive time-varying CO2 forcing in SWAT+. Each line supplies a year identifier followed by the corresponding CO2 value."
---

# co2_yr.dat

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Provides annual atmospheric CO2 concentrations (ppm) and the simulation years they apply to, used to drive time-varying CO2 forcing in SWAT+. Each line supplies a year identifier followed by the corresponding CO2 value.

SWAT+ uses the literal filename `co2_yr.dat` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [co2_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/co2_read.f90#L45). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

Physical record order is: title, annual-record count (`yrs`), column header, then `yrs` records containing year and CO2 concentration. The source-group headings below do not change that order.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record.

### Record at line 57

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [iyr](iyr.md) | Simulation year (integer) identifying the start of the year for which the CO2 value is defined | integer | n/a | — | — |
| [co2](co2.md) | Atmospheric CO2 concentration (real) in parts per million (ppm) for the year given by iyr | real | — | — | — |

### Record at line 49

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [yrs](yrs.md) | Total number of annual CO2 records (integer) that follow in this file, used to size the internal storage array | integer | n/a | — | — |
