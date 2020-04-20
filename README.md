# Yahoo Knowledge Graph COVID-19 Datasets

## Background

The Yahoo Knowledge Graph team at Verizon Media is responsible for providing critical COVID-19 data that feeds into Yahoo properties like Yahoo News, Yahoo Finance, and Yahoo Weather. The team is releasing COVID-19 data, an API, and a dashboard that includes country, state, and county level information to the public.

The current offering includes:

* A [public API](https://github.com/yahoo/covid-19-api/) powered by [Elide](https://elide.io/)
* Hourly dataset updates from [public sources](https://github.com/yahoo/covid-19-data/blob/master/data-sources.md)
* Open datasets ([commercial use upon request](https://docs.google.com/forms/d/e/1FAIpQLSdINfXR6S0ZmOGSvdvg4WUKzhqvDxltLoa4q4btQ4gkJokTPw/viewform]))
* Open source [dashboard to explore data](https://yahoo.github.io/covid-19-dashboard)

## Datasets

The data is split into two sets - regional information and daily case counts. The schema of the data reflects current available information. As the COVID-19 pandemic develops and local governments and agencies improve their ability to collect and present their data to the public, the schema will evolve. 

Please check back frequently as more information will be constantly added.

We welcome data feeds or links to web pages that you would like us to crawl, extract, and merge into the overall stats. Feel free to [submit an issue](https://github.com/yahoo/covid-19-data/issues/new).

### region-metadata

Provides general information about the regions covered in the dataset, such as geographical location and links to other public data sources.

| Field               | Type        | Description |
|---------------------|-------------|-------------|
| id                  | xsd:string  | a unique identifier for the region |
| type                | list of xsd:string | a list of type classifications for the region. for example: Country, StateAdminArea, CountyAdminArea, etc... |
| woeId               | xsd:string  | WhereOnEarth unique identifier for the region |
| wikiId              | xsd:string  | the main Wikipedia page name of the country, can be used as a unique key |
| label               | xsd:string  | the English name of the region |
| latitude            | xsd:float   | latitude in decimal number format |
| longitude           | xsd:float   | longitude in decimal number format |
| population          | xsd:integer | the population residing in the region |
| stateLabel          | xsd:string  | the English name of the state where the region is located (if applicable) |
| stateId             | xsd:string  | the region id of the state if applicable |
| countryLabel        | xsd:string  | the English name of the country where the region is located (if applicable) |
| countryId           | xsd:string  | the region id of the country if applicable |

### region-daily

Provides detailed case counts of COVID-19 per region. Each entry (row) in the daily file represents a single region.

We retain historical daily counts to help facilitate understanding and tracking of the pandemic.

In order to provide the most accurate and up-to-date data, we also publish the current daily case counts. The current daily counts are continuously updated as more information is collected and processed by our platform,
when reading the current daily counts take notice that the case counts for specific regions may change throughout the day.

| Field               | Type        | Description |
|---------------------|-------------|-------------|
| regionId            | xsd:string  | see _id_ above |
| label               | xsd:string  | see above      |
| totalConfirmed      | xsd:integer | the total amount of confirmed cases of COVID-19 in the region until the given date (aggregate) |
| totalDeaths         | xsd:integer | the total amount of fatalities from COVID-19 in the region |
| totalRecoveredCases | xsd:integer | the total amount of people recovered from COVID-19 in the region (aggregate) |
| totalTestedCases    | xsd:integer | the total amount of people tested for COVID-19 in the region (aggregate) |
| numActiveCases      | xsd:integer | the current count of confirmed COVID-19 cases in the region which have yet to recover or otherwise |
| numDeaths           | xsd:integer | the daily count of fatalities as a result of COVID-19 |
| numRecoveredCases   | xsd:integer | the daily count of recovered cases |
| numTests            | xsd:integer | the daily count of people tested for COVID-19 |
| referenceDate       | xsd:date    | the date associated with the COVID-19 data according to the **local** timezone of the region |
| lastUpdatedDate     | xsd:datetime| last update time of the entry |
| dataSource          | xsd:anyURI  | the source attribution for the COVID-19 data in the current entry |

### region-latest

Provides the latest known figures for each region.

The schema for the latest file is the same as the region-daily above.
The main difference is in _referenceDate_: for the daily files, _referenceDate_ will always match the filename.
In the latest file, _referenceDate_ will be dependant on the last extraction date and the local timezone of the region.

## Maintainers

* [Amit Nagpal](https://www.linkedin.com/in/amitnagpal09/)
* [Asaf Ary](https://www.linkedin.com/in/asafary/)
* [Cindy Wang](https://www.linkedin.com/in/cindy-wang-365233/)

Please contact yk-covid-19-os@verizonmedia.com with any questions.

## License

The Yahoo Knowledge Graph COVID-19 Dataset is made available under a [Creative Commons CC-BY-NC 4.0 license](https://creativecommons.org/licenses/by-nc/4.0/legalcode).  No express permission from Verizon Media is required for noncommercial uses.  Only compliance with the CC-BY-NC 4.0 license is required for [noncommercial uses](https://wiki.creativecommons.org/wiki/NonCommercial_interpretation) including attribution.

Verizon Media may consider granting royalty-free commercial licenses upon request.  If you are interested in making commercial use of the Yahoo COVID-19 Dataset, [please submit a request](https://docs.google.com/forms/d/e/1FAIpQLSdINfXR6S0ZmOGSvdvg4WUKzhqvDxltLoa4q4btQ4gkJokTPw/viewform).
