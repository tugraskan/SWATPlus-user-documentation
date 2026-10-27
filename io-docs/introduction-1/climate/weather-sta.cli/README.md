---
description: This file lists the weather stations defined for a SWAT+ setup.
---

# weather-sta.cli

<table><thead><tr><th>Field</th><th width="292">Description</th><th width="150">Type</th></tr></thead><tbody><tr><td><a href="name-weather_sta.cli.md">name</a></td><td>Name of the weather station</td><td>string</td></tr><tr><td><a href="wgn.md">wgn</a></td><td>Name of the weather generator station</td><td>string</td></tr><tr><td><a href="pcp.md">pcp</a><sup>*</sup></td><td>Name of the precipitation station</td><td>string</td></tr><tr><td><a href="tmp.md">tmp</a><sup>*</sup></td><td>Name of the temperature station</td><td>string</td></tr><tr><td><a href="slr.md">slr</a><sup>*</sup></td><td>Name of the solar radiation station</td><td>string</td></tr><tr><td><a href="hmd.md">hmd</a><sup>*</sup></td><td>Name of the relative humidity station</td><td>string</td></tr><tr><td><a href="wnd.md">wnd</a><sup>*</sup></td><td>Name of the wind speed station</td><td>string</td></tr><tr><td><a href="pet.md">pet</a><sup>*</sup></td><td>Name of the PET station</td><td>string</td></tr><tr><td><a href="atmo_dep.md">atmo_dep</a><sup>*</sup></td><td>Name of the atmospheric deposition station</td><td>string</td></tr></tbody></table>

\* Input-file labels marked with an asterisk have different Fortran names: `pcp` → `wst(i)%wco_c%pgage`; `tmp` → `wst(i)%wco_c%tgage`; `slr` → `wst(i)%wco_c%sgage`; `hmd` → `wst(i)%wco_c%hgage`; `wnd` → `wst(i)%wco_c%wgage`; `pet` → `wst(i)%wco_c%petgage`; `atmo_dep` → `wst(i)%wco_c%atmodep`. [Reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/cli_staread.f90#L68).
