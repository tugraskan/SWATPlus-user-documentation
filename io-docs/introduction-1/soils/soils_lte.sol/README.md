---
description: "This file supplies soil properties for the twelve texture classes used by HRU-LTE."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies soil properties for the twelve texture classes used by HRU-LTE.

# soils_lte.sol

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

{% hint style="warning" %}
The current file-loading routine has a repeated-loading issue. A complete file layout does not establish that the model will initialize successfully with it.
{% endhint %}

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [texture](texture.md) | Texture class identifier for the soil entry | string | n/a | — | — |
| [awc](awc.md) | Available water capacity value for the soil | real | — | — | — |
| [por](por.md) | Porosity value for the soil, scaled by the soil layer thickness when assigned to the HRU LTE state | real | — | — | — |
| [scon](scon.md) | LTE soil coefficient | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
