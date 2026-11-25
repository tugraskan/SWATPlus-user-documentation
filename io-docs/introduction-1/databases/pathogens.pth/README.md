---
description: "This file contains parameters for pathogen growth, die-off, partitioning, and transport."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file contains parameters for pathogen growth, die-off, partitioning, and transport.

# pathogens.pth

{% hint style="info" %}
SWAT+ dev also contains a reader for a file named `pathogen_db.pth` that fills the same pathogen array, but nothing calls it, so that file has no effect ([`pathogen_db_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pathogen_db_read.f90#L1-L58)). Use `pathogens.pth`.
{% endhint %}

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
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

{% hint style="warning" %}
Suspected defects (this comes from source reading, not a model run): HRU routines choose the pathogen record by the initialization record number and channel routing by list position, not by the matched name ([`path_ls_process.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/path_ls_process.f90#L34-L35), [`ch_rtpath.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_rtpath.f90#L90)). The surface runoff routine moves the whole surface-layer pathogen amount to runoff each day ([`path_ls_runoff.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/path_ls_runoff.f90#L26-L30)).
{% endhint %}
