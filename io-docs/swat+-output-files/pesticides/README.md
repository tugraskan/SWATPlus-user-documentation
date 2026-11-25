# Pesticides

Pesticide output is written only when pesticides are configured and the corresponding object-level print option is enabled. Daily, monthly, yearly, and average-annual reports use `_day`, `_mon`, `_yr`, and `_aa`; TXT and CSV variants share the same headings. A separate row is written for each pesticide.

## How to produce these files

Configure pesticides in the model. In [print.prt](../../introduction-1/simulation-settings/print.prt/README.md), use the shared `pest` row for all pesticide reports on this page. Its four columns select daily, monthly, yearly, and average-annual output. For example, `pest n y n n` enables the monthly reports. Set `csvout` to `y` to request CSV copies. Data rows depend on the pesticides and relevant objects present in the model. [Print row](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_print_codes_read.f90#L593), [Pesticide file creation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_pest.f90#L17), [Example pesticide writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_pesticide_output.f90#L34)

## File schemas

| File family | Schema |
| --- | --- |
| `hru_pest_*`, `basin_ls_pest_*` | [HRU and landscape pesticide balance](hru-landscape-pesticide-balance.md) |
| `channel_pest_*`, `reservoir_pest_*`, `basin_ch_pest_*`, `basin_res_pest_*` | [Channel and reservoir pesticide balance](channel-reservoir-pesticide-balance.md) |
| `aquifer_pest_*`, `basin_aqu_pest_*` | [Aquifer pesticide balance](aquifer-pesticide-balance.md) |
