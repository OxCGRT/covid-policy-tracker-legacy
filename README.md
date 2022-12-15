| **End of OxCGRT data collection, December 2022** |
| --- |
| The Oxford COVID-19 Government Response Tracker will stop publishing real-time updates for most jurisdictions at the end of 2022. Reviewing and confirming data will continue into 2023. Most governments around the world have settled into a steady state of pandemic-related policy – there are not many significant changes for us to report. </br></br>At this stage, we are planning to continue publishing data for individual Chinese provinces into 2023, as there is still significant policy variation and change. We will publish a separate repository for this soon. </br></br>We have posted a longer update on the [Blavatnik School of Government website](https://www.bsg.ox.ac.uk/future-oxford-covid-19-government-response-tracker). The OxCGRT dataset will continue to be available, primarily on this GitHub repository, and we will establish a lasting internet presence over the course of 2023. Our main channel for updates will be our data users mailing list, which you can join here: http://eepurl.com/hiMsdL |

# Oxford Covid-19 Government Response Tracker (OxCGRT) legacy repository

The Oxford Covid-19 Government Response Tracker (OxCGRT) collects systematic information on which governments have taken which measures, and when. This can help decision-makers and citizens understand governmental responses in a consistent way, aiding efforts to fight the pandemic. This repository contains data in legacy (depricated) formats – our most current data and data formats can be found on our main [OxCGRT/covid-policy-tracker](https://github.com/OxCGRT/covid-policy-tracker) repository.

The OxCGRT systematically collects information on several different common policy responses governments have taken, records these policies on a scale to reflect the extent of government action, and aggregates these scores into a suite of policy indices. This is a project from the [Blavatnik School of Government](www.bsg.ox.ac.uk). More information on the OxCGRT is available on the school's website: https://www.bsg.ox.ac.uk/covidtracker.

In this document, we outline our Legacy Repository, which is our archive of two now-outdated data structures which were retired in April 2020 and July 2022.

## Legacy OxCGRT dataset (retired *April 2020*)
*Last updated 25 April 2020*

The OxCGRT implemented a new data structure on 28 April 2020. All existing indicators were renamed, many were recoded, and several new indicators were added.

The [/legacy_data_20200425](/legacy_data_20200425) folder contains the legacy data that was in place before the data migration started on 25 April 2020. The files here have the 13 "S" indicators that the OxCGRT used in March and April. The folder contains the following data files:

- [OxCGRT_20200425 LEGACY](/legacy_data_20200425/OxCGRT_20200425%20LEGACY.csv) is the full dataset, as at 25 April 2020, without notes.
- [OxCGRT_20200425_withnotes LEGACY](/legacy_data_20200425/OxCGRT_20200425_withnotes%20LEGACY.csv) is the same dataset but with a notes column for each indicator.
- the [/timeseries](/legacy_data_20200425/timeseries) folder contains the same data but in .xlsx and .csv timeseries format.

This old data structure is described in v4 of our [working paper](/legacy_data_20200425/BSG-WP-2020-032-v4.pdf), also archived in this folder.

Please note that this archived dataset from 25 April 2020 is patchy towards the end (mid-April onwards) as we diverted more resources towards the migration to the new data structure, rather than keeping the old database perfectly up to date.

The [index methodology](https://github.com/OxCGRT/covid-policy-tracker/blob/master/documentation/index_methodology.md) on our main repository also describes the methodology for the `legacy stringency index` which is based on the old database structure in place prior to 25 April 2020.


## Legacy OxCGRT dataset (retired *July 2022*)
*still updated daily*

### Difference from our current [covid-policy-tracker](https://github.com/OxCGRT/covid-policy-tracker/tree/master/documentation) respository

On 27 July 2022 the OxCGRT implemented data changes which incorporate different policies applying to vaccinated and non-vaccinated people. This results in breaking changes to the csv files published in our main [covid-policy-tracker](https://github.com/OxCGRT/covid-policy-tracker/tree/master/documentation) respository, and the addition of new csv files.

In short: for 10 of our indicators (C1-C8, H6 and H8) our new data structure records which policies apply to everyone in a jurisdiction, which policies apply to non-vaccinated people, and which policies apply to vaccinated people. This creates multiple versions of each policy indicator, which necessitated a new and expanded data structure. More information about these "differentiated policies" is provided in the [codebook in our main repository](https://github.com/OxCGRT/covid-policy-tracker/blob/master/documentation/codebook.md).


### The database

OxCGRT collects publicly available information on 21 indicators of government response. The policies in this legacy dataset are the defined in the same way as the policies in our current main dataset, and the [documentation on our main repository](https://github.com/OxCGRT/covid-policy-tracker/tree/master/documentation) provides information on how to interpret these policies.

Full descriptions of the policy indicators and their meaning can be found in our [codebook](https://github.com/OxCGRT/covid-policy-tracker/blob/master/documentation/codebook.md). For more detailed guidance about the codebook and how we interpret the indicators, see the [coding interpretation guide](https://github.com/OxCGRT/covid-policy-tracker/blob/master/documentation/interpretation_guide.md). This ensures consistency, and standardizes coding across the database.

We also include statistics on the number of reported Covid-19 cases and deaths in each country. These are taken from the [JHU CSSE data repository](https://github.com/CSSEGISandData/COVID-19) for all countries and the US States. 

### Policy indices

To help make sense of the data, we have produced four indices that aggregate the data into a single number. These are defined and calculated the same way as in our main repository, and the [index methodology](https://github.com/OxCGRT/covid-policy-tracker/blob/master/documentation/index_methodology.md) published there contains more information.

### Subnational data

In addition to country-level data, our primary dataset additionally includes some subnational data. We have incorporated data for US states, Brazilian States, Indian States, UK devolved nations, Canadian provinces and territories, and Chinese provinces into the primary dataset on this covid-policy-tracker repository.

Subnational data can be interpreted using the main [codebook](https://github.com/OxCGRT/covid-policy-tracker/blob/master/documentation/codebook.md), with additional guidance on subnational-specific interpretation available in the [documentation folder](https://github.com/OxCGRT/covid-policy-tracker/blob/master/documentation/subnational_interpretation.md). The state data included in our primary dataset aims to describe the overall policy environment that applies to residents of the state or equivalent jurisdiction, and so includes policies set by the national government where those values are more stringent than state-level action.

### Data files

The data files in the [/legacy_data_202207](/legacy_data_202207) folder continue to be updated in real time from our database. We publish this in a variety of formats, reproducing what used to be published in our main repository until July 2022:

- The CSV file `OxCGRT_latest.csv` reports country/territory- and state-level data presented in "country/territory-day" format (or "state-day" as the case may be), with a list of all indicators for each country/territory as a single row each day. This CSV is updated every hour from the main database, and the badge above shows whether this data link is functioning correctly.
- The CSV file `OxCGRT_latest_combined.csv` reports country/territory- and state-level data in "country/territory-day" format, but gives a single "combined" value for each indicator. As described in the [codebook](documentation/codebook.md), many of our indicators are recorded across two variables: one that records the _strictness_ of the policy, and one that records its _scope_.
  - This is reported as a combination of the policy level (a number) and the scope flag (a letter: `T` for targetted policies or `G` for general policie; or `F`/`A` flags for indicator E1). For instance, for `C3_Cancel public events` we would have `0`, `1T` (recommend cancelling in some areas), `1G` (recommend cancelling everywhere), `2T` (require cancelling in some areas), `2G` (require cancelling everywhere).
  - We also include a numerical combination, using the same methodology to calculate compenents for our indices: a targeted policy is considered a half-step lower than a general jurisdiction-wide policy. For instance, for `C3_Cancel public events` we would have `0`, `0.5` (recommend cancelling in some areas), `1` (recommend cancelling everywhere), `1.5` (require cancelling in some areas), `2` (require cancelling everywhere).
- The CSV files `OxCGRT_withnotes_2020.csv`, `OxCGRT_withnotes_2021.csv`, and `OxCGRT_withnotes_2022.csv` report country/territory- and state-level data in "country/territory-day" format _with_ a column of notes from our data collectors for each indicator. This is also updated every hour from the main database. Please note that some of the comments contain commas and other characters interpreted as a delimiter, and so may cause problems when parsing this CSV file.
- The CSV file `OxCGRT_latest_allchanges.csv` reports country/territory-level data with a list of every _change_ to the database. Every time a policy value changes, or every time a note is added to an indicator, it is represented with it's own new row. (This does not include subnational data.)
- The CSV file `OxCGRT_vaccines_full.csv` reports country/region/territory data presented in "country/region/territory-day" format, for the three summary vaccine indicators (V1, V2, V3) and 50 subcategories for eligible groups for vaccination for each country/region/territory as a single row each day.
