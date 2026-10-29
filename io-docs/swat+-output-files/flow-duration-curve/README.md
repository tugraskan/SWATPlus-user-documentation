# Flow Duration Curve

`flow_duration_curve.out` is opened when flow-duration-curve output is enabled in `print.prt`. It summarizes the simulated flow distribution rather than reporting one row per time step.

| Field | Description | Unit |
| --- | --- | --- |
| [ob_typ](ob_typ.md) | Object type | n/a |
| [props](props.md) | Object or property identifier | n/a |
| [area_ha](area_ha.md) | Contributing area | ha |
| [flash_idx](flash_idx.md) | Flashiness index | n/a |
| [mean](mean.md) | Mean flow | m3/s |
| [max](max.md) | Maximum flow | m3/s |
| [p.1](p-dot-1.md), [p.5](p-dot-5.md), [p1](p1.md), [p2](p2.md), [p3](p3.md), [p5](p5.md), [p10](p10.md), [p15](p15.md), [p20](p20.md), [p25](p25.md), [p30](p30.md), [p35](p35.md), [p40](p40.md), [p45](p45.md), [p50](p50.md), [p55](p55.md), [p60](p60.md), [p65](p65.md), [p70](p70.md), [p75](p75.md), [p80](p80.md), [p85](p85.md), [p90](p90.md), [p95](p95.md), [p97](p97.md), [p98](p98.md), [p99](p99.md) | Flow-duration percentiles printed by the model | m3/s |
| [min](min.md) | Minimum flow | m3/s |

The percentile labels are reproduced exactly, including `p.1` and `p.5`.
