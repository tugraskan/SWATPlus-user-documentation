---
description: "Supplies the twelve texture-class records read into the LTE soil database: texture label, available water capacity, porosity, and the source field scon. See the source limitation below."
---

# soils_lte.sol

{% hint style="info" %}
The inspected Editor has a dispatched exporter for this input format; generation depends on project settings. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Supplies the twelve texture-class records read into the LTE soil database: texture label, available water capacity, porosity, and the source field scon. See the source limitation below.

The reader obtains the filename through `in_sol%lte_sol`.

{% hint style="warning" %}
Source limitation: Outer read loop lacks a normal exit before re-reading/reallocating; source concern, not a reproduced runtime result. These pages describe the inspected source and do not establish a working runtime configuration.
{% endhint %}

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record, then a header record.

### Data record

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [texture](texture.md) | Texture class identifier for the soil entry, matched against the HRU LTE database during read operations | string | n/a | — | — |
| [awc](awc.md) | Available water capacity value for the soil, scaled by the soil layer thickness when assigned to the HRU LTE state | real | — | — | — |
| [por](por.md) | Porosity value for the soil, scaled by the soil layer thickness when assigned to the HRU LTE state | real | — | — | — |
| [scon](scon.md) | Source value copied into hlt(i)%sc during LTE HRU initialization; its physical interpretation is not established here | real | — | — | — |
