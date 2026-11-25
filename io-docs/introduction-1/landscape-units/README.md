# Landscape Units

The Landscape Units and Regions files correspond to the `regions` line of `file.cio` (`in_regs`, [`input_file_module.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/input_file_module.f90#L278), read in [`readcio_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/readcio_read.f90#L86)), except `element.ccu`, which is opened directly by [`ch_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_elements.f90#L145) rather than `file.cio`.

A Landscape Unit (LSU) groups HRUs and HRU-LTEs for spatial aggregation (such as subbasins, upland/floodplain units, or grid cells). In SWAT+ main (`6f515368`), `ls_unit.def` and `ls_unit.ele` are loaded in [`main.f90.in`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/main.f90.in#L69) via [`lsu_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/lsu_read_elements.f90#L1-L138) and are actively used for LSU- and basin-level output aggregation ([`lsu_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/lsu_output.f90#L21-L74), [`lsu_carbon_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/lsu_carbon_output.f90#L30-L50), [`basin_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_output.f90#L30-L53), [`basin_sw_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_sw_init.f90#L36-L78), [`basin_ls_pest_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_ls_pest_output.f90#L31-L32), [`soil_nutcarb_write.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_write.f90#L248-L251)), GWFlow HRU-to-LSU recharge and groundwater ET aggregation ([`gwflow_rech.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_rech.f90#L71-L78), [`gwflow_gwet.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_gwet.f90#L36-L43)), dynamic HRU area updates ([`hru_fr_change.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_fr_change.f90#L79-L97)), and soft-calibration HRU areas ([`lcu_read_softcal.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/lcu_read_softcal.f90#L108)).

{% hint style="warning" %}
Three `file.cio` `regions` slots are never opened in SWAT+ main (`6f515368`): `ls_cal.reg` (`in_regs%cal_lcu`) and `ch_catunit.ele` (`in_regs%ele_cha`) are unreferenced in the source, and `aqu_reg.def` (`in_regs%def_aqu_reg`) is checked with `inquire` in [`aqu_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_read_elements.f90#L86-L89) before line 89 mistakenly opens `in_regs%def_aqu` (`aqu_catunit.def`).
{% endhint %}

## Documented Files

* **Landscape Units** (active via [`lsu_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/lsu_read_elements.f90#L1-L138)):
  * [**ls\_unit.def**](ls_unit.def/README.md) defines each Landscape Unit and the element IDs it contains.
  * [**ls\_unit.ele**](ls_unit.ele/README.md) lists all HRUs and HRU-LTEs and their basin and LSU area fractions.
* **Landscape Regions** (uncalled reader [`reg_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reg_read_elements.f90#L1-L205)):
  * [**ls\_reg.def**](ls_reg.def/README.md) defines landscape regions, land-use groups, and their element lists.
  * [**ls\_reg.ele**](ls_reg.ele/README.md) identifies model objects included in landscape regions.
* **Aquifer Cataloging Units** (called from [`proc_cal.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/proc_cal.f90#L28) via [`aqu_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_read_elements.f90#L1-L195)):
  * [**aqu\_catunit.def**](aqu_catunit.def/README.md) groups aquifers into cataloging units.
  * [**aqu\_catunit.ele**](aqu_catunit.ele/README.md) identifies objects included in aquifer cataloging units and their area fractions.
* **Channel Cataloging Units and Regions** (called from [`proc_cal.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/proc_cal.f90#L29) via [`ch_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_elements.f90#L1-L190)):
  * [**ch\_catunit.def**](ch_catunit.def/README.md) groups channels into cataloging units.
  * [**ch\_reg.def**](ch_reg.def/README.md) defines channel regions and their element lists.
  * [**element.ccu**](element.ccu/README.md) identifies channel cataloging-unit elements and their area fractions.
* **Point-Source (Recall) Cataloging Units and Regions** (called from [`proc_cal.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/proc_cal.f90#L31) via [`rec_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/rec_read_elements.f90#L1-L183)):
  * [**rec\_catunit.def**](rec_catunit.def/README.md) groups point sources into cataloging units.
  * [**rec\_reg.def**](rec_reg.def/README.md) defines point-source regions and their element lists.
  * [**rec\_catunit.ele**](rec_catunit.ele/README.md) identifies objects included in point-source cataloging units and their area fractions.
* **Reservoir Cataloging Units and Regions** (called from [`proc_cal.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/proc_cal.f90#L30) via [`res_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read_elements.f90#L1-L185)):
  * [**res\_catunit.def**](res_catunit.def/README.md) groups reservoirs into cataloging units.
  * [**res\_reg.def**](res_reg.def/README.md) defines reservoir regions and their element lists.
  * [**res\_catunit.ele**](res_catunit.ele/README.md) identifies objects included in reservoir cataloging units and their area fractions.
