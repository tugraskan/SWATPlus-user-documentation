---
description: "This file defines saturated-buffer connections between HRUs."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file defines saturated-buffer connections between HRUs.

SWAT+ looks for `satbuffer.str` in the simulation working directory; it is not selected through `file.cio`. See the [sat_buff_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/sat_buff_read.f90#L34) reader.

# satbuffer.str

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Record name | string | n/a | — | — |
| [hru_src](hru_src.md) | Source HRU supplying tile inflow | integer | n/a | — | — |
| [frac_src](frac_src.md) | Fraction used in buffer inflow and nitrate partitioning | real | fraction | — | — |
| [flocon_dtbl](flocon_dtbl.md) | Decision table controlling flow into the buffer HRU | string | n/a | — | — |
| [hru_rcv](hru_rcv.md) | Receiving HRU acting as the saturated buffer | integer | n/a | — | — |
| [lyr](lyr.md) | Receiving soil-layer index | integer | n/a | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
