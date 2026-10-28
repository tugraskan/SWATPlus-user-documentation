---
description: "Defines organic-mineral composition of a manure or fertilizer entry by recording the mass fractions of water, carbon, mineral nitrogen (split between NO3 and NH3), mineral phosphorus, organic nitrogen, and organic phosphorus, along with a name used to crosswalk the entry to fertilizer records and a free-text description of the manure type."
---

# manure_om.frt

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines organic-mineral composition of a manure or fertilizer entry by recording the mass fractions of water, carbon, mineral nitrogen (split between NO3 and NH3), mineral phosphorus, organic nitrogen, and organic phosphorus, along with a name used to crosswalk the entry to fertilizer records and a free-text description of the manure type.

SWAT+ uses the literal filename `manure_om.frt` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [manure_orgmin_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/manure_orgmin_read.f90#L27). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record, then a header record.

### Data record

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Identifier used to crosswalk this manure/fertilizer entry to fertilizer records, constructed from manure_region, manure_source, and manure_type | string | n/a | — | — |
| [frac_water](frac_water.md) | Mass fraction of the manure that is water, expressed as kg water per kg of (manure + water) | real | — | — | — |
| [fcbn](fcbn.md) | Mass fraction of the fertilizer that is carbon, expressed as kg C per kg of fertilizer | real | — | — | — |
| [fminn](fminn.md) | Mass fraction of the fertilizer that is mineral nitrogen (sum of NO3 and NH3), expressed as kg minN per kg of fertilizer | real | — | — | — |
| [fminp](fminp.md) | Mass fraction of the fertilizer that is mineral phosphorus, expressed as kg minP per kg of fertilizer | real | — | — | — |
| [forgn](forgn.md) | Mass fraction of the fertilizer that is organic nitrogen, expressed as kg orgN per kg of fertilizer | real | — | — | — |
| [forgp](forgp.md) | Mass fraction of the fertilizer that is organic phosphorus, expressed as kg orgP per kg of fertilizer | real | — | — | — |
| [fnh3n](fnh3n.md) | Mass fraction of the mineral nitrogen content that is NH3, expressed as kg NH3-N per kg of mineral N | real | — | — | — |
| [description](description.md) | Free-text description of the manure type | string | n/a | — | — |
