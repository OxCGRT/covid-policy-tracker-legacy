# covid-policy-tracker-legacy
Data in legacy format from the OxCGRT, a systematic dataset of Covid-19 policy from Oxford University

# Oxford Covid-19 Government Response Tracker (OxCGRT)

The Oxford Covid-19 Government Response Tracker (OxCGRT) collects systematic information on which governments have taken which measures, and when. This can help decision-makers and citizens understand governmental responses in a consistent way, aiding efforts to fight the pandemic. The OxCGRT systematically collects information on several different common policy responses governments have taken, records these policies on a scale to reflect the extent of government action, and aggregates these scores into a suite of policy indices.

This is a project from the [Blavatnik School of Government](www.bsg.ox.ac.uk). More information on the OxCGRT is available on the school's website: https://www.bsg.ox.ac.uk/covidtracker. This README contains information about using the database.

In this document, we outline our Legacy Repository. It contains two main data structures:

- [Legacy OxCGRT dataset - 25 April 2020](#legacy-oxcgrt-dataset-2020)
- [Legacy OxCGRT dataset - 27 July 2022](#legacy-oxcgrt-dataset-2022)

## Legacy OxCGRT dataset 2020
*Last updated 25 April 2020

The OxCGRT implemented a new data structure on 28 April 2020. All existing indicators were renamed, many were recoded, and several new indicators were added.

This folder contains the legacy data that was in place before the data migration started on 25 April 2020. The files here have the 13 "S" indicators that the OxCGRT used in March and April. 

- [OxCGRT_20200425 LEGACY](OxCGRT_20200425%20LEGACY.csv) is the full dataset, as at 25 April 2020, without notes.
- [OxCGRT_20200425_withnotes LEGACY](OxCGRT_20200425_withnotes%20LEGACY.csv) is the same dataset but with a notes column for each indicator.
- the [/timeseries](timeseries/) folder contains the same data but in .xlsx and .csv timeseries format.

This old data structure is described in v4 of our [working paper](BSG-WP-2020-032-v4), also archived in this folder.

Please note that this archived dataset from 25 April 2020 is patchy towards the end (mid-April onwards) as we diverted more resources towards the migration to the new data structure, rather than keeping the old database perfectly up to date.


## Legacy OxCGRT dataset 2022
*Created 27 July 2022, updated daily

### The database

OxCGRT collects publicly available information on 21 indicators of government response. This information is collected by a team of over 200 volunteers from the Oxford community and is updated continuously.

We also include statistics on the number of reported Covid-19 cases and deaths in each country. These are taken from the [JHU CSSE data repository](https://github.com/CSSEGISandData/COVID-19) for all countries and the US States. 

### Individual policy measures

Full descriptions of the policy indicators and their meaning can be found in our [codebook](https://github.com/OxCGRT/covid-policy-tracker/blob/master/documentation/codebook.md). For more detailed guidance about the codebook and how we interpret the indicators, see the [coding interpretation guide](https://github.com/OxCGRT/covid-policy-tracker/blob/master/documentation/interpretation_guide.md). This ensures consistency, and standardizes coding across the database.

Eight of the policy indicators (C1-C8) record information on `Containment and closure policies`, such as school closures and restrictions in movement. Four of the indicators (E1-E4) record `Economic policies` such as income support to citizens or provision of foreign aid. Eight indicators (H1-H8) record `Health system policies` such as the Covid-19 testing regime or emergency investments into healthcare. Three indicators (V1-V4) record `Vaccination policies`; a country/region/territory’s priority list, eligible groups, and the individual cost of vaccination.

Finally, we have a `Miscellaneous indicator (M1)` for notes that do not fit elsewhere.

### Policy indices

To help make sense of the data, we have produced four indices that aggregate the data into a single number. Each of these indices report a number between 0 to 100 that reflects the level of the governments response along certain dimensions. This is a measure of how many of the relevant indicators a government has acted upon, and to what degree. The index cannot say whether a government's policy has been implemented effectively.

- overall government response index (all indicators)
- containment and health index (all C and H indicators)
- stringency index (all C indicators, plus H1 which records public information campaigns)
- economic support index (all E indicators)

(_Note: these only include indicators recorded on ordinal scales, so they all exclude E3, E4, H4, H5, and M1._)

The [index methodology](https://github.com/OxCGRT/covid-policy-tracker/blob/master/documentation/index_methodology.md) explains how the different indices are calculated and how they are reported for days with incomplete data. This also describes the methodology for the `legacy stringency index` which is based on the old database structure in place prior to 25 April 2020 reported above in this document.

### Subnational data

In addition to country-level data, our primary dataset additionally includes some subnational data. We have incorporated data for US states, Brazilian States, Indian States, UK devolved nations, Canadian provinces and territories, and Chinese provinces into the primary dataset on this covid-policy-tracker repository.

Subnational data can be interpreted using the main [codebook](https://github.com/OxCGRT/covid-policy-tracker/blob/master/documentation/codebook.md), with additional guidance on subnational-specific interpretation available in the [documentation folder](https://github.com/OxCGRT/covid-policy-tracker/blob/master/documentation/subnational_interpretation.md). The state data included in our primary dataset aims to describe the overall policy environment that applies to residents of the state or equivalent jurisdiction, and so includes policies set by the national government where those values are more stringent than state-level action.

### Using OxCGRT data

The OxCGRT is updated continuously in real time. There are numerous ways you can access the raw data.

The [/legacy_data_202207](legacy_data_202207/) folder in this repo contains recent exports from the OxCGRT database. You are welcome to build applications that draw directly from this repository.
- The CSV file `OxCGRT_latest.csv` reports country/territory- and state-level data presented in "country/territory-day" format (or "state-day" as the case may be), with a list of all indicators for each country/territory as a single row each day. This CSV is updated every hour from the main database, and the badge above shows whether this data link is functioning correctly.
- The CSV file `OxCGRT_latest_combined.csv` reports country/territory- and state-level data in "country/territory-day" format, but gives a single "combined" value for each indicator. As described in the [codebook](documentation/codebook.md), many of our indicators are recorded across two variables: one that records the _strictness_ of the policy, and one that records its _scope_.
  - This is reported as a combination of the policy level (a number) and the scope flag (a letter: `T` for targetted policies or `G` for general policie; or `F`/`A` flags for indicator E1). For instance, for `C3_Cancel public events` we would have `0`, `1T` (recommend cancelling in some areas), `1G` (recommend cancelling everywhere), `2T` (require cancelling in some areas), `2G` (require cancelling everywhere).
  - We also include a numerical combination, using the same methodology to calculate compenents for our indices: a targeted policy is considered a half-step lower than a general jurisdiction-wide policy. For instance, for `C3_Cancel public events` we would have `0`, `0.5` (recommend cancelling in some areas), `1` (recommend cancelling everywhere), `1.5` (require cancelling in some areas), `2` (require cancelling everywhere).
- The CSV files `OxCGRT_withnotes_2020.csv`, `OxCGRT_withnotes_2021.csv`, and `OxCGRT_withnotes_2022.csv` report country/territory- and state-level data in "country/territory-day" format _with_ a column of notes from our data collectors for each indicator. This is also updated every hour from the main database. Please note that some of the comments contain commas and other characters interpreted as a delimiter, and so may cause problems when parsing this CSV file.
- The CSV file `OxCGRT_latest_allchanges.csv` reports country/territory-level data with a list of every _change_ to the database. Every time a policy value changes, or every time a note is added to an indicator, it is represented with it's own new row. (This does not include subnational data.)
- The CSV file `OxCGRT_vaccines_full.csv` reports country/region/territory data presented in "country/region/territory-day" format, for the three summary vaccine indicators (V1, V2, V3) and 50 subcategories for eligible groups for vaccination for each country/region/territory as a single row each day.





