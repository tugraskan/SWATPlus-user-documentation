# pest_water.ini

This file supplies named pesticide initialization data for water and benthic sediment. It does not contain the soil/plant initialization columns `sw_frac`, `nut`, `pest`, `path`, `salt`, or `hmet` previously listed here.

The following describes the reader in SWAT+ main `6f515368`. The file begins with a title and a header. The number of pesticide values is `cs_db%num_pests`.

## Initialization name

| Field | Code reference | Declared type | Description |
| --- | --- | --- | --- |
| name* | `pest_init_name(ipesti)` | `character(len=16)` | Name of the initialization entry. |

\* `name` is read into the separate character array `pest_init_name`, rather than the `name` component of `pest_water_ini`.

## Values read by the loading pass

After the name, one list-directed read requests the following values in order. The array names below are code identifiers, not verified Editor column headers.

| Position | Field | Code reference | Declared type | Description |
| --- | --- | --- | --- | --- |
| 1 | label* | `titldum` | `character(len=80)` | Leading character token; its contents are not used by this read. |
| 2 | water | `pest_water_ini(ipesti)%water` | `cs_water_init_concentrations` | Array of `cs_db%num_pests` real values for water. |
| 3 | benthic | `pest_water_ini(ipesti)%benthic` | `cs_water_init_concentrations` | Array of `cs_db%num_pests` real values for benthic sediment. |

\* `label` describes the leading token read into the local variable `titldum`.

{% hint style="warning" %}
The counting and loading passes use different record patterns. The counting pass reads one name record followed by two records per pesticide. After rewind, the loading pass reads the name and then uses a single list-directed read for a label, the complete water array, and the complete benthic array. Consequently, the loading-pass table alone is not a guaranteed working file template. This source inconsistency needs a code correction or a tested fixture before a working layout can be prescribed. No runtime validation is claimed here.
{% endhint %}

Pesticide-specific units, recommended defaults, and ranges are not established here from the generic constituent-type comments.

[Counting pass](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/pest_cha_res_read.f90#L34), [loading pass](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/pest_cha_res_read.f90#L62), and [array declarations](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/constituent_mass_module.f90#L331).
