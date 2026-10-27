---
description: Septic system type
---

# typ

**Code reference:** `sep(isep)%typ`

**Declared type:** `septic_system` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/sep_read.f90#L43), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/septic_data_module.f90#L22)).

Enter the 1-based row number of the septic water-quality record in `septic.sep`. For example, `1` selects the first data record. SWAT+ main (6f515368) uses this integer directly as an array index; it does not match the value to the record's `name` field. The names below describe the standard database records, whose row order determines their integer numbers.

| Name | Description                                                               |
| ---- | ------------------------------------------------------------------------- |
| GCON | Generic type conventional system                                          |
| GADV | Generic type advanced system                                              |
| COND | Septic tank with conventional drainfield                                  |
| SAS1 | Septic tank with sand absorption system 1                                 |
| SAS2 | Septic tank with sand absorption system 2                                 |
| SAS3 | Septic tank with in-tank N removal and sand absorption system             |
| SAS4 | Septic tank with effluent N removal recycle                               |
| SAS5 | Septic tank with corrugated plastic trickling filter                      |
| SAS6 | Septic tank with open-cell form trickling filter                          |
| SPF1 | Single pass sand filter 1                                                 |
| SPF2 | Single pass sand filter 2                                                 |
| SPF3 | Single pass sand filter 3                                                 |
| SPF4 | Single pass sand filter 4                                                 |
| RCF1 | At grade recirculating sand filter                                        |
| RCF2 | Maryland style recirculating sand filter                                  |
| RCF3 | Recirculating sand filter                                                 |
| CWT1 | Septic tank w/ constructed wetland and surface water discharge            |
| CWT2 | Municipal wastewater w/ constructed wetland and surface water discharge 1 |
| CWT3 | Municipal wastewater w/ constructed wetland and surface water discharge 2 |
| CWT4 | Municipal wastewater w/ constructed wetland                               |
| CWT5 | Municipal wastewater w/ lagoon and constructed wetland                    |
| BFL1 | Waterloo biofilter (plastic media) 1                                      |
| BFL2 | Waterloo biofilter (plastic media) 2                                      |
| BFL3 | Peat biofilter                                                            |
| TXF1 | Recirculating textile filter                                              |
| TXF2 | Foam or textile filter effluent                                           |
| GFL1 | Septic, recirculating gravel filter, UV disinfection                      |
| USPT | Untreated Effluent - Texas A\&M reference                                 |
