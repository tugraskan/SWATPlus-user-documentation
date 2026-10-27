# satbuffer.str

Defines saturated-buffer connections between a source HRU and a receiving buffer HRU, including the flow-control decision-table name and receiving soil-layer index.

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
