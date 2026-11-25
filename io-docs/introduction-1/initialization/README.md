# Initialization

The initialization input files define starting conditions for soil, plant, aquifer, channel, reservoir, and wetland states at the beginning of a SWAT+ simulation.

## Files listed in `file.cio` (`init` row)

In [`readcio_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/readcio_read.f90#L80), the `init` row of [**file.cio**](../master-file-file.cio.md) populates `in_init` (`type (input_init)`, [`input_file_module.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/input_file_module.f90)):

* [**soil\_plant.ini**](soil_plant.ini/) — links HRUs to soil nutrient, pesticide, pathogen, salt, heavy-metal, and general-constituent initialization records.
* [**om\_water.ini**](om_water.ini/) — initial water volume fraction, sediment, organic/mineral nutrients, and water temperature for channels, reservoirs, and wetlands.
* [**pest\_hru.ini**](pest_hru.ini/) — initial pesticide concentrations in HRU soil and on plant foliage.
* [**pest\_water.ini**](pest_water.ini/) — initial pesticide concentrations in water and benthic sediment for channels, reservoirs, and aquifers.
* [**path\_hru.ini**](path_hru.ini/) — initial pathogen levels in HRU soil and on plant foliage.
* [**path\_water.ini**](path_water.ini/) — initial pathogen levels in channel and reservoir water and benthic sediment.
* [**hmet\_hru.ini**](hmet_hru.ini/) — initial heavy-metal values for HRU soil and plants (parsed into memory, but not used in simulation calculations).

Note that [**plant.ini**](../landuse-and-management/plant.ini/) (also listed on the `init` row of `file.cio`) is documented under [Landuse and Management](../landuse-and-management/), and that the `hmet_water` (`hmet_water.ini`) and `salt_water` (`salt_water.ini`) slots in `input_init` have no reader routines in SWAT+ main (`6f515368`).

## Constituent and salt files in the working directory

SWAT+ opens the following salt and general-constituent initialization files directly by fixed filename in the simulation working directory rather than through `file.cio`:

* [**salt\_hru.ini**](salt_hru.ini/) — initial soil salt ion concentrations and mineral percentages for HRUs.
* [**salt\_aqu.ini**](salt_aqu.ini/) — initial aquifer salt ion concentrations and mineral percentages.
* [**salt\_channel.ini**](salt_channel.ini/) — initial channel-water salt ion concentrations.
* [**cs\_hru.ini**](cs_hru.ini/) — initial dissolved and sorbed general-constituent (Se, B) values for HRU soil.
* [**cs\_aqu.ini**](cs_aqu.ini/) — initial dissolved and sorbed general-constituent values for aquifers.
* [**cs\_channel.ini**](cs_channel.ini/) — initial channel-water general-constituent concentrations.
* [**initial.aqu\_cs**](initial.aqu_cs/) — maps aquifers to pesticide, pathogen, salt, and general-constituent initialization sets.
* [**initial.cha\_cs**](initial.cha_cs/) — maps channels (by row alignment with `initial.cha`) to pathogen, salt, and general-constituent initialization sets.

Object-level organic-mineral and constituent initialization wrapper files are documented in their respective spatial-object families: [**initial.aqu**](../aquifers/initial.aqu/) (Aquifers), [**initial.cha**](../channels/initial.cha/) (Channels), and [**initial.res**](../reservoirs/initial.res/) (Reservoirs).
