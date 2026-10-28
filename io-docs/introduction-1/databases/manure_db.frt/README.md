---
description: "Defines named manure types by cross-referencing the constituent databases that supply each manure's organic/mineral, pesticide, pathogen, heavy-metal, salt, and other-constituent values, along with a human-readable description."
---

# manure_db.frt

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines named manure types by cross-referencing the constituent databases that supply each manure's organic/mineral, pesticide, pathogen, heavy-metal, salt, and other-constituent values, along with a human-readable description.

SWAT+ uses the literal filename `manure_db.frt` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [manure_db_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/manure_db_read.f90#L27). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record, then a header record.

### Data record

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Identifier matching this manure type against the organic/mineral constituent database | string | n/a | — | — |
| [org_min](org_min.md) | Identifier matching this manure type against the organic/mineral constituent database entry that supplies sediment, carbon, and nutrient values | string | n/a | — | — |
| [pests](pests.md) | Identifier matching this manure type against the pesticide database entry supplying pesticide concentrations | string | n/a | — | — |
| [paths](paths.md) | Identifier matching this manure type against the pathogen database entry supplying pathogen counts | string | n/a | — | — |
| [hmets](hmets.md) | Identifier matching this manure type against the heavy-metal database entry supplying heavy-metal concentrations | string | n/a | — | — |
| [salts](salts.md) | Identifier matching this manure type against the salt database entry supplying salt-ion concentrations | string | n/a | — | — |
| [constit](constit.md) | Identifier matching this manure type against the other-constituent database entry supplying additional constituent concentrations | string | n/a | — | — |
| [descrip](descrip.md) | Free-text description of the manure type | string | n/a | — | — |
