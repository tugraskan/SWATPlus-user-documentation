---
description: "This file contains basin-wide carbon cycling parameters and the associated soil-layer carbon settings."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file contains basin-wide carbon cycling parameters and the associated soil-layer carbon settings.

# carbon.bsn

Use the basin parameters in the first table. The per-layer values belong in a companion file: `carbon.bsn` uses `carbon_lyr.bsn`, while another configured name such as `foo.bsn` uses `foo_lyr.bsn`. The companion starts with a title and column headings, followed by one row per layer.

## Basin parameters

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [frac_seq](frac_seq.md) | Fraction of total soil carbon assigned to sequestered (passive and slow) pools when initializing organic carbon pools | real | fraction | — | — |
| [frac_hum_microb](frac_hum_microb.md) | Fraction of carbon assigned to the microbial pool when initializing microbial organic carbon pools | real | — | — | — |
| [frac_hum_slow](frac_hum_slow.md) | Fraction of carbon assigned to the humus slow pool when initializing humus slow organic carbon pools | real | — | — | — |
| [frac_hum_passive](frac_hum_passive.md) | Fraction of carbon assigned to the humus passive pool when initializing humus passive organic carbon pools | real | — | — | — |
| [prmt_21](prmt_21.md) | Koc partition coefficient for carbon loss to water and sediment | real | — | — | — |
| [prmt_44](prmt_44.md) | Ratio of soluble carbon concentration in runoff to that in percolate | real | — | — | — |
| [till_eff_days](till_eff_days.md) | Number of days a tillage operation continues to affect carbon cycling processes | integer | n/a | — | — |
| [rtof](rtof.md) | Weighting factor partitioning the organic N and P concentration of septic effluent between the fresh and stable organic pools | real | — | — | — |
| [bio_consf](bio_consf.md) | Consumption factor applied during biomass mixing operations to reduce residue carbon | real | — | — | — |
| [till_consf](till_consf.md) | Consumption factor applied during tillage operations to reduce residue carbon | real | — | — | — |
| [tmpf](tmpf.md) | Selector for the temperature response function approach used in the Zhang et al. carbon decomposition model | integer | n/a | — | — |
| [watf](watf.md) | Selector for the water response function approach used in the Zhang et al. carbon decomposition model | integer | n/a | — | — |
| [tn](tn.md) | Minimum temperature bound (degrees Celsius) for the Zhang et al. carbon decomposition temperature function | real | — | — | — |
| [top](top.md) | Peak (optimum) temperature (degrees Celsius) for the Zhang et al. carbon decomposition temperature function | real | — | — | — |
| [tx](tx.md) | Maximum temperature bound (degrees Celsius) for the Zhang et al. carbon decomposition temperature function | real | — | — | — |
| [bmix_a](bmix_a.md) | Base intercept in the zz equation used by mgt_tillfactor for biomixing calculations | real | — | — | — |
| [bmix_b](bmix_b.md) | Slope coefficient in the zz equation used by mgt_tillfactor for biomixing calculations | real | — | — | — |
| [bmix_c](bmix_c.md) | Exponent multiplier in the zz equation used by mgt_tillfactor for biomixing calculations | real | — | — | — |
| [tillmix_a](tillmix_a.md) | Base intercept in the zz equation used by mgt_tillfactor for tillage mixing calculations | real | — | — | — |
| [tillmix_b](tillmix_b.md) | Slope coefficient in the zz equation used by mgt_tillfactor for tillage mixing calculations | real | — | — | — |
| [tillmix_c](tillmix_c.md) | Exponent multiplier in the zz equation used by mgt_tillfactor for tillage mixing calculations | real | — | — | — |
| [photo_degrade_factor](photo_degrade_factor.md) | Fraction by which surface residue carbon is reduced each time step due to photodegradation | real | — | — | — |
| [n_act_frac](n_act_frac.md) | Fraction of organic nitrogen in the active humus pool | real | — | — | — |
| [cnr_cap](cnr_cap.md) | Upper cap applied to the residue C:N ratio before computing the decomposition factor | real | — | — | — |
| [cnr_ref](cnr_ref.md) | Reference C:N ratio at which the decomposition factor equals one | real | — | — | — |
| [cpr_cap](cpr_cap.md) | Upper cap applied to the residue C:P ratio before computing the decomposition factor | real | — | — | — |
| [cpr_ref](cpr_ref.md) | Reference C:P ratio at which the decomposition factor equals one | real | — | — | — |
| [mathers_int](mathers_int.md) | Flag (0 or 1) selecting whether the Mathers method is used for initializing organic carbon fractions | integer | n/a | — | — |

## Soil-layer companion

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [layer_id](layer_id.md) | Identifier of the soil layer (1 to max_lyr) to which the following companion-layer carbon parameters apply | integer | n/a | — | — |
| [r_hp_rate](r_hp_rate.md) | Rate coefficient for the passive (humus passive) organic carbon pool on the identified layer | real | — | — | — |
| [r_hs_rate](r_hs_rate.md) | Rate coefficient for the slow (humus slow) organic carbon pool on the identified layer | real | — | — | — |
| [r_microb_rate](r_microb_rate.md) | Rate coefficient for the microbial organic carbon pool on the identified layer | real | — | — | — |
| [r_meta_rate](r_meta_rate.md) | Rate coefficient for the metabolic organic carbon pool on the identified layer | real | — | — | — |
| [r_str_rate](r_str_rate.md) | Rate coefficient for the structural organic carbon pool on the identified layer | real | — | — | — |
| [r_microb_top_rate](r_microb_top_rate.md) | Rate coefficient for the microbial top-layer organic carbon pool on the identified layer | real | — | — | — |
| [r_hs_hp](r_hs_hp.md) | Ratio between the slow and passive humus organic carbon pools on the identified layer | real | — | — | — |
| [r_a1co2](r_a1co2.md) | CO2 production fraction from the active organic carbon pool on the identified layer | real | — | — | — |
| [r_asco2](r_asco2.md) | CO2 production fraction from the slow organic carbon pool on the identified layer | real | — | — | — |
| [r_apco2](r_apco2.md) | CO2 production fraction from the passive organic carbon pool on the identified layer | real | — | — | — |
| [r_abco2](r_abco2.md) | CO2 production fraction from the base organic carbon pool on the identified layer | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
