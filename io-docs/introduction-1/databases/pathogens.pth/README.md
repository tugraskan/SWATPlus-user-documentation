---
description: "This file contains parameters for pathogen growth, die-off, partitioning, and transport."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file contains parameters for pathogen growth, die-off, partitioning, and transport.

# pathogens.pth

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [pathnm](pathnm.md) | Name identifying the pathogen record | string | n/a | — | — |
| [do_soln](do_soln.md) | Die-off factor for persistent bacteria in soil solution | real | — | — | — |
| [gr_soln](gr_soln.md) | Growth factor for persistent bacteria in soil solution | real | — | — | — |
| [do_sorb](do_sorb.md) | Die-off factor for persistent bacteria adsorbed to the soil particle phase | real | — | — | — |
| [gr_sorb](gr_sorb.md) | Growth factor for persistent bacteria adsorbed to the soil particle phase | real | — | — | — |
| [kd](kd.md) | Partition coefficient relating pathogen between dissolved and sorbed phases in surface runoff | real | — | — | — |
| [t_adj](t_adj.md) | Temperature adjustment factor applied to bacterial die-off and growth | real | — | — | — |
| [washoff](washoff.md) | Fraction of bacteria on foliage washed off by a rainfall event | real | — | — | — |
| [do_plnt](do_plnt.md) | Die-off factor for persistent bacteria on foliage | real | — | — | — |
| [gr_plnt](gr_plnt.md) | Growth factor for persistent bacteria on foliage | real | — | — | — |
| [fr_manure](fr_manure.md) | Fraction of manure containing active colony-forming units | real | — | — | — |
| [perco](perco.md) | Percolation coefficient for the ratio of solution bacteria in the surface soil layer | real | — | — | — |
| [det_thrshd](det_thrshd.md) | Threshold detection level below which less-persistent bacteria in soil are considered insignificant and reset to zero | real | — | — | — |
| [do_stream](do_stream.md) | Die-off factor for persistent bacteria in streams | real | — | — | — |
| [gr_stream](gr_stream.md) | Growth factor for persistent bacteria in streams | real | — | — | — |
| [do_res](do_res.md) | Die-off factor for less-persistent bacteria in reservoirs | real | — | — | — |
| [gr_res](gr_res.md) | Growth factor for less-persistent bacteria in reservoirs | real | — | — | — |
| [conc_min](conc_min.md) | Minimum pathogen concentration applied as a floor in foliage and soil solution calculations | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
