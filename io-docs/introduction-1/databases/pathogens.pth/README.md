---
description: "Defines per-pathogen parameters governing die-off, growth, partitioning, and transport of persistent and less-persistent bacteria across soil solution, sorbed soil phase, foliage, streams, and reservoirs, including temperature adjustment, rainfall washoff, manure association, percolation, and a detection threshold."
---

# pathogens.pth

{% hint style="info" %}
The inspected Editor has a dispatched exporter for this input format; generation depends on project settings. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines per-pathogen parameters governing die-off, growth, partitioning, and transport of persistent and less-persistent bacteria across soil solution, sorbed soil phase, foliage, streams, and reservoirs, including temperature adjustment, rainfall washoff, manure association, percolation, and a detection threshold.

The reader obtains the filename through `in_parmdb%pathcom_db`.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record, then a header record, then a title record.

### Data record

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
