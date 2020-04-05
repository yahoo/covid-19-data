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

The collected data is split into 2 dataset
For a detailed description of contents of each file, see the [schema](schema) section.

### region-info
Provides general information about the regions covered in the dataset, such as geographical location and links to other public data sources

### region-daily
Provides detailed case counts of covid-19 per region.
Each entry (row) in the daily file represents a single region.

We retain historical daily counts to help facilitate understanding and tracking of the pandemic.

In order to provide the most accurate and up-to-date data, we also publish the current daily case counts.
The current daily counts are continuously updated as more information is collected and processed by our platform,
when reading the current daily counts take notice that the case counts for specific regions may change throughout the day.

## Maintainers

+ Amit 
+ Asaf
+ Cindy

Please contact yk-covid-19-os@verizonmedia.com with any questions.

## License

The Yahoo Covid-19 Dataset is made available under a Creative Commons CC-BY-NC 4.0 license.  No express permission from Verizon Media is required for noncommercial uses.  Only compliance with the CC-BY-NC 4.0 license is required for noncommercial uses.

You can find a copy of the license here https://creativecommons.org/licenses/by-nc/4.0/legalcode.  Some additional details about what noncommercial use means are available here https://wiki.creativecommons.org/wiki/NonCommercial_interpretation.

Verizon Media is also offering royalty-free commercial licenses upon request.  If you are interested in using the Yahoo Covid-19 Dataset for a commercial use, [please submit a request](https://docs.google.com/forms/d/e/1FAIpQLSdINfXR6S0ZmOGSvdvg4WUKzhqvDxltLoa4q4btQ4gkJokTPw/viewform).
