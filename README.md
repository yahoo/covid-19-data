# Yahoo Knowledge Graph COVID-19 Datasets

## Background

The Yahoo Knowledge Graph team at Verizon Media is responsible for providing critical COVID-19 data that feeds into Yahoo properties like Yahoo News, Yahoo Finance, and Yahoo Weather. The COVID-19 datasets include country, state, and county level information updated on a rolling basis, with updates occuring approximately hourly.

__The COVID-19 datasets are constructed entirely from primary (government and public agency) sources with a clear attribution of the primary sources used for each geographical region.__  While other aggregations of COVID-19 data are already available, we believe ours to be the only open source COVID-19 dataset that is constructed entirely from primary sources with clear attribution back to those sources.  Our hope is that additional transparency will enable more accurate analysis, aiding researchers who seek to understand and prevent further spread of the disease.

Released together with the COVID-19 dataset are two other open source projects:

* An [API](https://github.com/yahoo/covid-19-api/) powered by [Elide](https://elide.io/), which provides JSON-API and GraphQL interfaces to the COVID-19 public data
* A [dashboard to explore the data](https://yahoo.github.io/covid-19-dashboard)


## Datasets

The data is logically organized by region and time. Time is further organized into a snapshot of the latest updates received for all regions and the updates reported by regions for a given date. As the COVID-19 pandemic develops and local governments and agencies improve their ability to collect and present their data to the public, the schema will evolve. Please check back as sources frequently evolve.

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

### by-region-`[DATE]`

Provides detailed case counts of COVID-19 in each region on `[DATE]` in local time for that region. Each entry (row) in the daily file represents a single region. 

Please be aware that different sources release data at different and often unpredictable frequencies. The by-region-`[DATE]` numbers will be updated as sources release data for the given date for their region. In some cases, data for a given region is not released until many days after that calendar date has elapsed everywhere in the world.  As a result, the same by-region-`[DATE]` file may show different aggregate statistics for the same date depending on when the by-region-`[DATE]` is accessed.  Generally speaking, by-region-`[DATE]` data more than one week old is stable.

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

### by-region-latest

Provides the latest figures for each region.  

The schema for the latest file is almost the same as the by-region-`[DATE]` above. The main difference is in _referenceDate_. In the daily files, referenceDate always matches the filename, and represents the date in local time for the relevant data reported by the source for that region when that source was last consulted. In the latest file, referenceDate will differ across regions, representing _the latest date_ on which the source for a given region was consulted.

Note that because different regions report at different and often unpredictable frequencies, the latest figures for one region may be many days older than the latest figures for another region.  For this reason, stable by-region-`[DATE]` numbers are required for an accurate comparison of growth rates in different regions.  Generally speaking, by-region-`[DATE]` data more than one week old is stable.

## Maintainers

* [Amit Nagpal](https://www.linkedin.com/in/amitnagpal09/)
* [Asaf Ary](https://www.linkedin.com/in/asafary/)
* [Cindy Wang](https://www.linkedin.com/in/cindy-wang-365233/)

Please contact yk-covid-19-os@verizonmedia.com with any questions.

## License

The Yahoo Knowledge Graph COVID-19 Dataset is made available under a [Creative Commons CC-BY-NC 4.0 license](https://creativecommons.org/licenses/by-nc/4.0/legalcode).  No express permission from Verizon Media is required for noncommercial uses.  Only compliance with the CC-BY-NC 4.0 license is required for [noncommercial uses](https://wiki.creativecommons.org/wiki/NonCommercial_interpretation) including attribution.

Verizon Media may consider granting royalty-free commercial licenses upon request.  If you are interested in making commercial use of the Yahoo COVID-19 Dataset, [please submit a request](https://docs.google.com/forms/d/e/1FAIpQLSdINfXR6S0ZmOGSvdvg4WUKzhqvDxltLoa4q4btQ4gkJokTPw/viewform).
