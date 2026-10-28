---
description: "Defines named aquifer initial-condition sets by referencing pesticide, pathogen, heavy-metal, salt, and general-constituent initialization records."
---

# initial.aqu_cs

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines named aquifer initial-condition sets by referencing pesticide, pathogen, heavy-metal, salt, and general-constituent initialization records.

SWAT+ uses the literal filename `initial.aqu_cs` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [aqu_read_init_cs.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/aqu_read_init_cs.f90#L42). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record, then a header record.

### Data record

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Identifier that cross-walks with aqudb(iaqu)%aqu_ini, used to associate this initial condition record with its corresponding entry in the aquatic database | string | n/a | — | — |
| [pest](pest.md) | Name of the referenced pesticide initialization record | string | n/a | — | — |
| [path](path.md) | Name of the referenced pathogen initialization record | string | n/a | — | — |
| [hmet](hmet.md) | Name of the referenced heavy-metal initialization record | string | n/a | — | — |
| [salt](salt.md) | Name of the referenced salt initialization record | string | n/a | — | — |
| [cs](cs.md) | Name of the referenced general-constituent initialization record | string | n/a | — | — |
