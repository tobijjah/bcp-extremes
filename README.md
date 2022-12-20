# Past and future weather extremes across Europe

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.7463485.svg)](https://doi.org/10.5281/zenodo.7463485)

![Past and future heat waves across Europe](hw.svg)

**Figure 1:** Past and future heat waves across Europe.

This repository contains the annual exceedance index data for past and future weather extremes across Europe on NUTS1
scale.
The code and an accompanying paper analyzing the impact of this weather extremes on the European agricultural sector on
subnational scale will be published during 2023.
We use a percentile-based approach to assess the annual exceedance index of the four weather extremes heat waves
, cold waves, fire-risk and droughts for the past (1981–2020) and future (2006–2100) [**Zhang** et al., 2005].
For the past, we used daily weather records on a grid level (around 11 km at the equator) from the
[ERA5-Land](https://cds.climate.copernicus.eu/cdsapp#!/dataset/reanalysis-era5-land?tab=overview) reanalysis dataset,
and for future projections, we use modelled daily weather records from
[EURO-CORDEX](https://cds.climate.copernicus.eu/cdsapp#!/dataset/projections-cordex-domains-single-levels?tab=overview)
[**Christensen** et al., 2020,**Muñoz**, 2019].
For past and future fire-risk we use precalculated fire weather index data from
[ERA5](https://cds.climate.copernicus.eu/cdsapp#!/dataset/cems-fire-historical?tab=overview) and
[EURO-CORDEX](https://cds.climate.copernicus.eu/cdsapp#!/dataset/sis-tourism-fire-danger-indicators?tab=overview),
respectively
[**Giannakopoulos** et al., 2020].
We used the model average of the following driving GCMs and RCMs for future projections: ICHECs Earth System Model
(EC-Earth), MPI-Ms Earth System Model (MPI-ESM-LR), SMHIs Regional Climate Model (RCA4).
The baseline period for the historical scenario is 1981–2010, and for future projections 1981–2005.
Daily thresholds for heat waves, cold waves, and flash droughts are estimated from the 90th percentile of the daily
minimum and maximum temperature, 10th percentile of the daily minimum and maximum temperature, and 30th percentile of
the soil volumetric water content (0–28cm), respectively [**Sutanto** et al., 2020].
We use a five days centre data window for all three extreme events to estimate the thresholds from the previously listed
baseline periods.
The annual exceedance index for heat waves is calculated as the sum of days, at least for three consecutive days; the
daily temperature values exceed the thresholds for June, July, and August.
For cold waves, the annual exceedance index is the sum of days, at least for three consecutive days; the daily
temperature values are below the thresholds for January, February, October, November, and December.
In-base, exceedance is calculated using bootstrapping (1000x repetitions) for both extreme events.
Heat and cold wave exceedance indices are rescaled to NUTS1 regions using a maximum resampling.
We use sequent peak analysis to detect annual flash droughts, remove minor droughts, and pool interdependent droughts
for the season from June to October [**Biggs** et al., 2004].
The annual exceedance index of droughts is rescaled to NUTS1 regions by using a mean resampling.
Parameters for fire-risk are listed in the table below while.

**Table 1:** Parameters of the percentile-based extremes analysis.

| Type          | Variable      | Percentile | Window | Min duration | Rescaling | Months              | Bootstrapping |
|:--------------|:--------------|-----------:|-------:|-------------:|:----------|:--------------------|:--------------|
| Heat wave     | tmin and tmax |         90 |      5 |            3 | max       | 6, 7, 8             | yes           |
| Cold wave     | tmin and tmax |         10 |      5 |            3 | max       | 1, 2, 10, 11, 12    | yes           |
| Flash drought | swvl 0-28 cm  |         30 |      5 |            5 | mean      | 6, 7, 8, 9, 10      | no            |
| Fire risk     | FWI           |         90 |      5 |            1 | mean      | 3, 4, 5, 6, 7, 8, 9 | yes           |

<div class="figure" style="font-size: 80%">

Xuebin **Zhang**, Gabriele Hegerl, Francis W. Zwiers, and Jesse Kenyon. Avoiding inhomogeneity in percentile-based
indices
of temperature extremes. Journal of Climate, 18 (11):1641–1651, 2005. ISSN 08948755. doi: 10.1175/JCLI3366.1.

Samuel Jonson **Sutanto**, Claudia Vitolo, Claudia Di Napoli, Mirko D’Andrea, and Henny A.J. Van Lanen. Heatwaves,
droughts,
and fires: Exploring compound and cascading dry hazards at the pan-European scale. Environment International, 134
(March 2019):105276, jan 2020. ISSN 01604120. doi: 10.1016/j.envint.2019.105276.

J. Sabater **Muñoz**. ERA5-Land hourly data from 1981 to present. Copernicus Climate Change Service (C3S) Climate Data
Store
(CDS), 2019.

O. B. **Christensen**, W. J. Gutowski, G. Nikulin, and S. Legutke. CORDEX Archive Design, 2020. URL
https://is-enes-data.github.io/cordex_archive_specifications.pdf

Barry J. F. **Biggs**, Bente Clausen, Siegfried Demuth, Miriam Fendeková, Lars Gottschalk, Alan Gustard, Hege Hisdal,
Matthew G. R. Holmes, Ian G. Jowett, Ladislav Kašpárek, Artur Kasprzyk, Elzbieta Kupczyk, Henny A.J. Van Lanen, Henrik
Madsen, Terry J. Marsh, Bjarne Moeslund, Oldřich Novický, Elisabeth Peters, Wojciech Pokojski, Erik P. Querner, Gwyn
Rees, Lars Roald, Kerstin Stahl, Lena M. Tallaksen, and Andrew R. Young. Hydrological Drought: Processes and Estimation
Methods for Stream- flow and Groundwater. Elsevier, 1 edition, 2004. ISBN 0444517677.

**Giannakopoulos**, C., Karali, A., Cauchy, A. (2020): Fire danger indicators for Europe from 1970 to 2098 derived from
climate projections, version 1.0, Copernicus Climate Change Service (C3S) Climate Data Store (CDS),
DOI: 10.24381/cds.ca755de7

</div>

#### Funding

Tobias Seydewitz acknowledges funding from the German Federal Ministry of Education and Research for the
[BIOCLIMAPATHS](https://www.pik-potsdam.de/en/output/projects/all/647) project (grant agreement No 01LS1906A) under the
Axis-ERANET call. The funders had no role in study design, data collection, analysis, decision to publish, or manuscript
preparation.

![Past heat waves across Europe an animation](hw.gif)

**Figure 2:** Past heat waves across Europe, the animation shows the annual exceedance index of heat waves from
1981-2020.
