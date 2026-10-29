# Flow Duration Curve

`flow_duration_curve.out` is opened when flow-duration-curve output is enabled in `print.prt`. It summarizes the simulated flow distribution rather than reporting one row per time step.

| Field | Description | Unit |
| --- | --- | --- |
| [ob_typ](flow-duration-curve/ob_typ.md) | Object type | n/a |
| [props](flow-duration-curve/props.md) | Object or property identifier | n/a |
| [area_ha](flow-duration-curve/area_ha.md) | Contributing area | ha |
| [flash_idx](flow-duration-curve/flash_idx.md) | Flashiness index | n/a |
| [mean](flow-duration-curve/mean.md) | Mean flow | m3/s |
| [max](flow-duration-curve/max.md) | Maximum flow | m3/s |
| [p.1](flow-duration-curve/p-dot-1.md), [p.5](flow-duration-curve/p-dot-5.md), [p1](flow-duration-curve/p1.md), [p2](flow-duration-curve/p2.md), [p3](flow-duration-curve/p3.md), [p5](flow-duration-curve/p5.md), [p10](flow-duration-curve/p10.md), [p15](flow-duration-curve/p15.md), [p20](flow-duration-curve/p20.md), [p25](flow-duration-curve/p25.md), [p30](flow-duration-curve/p30.md), [p35](flow-duration-curve/p35.md), [p40](flow-duration-curve/p40.md), [p45](flow-duration-curve/p45.md), [p50](flow-duration-curve/p50.md), [p55](flow-duration-curve/p55.md), [p60](flow-duration-curve/p60.md), [p65](flow-duration-curve/p65.md), [p70](flow-duration-curve/p70.md), [p75](flow-duration-curve/p75.md), [p80](flow-duration-curve/p80.md), [p85](flow-duration-curve/p85.md), [p90](flow-duration-curve/p90.md), [p95](flow-duration-curve/p95.md), [p97](flow-duration-curve/p97.md), [p98](flow-duration-curve/p98.md), [p99](flow-duration-curve/p99.md) | Flow-duration percentiles printed by the model | m3/s |
| [min](flow-duration-curve/min.md) | Minimum flow | m3/s |

The percentile labels are reproduced exactly, including `p.1` and `p.5`.
