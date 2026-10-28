---
description: "Defines wetland bed properties used by the groundwater flow (gwflow) routing, read as a data record and applied to the wetland identified by name on the matching HRU index."
---

# gwflow.wetland

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines wetland bed properties used by the groundwater flow (gwflow) routing, read as a data record and applied to the wetland identified by name on the matching HRU index.

SWAT+ uses the literal filename `gwflow.wetland` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [wet_read_hyd.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/wet_read_hyd.f90#L80). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a header record, then a header record.

### Data record

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [wet_name](wet_name.md) | Identifier of the wetland (character string) read from the gwflow.wetland file; used to locate the numeric suffix that selects the target HRU index | string | n/a | — | — |
| [thick_val](thick_val.md) | Bed thickness (real value) read from the gwflow.wetland file and copied into the wetland thickness storage for the matched HRU | real | — | — | — |
