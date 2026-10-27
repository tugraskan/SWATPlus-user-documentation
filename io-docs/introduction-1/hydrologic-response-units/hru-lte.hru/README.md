# hru-lte.hru

| Field                         | Description                                                                                   |   Type  |   Unit   |    Default   |    Range   |
| ----------------------------- | --------------------------------------------------------------------------------------------- | :-----: | :------: | :----------: | :--------: |
| [id](id-hru-lte.hru.md)       | ID of the HRU-lte                                                                             | integer |    n/a   |              |            |
| [name](name_hrulte_db.md)     | Name of HRU-lte                                                                               |  string |    n/a   |      n/a     |     n/a    |
| [area](area.md)               | HRU-lte drainage area                                                                         |   real  |   km^2   |      0.0     |            |
| [cn2](cn2.md) | Condition II Curve Number | real | none | 80.0 | 35-98 |
| [cn3\_swf](cn3_swf.md) | Soil water factor for CN3 | real | none | 1.0 | 0.0-1.0 |
| [t\_conc](t_conc.md)          | Time of concentration                                                                         |   real  |    min   |     26.0     |            |
| [soil\_dp](soil_dp.md)        | Soil profile depth                                                                            |   real  |    mm    |    1500.0    |            |
| [perc\_co](perco_co.md) | Soil percolation coefficient | real | none | 0.0 | 0.0-6000.0 |
| [slp](slp.md)                 | Land surface slope                                                                            |   real  |    m/m   |     0.04     |  0.0-0.60  |
| [slp\_len](slp_len.md)        | Land surface slope length                                                                     |   real  |     m    |     64.20    |            |
| [et\_co](et_co.md)            | ET coefficient                                                                                |   real  |   none   |              |            |
| [aqu\_sp\_yld](aqu_sp_yld.md) | Specific yield of the shallow aquifer (currently not used in simulation calculations) | real | none | 0.05 |  |
| [alpha\_bf](alpha_bf.md) | Baseflow alpha factor | real | 1/days | 0.05 |  |
| [revap](revap.md)             | Revap coefficient                                                                             |   real  |   none   |      0.0     |            |
| [rchg\_dp](rchg_dp.md)        | Percolation coefficient from shallow to deep aquifer                                          |   real  |   none   |     0.01     |            |
| [sw\_init](sw_init.md)        | Initial soil water (fraction of available water capacity)                                     |   real  | fraction |     0.50     |   0.0-1.0  |
| [aqu\_init](aqu_init.md) | Initial shallow aquifer storage (currently not used in simulation calculations) | real | mm | 3.00 |  |
| [aqu\_sh\_flo](aqu_sh_flo.md) | Initial shallow aquifer flow (currently not used in simulation calculations) | real | mm | 0.0 |  |
| [aqu\_dp\_flo](aqu_dp_flo.md) | Initial deep aquifer flow (currently not used in simulation calculations) | real | mm | 300.0 |  |
| [snow\_h2o](snow_h2o.md) | Initial snow water equivalent (currently not used in simulation calculations) | real | mm | 0.0 |  |
| [lat](lat.md) | Latitude | real | dec degrees | 31.60 |  |
| [soil\_text](soil_text.md)    | Soil texture                                                                                  |  string |    n/a   |      n/a     |     n/a    |
| [trop\_flag](trop_flag.md) | Tropical flag (currently not used in simulation calculations) | string | n/a | non\_trop | n/a |
| [grow\_start](grow_start.md)  | Start of growing season for non-tropical/start of monsoon initialization period for tropical  |  string |    n/a   |      n/a     |     n/a    |
| [grow\_end](grow_end.md) | End of growing season for non-tropical/end of monsoon initialization period for tropical | string | n/a | n/a | n/a |
| [plnt\_typ](plnt_typ.md)      | Plant type                                                                                    |  string |    n/a   |     agrl     |     n/a    |
| [stress](stress.md)           | Plant stress                                                                                  |   real  | fraction |       1      |   0.0-1.0  |
| [pet\_flag](pet_flag.md)      | Potential ET method                                                                           |  string |    n/a   |     harg     |     n/a    |
| [irr\_flag](irr_flag.md)      | Irrigation code                                                                               |  string |    n/a   |    no\_irr   |     n/a    |
| [irr\_src](irr_src.md)        | Irrigation source                                                                             |  string |    n/a   | outside\_bsn |     n/a    |
| [t\_drain](t_drain.md)        | Design subsurface tile drain time                                                             |   real  |    hr    |      0.0     |            |
| [usle\_k](usle_k.md)          | USLE soil erodibility factor K                                                                |   real  |    n/a   |     0.32     |            |
| [usle\_c](usle_c.md)          | USLE cover factor C                                                                           |   real  |    n/a   |     0.20     |            |
| [usle\_p](usle_p.md)          | USLE support practice factor P                                                                |   real  |    n/a   |     0.80     |            |
| [usle\_ls](usle_ls.md)        | USLE slope length and slope factor LS                                                         |   real  |    n/a   |     0.53     |            |
