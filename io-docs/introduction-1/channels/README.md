# Channels

There are several SWAT+ input files that control the simulation of channel processes.

## Active SWAT-DEG (`chandeg`) Channel Files

In SWAT+ main (`6f515368`), daily channel routing executes through the [`chandeg`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L374-L408) command path ([`sd_channel_control3.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_control3.f90#L1)), using:

* [**channel-lte.cha**](channel-lte.cha/) — main SWAT-DEG channel table linking each channel to its initialization, hydrology/sediment, and nutrient records:
  * [**initial.cha**](initial.cha/) — references files specifying initial water-column and benthic concentrations,
  * [**hyd-sed-lte.cha**](hyd-sed-lte.cha/) — channel geometry, hydraulics, floodplain, and sediment parameters,
  * [**sed\_nut.cha**](sed_nut.cha/) — additional channel sediment, nutrient settling, and erosion parameters (matched by `cha_hyd` name),
  * [**nutrients.cha**](nutrients.cha/) — QUAL2E in-stream nutrient and algal parameters.
* [**temperature.cha**](temperature.cha/) and [**shade\_factor.shf**](shade_factor.shf/) — channel water temperature parameters and daily shading factors *(note: from source reading at `6f515368`, [`ch_temp.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_temp.f90#L189-L200) reads record `0` of `w_temp` rather than the rows loaded by [`ch_read_temp.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_temp.f90#L50-L56))*.

## Legacy / Unused Channel Files

* [**channel.cha**](channel.cha/), [**hydrology.cha**](hydrology.cha/), and [**sediment.cha**](sediment.cha/) — read and initialized in [`proc_cha.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/proc_cha.f90#L19-L41), while the daily `case ("chan")` dispatch in [`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L305-L310) is commented out.
* [**nutrients.rte**](nutrients.rte/) — parsed into `rte_nut` by [`rte_read_nut.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/rte_read_nut.f90#L24-L57) when present, with no downstream executable references in `6f515368`.
