---
description: "Defines pesticide degradation pathways by listing parent pesticides and their daughter metabolites, including the fraction of parent degradation in each environmental compartment (foliar, soil, aquatic, benthic) that yields each metabolite."
---

# pest_metabolite.pes

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines pesticide degradation pathways by listing parent pesticides and their daughter metabolites, including the fraction of parent degradation in each environmental compartment (foliar, soil, aquatic, benthic) that yields each metabolite.

SWAT+ uses the literal filename `pest_metabolite.pes` in the simulation working directory rather than selecting this filename through `file.cio`. It is read by [pest_metabolite_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/pest_metabolite_read.f90#L29). File-presence requirements and feature conditions are determined by this reader; a missing file is not assumed to be harmless.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record, then a header record.

### Record at line 50

Source condition/loop: `if (i_exist ) then > do > do iparent = 1, imax`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [parent_name](parent_name.md) | Name of the parent pesticide to which the following metabolites belong | string | n/a | — | — |
| [num_metab](num_metab.md) | Number of daughter metabolites defined for this parent pesticide | integer | n/a | — | — |

### Record at line 60

Source condition/loop: `if (i_exist ) then > do > do iparent = 1, imax > do ip = 1, db_mx%pestparm > if (parent_name == pestdb(ip)%name) then > do imeta = 1, num_metab`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Name of the daughter metabolite produced from the parent pesticide | string | n/a | — | — |
| [foliar_fr](foliar_fr.md) | Fraction of parent pesticide degradation in the foliar compartment that forms this daughter metabolite | real | — | — | — |
| [soil_fr](soil_fr.md) | Fraction of parent pesticide degradation in the soil compartment that forms this daughter metabolite | real | — | — | — |
| [aq_fr](aq_fr.md) | Fraction of parent pesticide degradation in the aquatic compartment that forms this daughter metabolite | real | — | — | — |
| [ben_fr](ben_fr.md) | Fraction of parent pesticide degradation in the benthic compartment that forms this daughter metabolite | real | — | — | — |
