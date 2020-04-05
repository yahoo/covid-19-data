# Yahoo Knowledge Graph COVID-19 Datasets

## Background

The Yahoo Knowledge Graph team at Verizon Media is responsible for providing critical COVID-19 data that feeds into Yahoo properties like Yahoo News, Yahoo Finance, and Yahoo Weather. In the spirit of open source, the team is releasing a subset of COVID-19 data, an API, and a dashboard that includes country, state, and county level information to the public. 

The current offering includes:
* A [public API](https://github.com/yahoo/covid-19-api/) (commercial use upon request)
* Hourly dataset updates with history 
* Open datasets (commercial use upon request)
* Open source [dashboard to explore data](https://github.com/yahoo/covid-19-dashboard/)
* Data from public sources

## API

This project doesn't have an API. This is a placeholder in case you need it for your project. If you don't need it, delete this section and the reference to it in the [table of contents](#table-of-contents).

## Dashboard

This project doesn't have an API. This is a placeholder in case you need it for your project. If you don't need it, delete this section and the reference to it in the [table of contents](#table-of-contents).

## Datasets

The collected data is split into 2 datasets - region information and daily case counts, detailed below.

The schema of the data reflect current available information.
As the covid-19 pandemic develops and local governments and agencies improve in their
ability to collect and present their data to the public, so will the schema evolve to reflect that.

Please check back often as more information is constantly being collected.

### region-info
Provides general information about the regions covered in the dataset, such as geographical location and links to other public data sources.

| Field               | Type        | Description |
|---------------------|-------------|-------------|
| id                  | xsd:string  | a unique identifier for the region |
| type                | xsd:string  | the region type, for example: Country, StateAdminArea, CityTown, etc... |
| woeId               | xsd:string  | WhereOnEarth unique identifier for the region |
| wikiId              | xsd:string  | the main wikiepdia page name of the country, can be used as a unique key |
| label               | xsd:string  | the english name of the region |
| latitude            | xsd:float   | latitude in decimal number format |
| longitude           | xsd:float   | longitude in decimal number format |
| population          | xsd:integer | the population residing in the region |
| stateLabel          | xsd:string  | the english name of the state where the region is located (if applicable) |
| stateId             | xsd:string  | the region id of the state if applicable |
| countryLabel        | xsd:string  | the english name of the country where the region is located (if applicable) |
| countryId           | xsd:string  | the region id of the country if applicable |

### region-daily
Provides detailed case counts of covid-19 per region.
Each entry (row) in the daily file represents a single region.

We retain historical daily counts to help facilitate understanding and tracking of the pandemic.

In order to provide the most accurate and up-to-date data, we also publish the current daily case counts.
The current daily counts are continuously updated as more information is collected and processed by our platform,
when reading the current daily counts take notice that the case counts for specific regions may change throughout the day.

| Field               | Type        | Description |
|---------------------|-------------|-------------|
| regionId            | xsd:string  | see _id_ above |
| regionType          | xsd:string  | see above |
| stateId             | xsd:string  |           |
| countryId           | xsd:string  |           |
| label               | xsd:string  |           |
| totalConfirmed      | xsd:integer | the total amount of confirmed cases of covid-19 in the region until the given date (aggregate) |
| totalDeaths         | xsd:integer | the total amount of fatalities from covid-19 in the region |
| totalRecoveredCases | xsd:integer | the total amount of people recovered from covid-19 in the region (aggregate) |
| totalTestedCases    | xsd:integer | the total amount of people tested for covid-19 in the region (aggregate) |
| numActiveCases      | xsd:integer | the current count of confirmed covid-19 cases in the region which have yet to recover or otherwise |
| numDeaths           | xsd:integer | the daily count of fatalities as a result of covid-19 |
| numPendingTests     | xsd:integer | the current count of people waiting to be tested for covid-19 |
| numRecoveredCases   | xsd:integer | the daily count of recovered cases |
| numTested           | xsd:integer | the daily count of people tested for covid-19 |
| collectedDate       | xsd:datetime| last update time of the entry |

## Maintainers

+ Amit 
+ Asaf
+ Cindy

Please contact yk-covid-19-os@verizonmedia.com with any questions.

## License

The Yahoo Covid-19 Dataset is made available under a Creative Commons CC-BY-NC 4.0 license.  No express permission from Verizon Media is required for noncommercial uses.  Only compliance with the CC-BY-NC 4.0 license is required for noncommercial uses.

You can find a copy of the license here https://creativecommons.org/licenses/by-nc/4.0/legalcode.  Some additional details about what noncommercial use means are available here https://wiki.creativecommons.org/wiki/NonCommercial_interpretation.

Verizon Media is also offering royalty-free commercial licenses upon request.  If you are interested in using the Yahoo Covid-19 Dataset for a commercial use, [please submit a request](https://docs.google.com/forms/d/e/1FAIpQLSdINfXR6S0ZmOGSvdvg4WUKzhqvDxltLoa4q4btQ4gkJokTPw/viewform).
