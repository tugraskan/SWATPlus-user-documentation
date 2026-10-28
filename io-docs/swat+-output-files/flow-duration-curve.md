# Flow Duration Curve

`flow_duration_curve.out` is opened when flow-duration-curve output is enabled in `print.prt`. It summarizes the simulated flow distribution rather than reporting one row per time step.

| Field | Description | Unit |
| --- | --- | --- |
| ob_typ | Object type | n/a |
| props | Object or property identifier | n/a |
| area_ha | Contributing area | ha |
| flash_idx | Flashiness index | n/a |
| mean | Mean flow | m3/s |
| max | Maximum flow | m3/s |
| p.1, p.5, p1, p2, p3, p5, p10, p15, p20, p25, p30, p35, p40, p45, p50, p55, p60, p65, p70, p75, p80, p85, p90, p95, p97, p98, p99 | Flow-duration percentiles printed by the model | m3/s |
| min | Minimum flow | m3/s |

The percentile labels are reproduced exactly, including `p.1` and `p.5`.
