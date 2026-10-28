---
description: "Defines basin-level carbon cycling parameters used to initialize soil organic carbon pools, set CO2 production and decay rates for residue and living organic matter, and control carbon transport and decomposition coefficients. A companion per-layer file (carbon_lyr.bsn, derived from this filename) supplies layer-specific rates and CO2 production fractions; both are read when the carbon option is enabled."
---

# carbon.bsn

{% hint style="info" %}
The inspected Editor has a dispatched exporter for this input format; generation depends on project settings. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines basin-level carbon cycling parameters used to initialize soil organic carbon pools, set CO2 production and decay rates for residue and living organic matter, and control carbon transport and decomposition coefficients. A companion per-layer file (carbon_lyr.bsn, derived from this filename) supplies layer-specific rates and CO2 production fractions; both are read when the carbon option is enabled.

The reader obtains the filename through `in_basin%carbon_bsn`.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record, then a header record.

The per-layer companion is derived from the configured carbon filename: carbon.bsn gives carbon_lyr.bsn and foo.bsn gives foo_lyr.bsn. It is not separately selected in file.cio. The reader requires it when the carbon option is enabled; its title and header are followed by per-layer rows. The companion fields appear in their own group below.

### Data record

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [frac_seq](frac_seq.md) | Fraction of total soil carbon assigned to sequestered (passive and slow) pools when initializing organic carbon pools | real | fraction | — | — |
| [frac_hum_microb](frac_hum_microb.md) | Fraction of carbon assigned to the microbial pool when initializing microbial organic carbon pools | real | — | — | — |
| [frac_hum_slow](frac_hum_slow.md) | Fraction of carbon assigned to the humus slow pool when initializing humus slow organic carbon pools | real | — | — | — |
| [frac_hum_passive](frac_hum_passive.md) | Fraction of carbon assigned to the humus passive pool when initializing humus passive organic carbon pools | real | — | — | — |
| [prmt_21](prmt_21.md) | Koc partition coefficient for carbon loss to water and sediment, used to compute the distribution coefficient as KD = KOC * C | real | — | — | — |
| [prmt_44](prmt_44.md) | Ratio of soluble carbon concentration in runoff to that in percolate, used to partition vertical and horizontal carbon transport | real | — | — | — |
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
| [n_act_frac](n_act_frac.md) | Fraction of organic nitrogen in the active humus pool, used in active-to-stable nitrogen mineralization flow | real | — | — | — |
| [cnr_cap](cnr_cap.md) | Upper cap applied to the residue C:N ratio before computing the decomposition factor | real | — | — | — |
| [cnr_ref](cnr_ref.md) | Reference C:N ratio at which the decomposition factor equals one | real | — | — | — |
| [cpr_cap](cpr_cap.md) | Upper cap applied to the residue C:P ratio before computing the decomposition factor | real | — | — | — |
| [cpr_ref](cpr_ref.md) | Reference C:P ratio at which the decomposition factor equals one | real | — | — | — |
| [mathers_int](mathers_int.md) | Integer flag (0 or 1) selecting whether the Mathers method is used for initializing organic carbon fractions | integer | n/a | — | — |

### Companion layer record

These fields belong to the derived-name carbon-layer companion, not the main carbon record.

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
