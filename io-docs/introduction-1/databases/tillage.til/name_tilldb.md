---
description: Name of tillage record
---

# name (tillage.til)

**Code reference:** `tilldb(itl)%tillnm` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/tillage_data_module.f90#L20)).

The name holds up to 16 characters. Management operations and decision tables find the record by exact name ([`read_mgtops.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/read_mgtops.f90#L88), [`dtbl_lum_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dtbl_lum_read.f90#L132)).

The name `biomix` is special: its `mix_eff` and `mix_dp` set biological mixing, which falls back to 0.2 and 50 mm when no such record exists ([`till_parm_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/till_parm_read.f90#L48-L60)). This biological mixing runs when carbon = 2 in codes.bsn ([`hru_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L396-L397)).

The name of the tillage record is a primary key referenced when tillage operations are scheduled  in [**management.sch**](../../landuse-and-management/management.sch/) or [**lum.dtl**](../../decision-tables/lum.dtl/). All names in the **tillage.til** database must be unique.

| Name          | Description                      |
| ------------- | -------------------------------- |
| fallplow      | Generic Fall Plowing Operation   |
| sprgplow      | Generic Spring Plowing Operation |
| constill      | Generic Conservation Tillage     |
| zerotill      | Generic No-Till Mixing           |
| duckftc       | Duckfoot Cultivator              |
| fldcult       | Field Cultivator                 |
| furowout      | Furrow-out Cultivator            |
| marker        | Marker (Cultivator)              |
| rollcult      | Rolling Cultivator               |
| rowcult       | Row Cultivator                   |
| discovat      | Discovator                       |
| leveler       | Leveler                          |
| harrow        | Harrow (Tines)                   |
| culmulch      | Culti-Mulch Roller               |
| culpkpul      | Culti-Packer Pulverizer          |
| landlevl      | Land Plane-Leveler               |
| landall       | Landall, Do-All                  |
| lasrplan      | Laser Planer                     |
| levpldis      | Levee Plow Disc                  |
| float         | Float                            |
| fldcdscr      | Field conditioner (Scratcher)    |
| listrmid      | Lister (Middle-Buster)           |
| rollgrov      | Roller Groover                   |
| rolpkrat      | Roller Packer Attachment         |
| rolpkrft      | Roller Packer Flat Roller        |
| sandfigt      | Sand-Fighter                     |
| seedroll      | Seedbed Roller                   |
| crustbst      | Crust Buster                     |
| rollhrrw      | Roller Harrow                    |
| triplek       | Triple K                         |
| finharrw      | Finishing Harrow                 |
| flexharw      | Flex-tine Harrow CL              |
| spiketth      | Powered Spike Tooth Harrow       |
| spiktoth      | Spike Tooth Harrow               |
| sprgtoth      | Spring Tooth Harrow              |
| soilfins      | Soil Finisher                    |
| rothoe        | Rotary Hoe                       |
| roterra       | Roterra                          |
| rototill      | Roto-Tiller                      |
| rotbeddr      | Rotovator-Bedder                 |
| rowbuck       | Rowbuck                          |
| ripper        | Ripper                           |
| midbst1r      | Middle Buster                    |
| rodweedr      | Rod Weeder                       |
| rubwhwpl      | Rubber-Wheel Weed Puller         |
| multiwdr      | Multi-Weeder                     |
| mldboard      | Moldboard Plow                   |
| chisplow      | Chisel Plow                      |
| cchplow       | Coulter-Chisel                   |
| diskplow      | Disk Plow                        |
| stubmlch      | Stubble-Mulch Plow               |
| subchplw      | Subsoil Chisel Plow              |
| rowcond       | Row Conditioner                  |
| hipper        | Hipper                           |
| riceroll      | Rice Roller                      |
| paraplow      | Paraplow                         |
| sbedhipr      | Subsoiler-Bedder Hip-Rip         |
| riprsubs      | Deep Ripper-Subsoiler            |
| vripper       | V-Ripper                         |
| bedrollr      | Bed Roller                       |
| bedderd       | Bedder (Disk)                    |
| beddhipr      | Bedder Disk-Hipper               |
| beddkrow      | Bedder Disk-Row                  |
| bedders       | Bedder Shaper                    |
| dskbrmkr      | Disk Border Maker                |
| dkchmtil      | Disk Chisel (Mulch Tiller)       |
| offsethv      | Offset Disk - Heavy Duty         |
| offsetlt      | Offset Disk - Light Duty         |
| one-wayt      | One-Way (Disk Tiller)            |
| tandempl      | Tandem Disk Plow                 |
| tandemrg      | Tandem Disk Reg                  |
| singldis      | Single Disk                      |
| pwrmulch      | Power Mulcher                    |
| blade10       | Blade 10 ft                      |
| furwdike      | Furrow Diker                     |
| beetcult      | Beet Cultivator                  |
| cltiweed      | Cultiweeder                      |
| packer        | Packer                           |
