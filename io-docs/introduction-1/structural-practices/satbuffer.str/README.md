---
description: This file defines saturated-buffer connections between HRUs.
---

# satbuffer.str

{% hint style="info" %}
This file is supported by the SWAT+ model, but no exporter was found in the inspected SWAT+ Editor version. It may need to be supplied separately. Editor checkout checked: `1efec55`.

The table below is based on the SWAT+ Fortran source code. Its contents should not be assumed to match the labels, defaults, or options available in SWAT+ Editor. A dash means that no recommended default or range has been established here; it is not a Fortran initialization value.
{% endhint %}

Defines saturated-buffer connections between a source HRU and a receiving buffer HRU, including the flow-control decision-table name and receiving soil-layer index.

SWAT+ looks directly for the literal filename `satbuffer.str` in the simulation working directory; this filename is not selected through `file.cio`. It is read by [sat_buff_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/sat_buff_read.f90#L34). If the file is absent, no saturated-buffer records are loaded from it.

The first line is a title and the second line is a header. Each subsequent record contains the fields below, in this order. There is no separate record-count line.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Record label identifying this saturated buffer definition | string | n/a | — | — |
| [hru_src](hru_src.md) | Source HRU supplying tile inflow | integer | n/a | — | — |
| [frac_src](frac_src.md) | Fraction used in buffer inflow and nitrate partitioning | real | fraction | — | — |
| [flocon_dtbl](flocon_dtbl.md) | Decision table controlling flow into the buffer HRU | string | n/a | — | — |
| [hru_rcv](hru_rcv.md) | Receiving HRU acting as the saturated buffer | integer | n/a | — | — |
| [lyr](lyr.md) | Receiving soil-layer index | integer | n/a | — | — |

Recommended defaults and ranges are not specified by this page. The dash does not imply a default of zero.
