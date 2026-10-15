# CLIMBER-3α present-day and LGM climatologies (Montoya and Levermann, 2008)

Climatologies of the present-day and Last Glacial Maximum (LGM, 21 ka) simulations of
the Earth system model of intermediate complexity CLIMBER-3α, as used in:

Montoya, M. and Levermann, A.: Surface wind-stress threshold for glacial Atlantic
overturning, Geophys. Res. Lett., 35, L03608, 2008,
[doi:10.1029/2007GL032560](https://doi.org/10.1029/2007GL032560).

The model is described in:

Montoya, M., Griesel, A., Levermann, A., Mignot, J., Hofmann, M., Ganopolski, A., and
Rahmstorf, S.: The earth system model of intermediate complexity CLIMBER-3α. Part I:
description and performance for present-day conditions, Clim. Dyn., 25, 237-263, 2005,
[doi:10.1007/s00382-005-0044-1](https://doi.org/10.1007/s00382-005-0044-1).

Please cite both papers when using these data.

## Simulations

| Name | Simulation | Years averaged (atmosphere; ocean) |
|---|---|---|
| `present` | Present-day control | model year 13651 (from restart `c3beta_pw`); ocean snapshot 13652 |
| `lgm_1p7weak` | LGM, surface wind stress over the ocean scaled by 1.7: weak Atlantic overturning state (deep water formed south of Greenland) | 4701-4800 (`c3beta_clme_trenbx1p7_vd03_21k`); ocean 14 Aug 4798 - 9 Aug 4799 |
| `lgm_1p7strong` | LGM, the same wind-stress factor 1.7, continued from a run with factor 1.75 (from the run name): strong Atlantic overturning state (deep water formed north of the Greenland-Scotland ridge) | 7886-7985 (`c3b_deep_indo_trenbx1p75-1p7_vd03_21k`); ocean 28 Aug 7992 - 23 Aug 7993 |

At a wind-stress factor of 1.7 the glacial overturning is bistable: the weak and strong
states are the two equilibria of Montoya and Levermann (2008).

## Files

All files were written with FERRET (June-July 2009) by M. Montoya. The `.dat` files are
FERRET text listings of the same fields as the `.cdf` file of the same name.

### `atmosphere/` (POTSDAM-2 atmosphere grid)

16 x 24 cells of 22.5° longitude x 7.5° latitude, centres at 11.25-348.75°E and
86.25°S-86.25°N (`XT_I`, `YT_J`).

| File | Variables |
|---|---|
| `present.cdf`, `lgm_1p7weak.cdf`, `lgm_1p7strong.cdf` | `TS_ANN`: surface air temperature, annual mean (degC); `TS_JJA`: surface air temperature, June-August mean (degC); `PRC_ANN`: precipitation, annual mean (mm/day) |
| `horo.cdf` | `HORO_PRESENT`, `HORO_LGM`: surface height of the atmosphere model (m), present day and LGM (the same for both LGM states). 0 over the ocean and at least 1 over land. |

There are no monthly fields.

### `ocean/` (MOM-3 ocean grid)

96 x 48 cells of 3.75° x 3.75° (`XT_I`, `YT_J`), 24 depth levels from 12.5 to 5242.5 m
(`ZT_K`, with bounds `ZT_K_bnds`).

| File | Variables |
|---|---|
| `lgm_present_ocean.cdf` (present day, despite its name), `lgm_1p7weak_ocean.cdf`, `lgm_1p7strong_ocean.cdf` | `TEMP`: potential temperature, annual mean (degC); missing below the sea floor and over land |

## Provenance

The files were provided by Marisa Montoya (Universidad Complutense de Madrid) to Alexander
Robinson, and were kept in the archive of the Potsdam Institute for Climate
Impact Research (PIK), `/data/sicopolis/data/CLIMBER3a/` (atmosphere files in
`brutos/`, ocean files in `ocean_marisa/`). They are copied here unchanged. The files
derived from them in that archive (interpolations to other grids) are not included.

SHA-256 checksums are in `SHA256SUMS`.

## Licence

[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) (see `LICENSE`).

## Used in

[FesmData](https://github.com/fesmc/FesmData) (source `Montoya2008_climber3a`), which
remaps these fields onto ice-sheet model grids.
