# Data Schema
The schema of the data reflect current available information.
As the covid-19 pandemic develops and local governments and agencies improve in their
ability to collect and present their data to the public, so will the schema evolve to reflect that.

Please check back often as more information is constantly being collected.

### Region Metadata
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

### COVID-19 daily case counts per region
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
