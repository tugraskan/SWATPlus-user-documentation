---
description: "This file links landscape units to groundwater cells and gives their intersection areas."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file links landscape units to groundwater cells and gives their intersection areas.

SWAT+ looks for `lsucell.gw` in the simulation working directory; it is not selected through `file.cio`. See the [gwflow_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_read.f90#L2055) reader.

# lsucell.gw

The file starts with a title, the landscape-unit count, and the connected-unit count on separate lines. List the connected-unit identifiers, one per line, then include the two connection-header lines. Each association row gives the landscape-unit identifier, total unit area, groundwater cell identifier, and intersection area.

## Landscape-unit count

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [nlsu](nlsu.md) | Number of land-use source (LSU) entries in this linkage block | integer | n/a | — | — |

## Connected-unit count

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [nlsu_connected](nlsu_connected.md) | Count of LSU-to-grid-cell connections to be read in the following association records | integer | n/a | — | — |

## Connected-unit identifiers

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [lsu_id](lsu_id.md) | Identifier of the LSU being linked to one or more groundwater grid cells | integer | n/a | — | — |

## Cell associations

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [lsu](lsu.md) | Identifier of the LSU that owns the grid-cell association on this record | integer | n/a | — | — |
| [lsu_area](lsu_area.md) | Total area of the LSU used as the denominator when computing the fractional grid-cell coverage | real | — | — | — |
| [lsu_cells](lsu_cells.md) | Groundwater grid cell index associated with the LSU on this record | integer | n/a | — | — |
| [poly_area](poly_area.md) | Planimetered polygon area of the LSU-grid-cell intersection | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
