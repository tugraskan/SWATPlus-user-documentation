---
description: "This file specifies the daughter metabolites formed when a parent pesticide degrades."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file specifies the daughter metabolites formed when a parent pesticide degrades.

SWAT+ looks for `pest_metabolite.pes` in the simulation working directory; it is not selected through `file.cio`. See the [pest_metabolite_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/pest_metabolite_read.f90#L29) reader.

# pest_metabolite.pes

After the title and column headings, enter the parent pesticide name and daughter-metabolite count. Follow these with one row per daughter metabolite, including its formation fractions.

## Parent pesticide

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [parent_name](parent_name.md) | Name of the parent pesticide to which the following metabolites belong | string | n/a | — | — |
| [num_metab](num_metab.md) | Number of daughter metabolites defined for this parent pesticide | integer | n/a | — | — |

## Daughter metabolites

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Record name | string | n/a | — | — |
| [foliar_fr](foliar_fr.md) | Fraction of parent pesticide degradation in the foliar compartment that forms this daughter metabolite | real | — | — | — |
| [soil_fr](soil_fr.md) | Fraction of parent pesticide degradation in the soil compartment that forms this daughter metabolite | real | — | — | — |
| [aq_fr](aq_fr.md) | Fraction of parent pesticide degradation in the aquatic compartment that forms this daughter metabolite | real | — | — | — |
| [ben_fr](ben_fr.md) | Fraction of parent pesticide degradation in the benthic compartment that forms this daughter metabolite | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
