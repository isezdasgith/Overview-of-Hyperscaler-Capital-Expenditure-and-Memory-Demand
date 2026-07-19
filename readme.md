# NVIDIA's quarterly revenue by market segment - Data package

This data package contains the data that powers the chart ["NVIDIA's quarterly revenue by market segment"](https://ourworldindata.org/grapher/nvidia-quarterly-revenue-segment?v=1&csvType=full&useColumnShortNames=false) on the Our World in Data website. It was downloaded on July 19, 2026.

### Active Filters

A filtered subset of the full data was downloaded. The following filters were applied:

## CSV Structure

The high level structure of the CSV file is that each row is an observation for an entity (usually a country or region) and a timepoint (usually a year).

The first two columns in the CSV file are "Entity" and "Code". "Entity" is the name of the entity (e.g. "United States"). "Code" is the OWID internal entity code that we use if the entity is a country or region. For most countries, this is the same as the [iso alpha-3](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-3) code of the entity (e.g. "USA") - for non-standard countries like historical countries these are custom codes.

The third column is either "Year" or "Day". If the data is annual, this is "Year" and contains only the year as an integer. If the column is "Day", the column contains a date string in the form "YYYY-MM-DD".

The final column is the data column, which is the time series that powers the chart. If the CSV data is downloaded using the "full data" option, then the column corresponds to the time series below. If the CSV data is downloaded using the "only selected data visible in the chart" option then the data column is transformed depending on the chart type and thus the association with the time series might not be as straightforward.


## Metadata.json structure

The .metadata.json file contains metadata about the data package. The "charts" key contains information to recreate the chart, like the title, subtitle etc.. The "columns" key contains information about each of the columns in the csv, like the unit, timespan covered, citation for the data etc..

## About the data

Our World in Data is almost never the original producer of the data - almost all of the data we use has been compiled by others. If you want to re-use data, it is your responsibility to ensure that you adhere to the sources' license and to credit them correctly. Please note that a single time series may have more than one source - e.g. when we stich together data from different time periods by different producers or when we calculate per capita metrics using population data from a second source.

## Detailed information about the data


## NVIDIA's quarterly revenue by market segment – NVIDIA
Quarterly revenue of NVIDIA Corporation across its main market segments, reported in US dollars. NVIDIA designs graphics processing units (GPUs), originally built for gaming and now also widely used to train and run AI models. This data is not adjusted for inflation.
Last updated: June 8, 2026  
Next update: September 2026  
Unit: US dollars  


### How to cite this data

#### In-line citation
If you have limited space (e.g. in data visualizations), you can use this abbreviated in-line citation:  
NVIDIA Corporation (2026) – with major processing by Our World in Data

#### Full citation
NVIDIA Corporation (2026) – with major processing by Our World in Data. “NVIDIA's quarterly revenue by market segment – NVIDIA” [dataset]. NVIDIA Corporation, “NVIDIA Quarterly Revenue by Market Segment” [original data].
Source: NVIDIA Corporation (2026) – with major processing by Our World In Data

### What you should know about this data
* This indicator splits NVIDIA's quarterly revenue into two parts: its data centers and AI business, and everything else — gaming graphics cards, professional workstations, automotive chips, and chips and technology sold or licensed to other companies.
* Figures are self-reported by NVIDIA in its quarterly financial disclosures, shown in US dollars, and not adjusted for inflation.
* In April 2026, NVIDIA changed how it groups its market segments. Until then, it reported four separate non-data-center segments ("Gaming", "Professional Visualization", "Auto", and "OEM & Other"); from then on, it reports them as a single combined segment. We use the combined version throughout, summing the four older segments for earlier quarters so the time series stays consistent.

### Source

#### NVIDIA Corporation – NVIDIA Quarterly Revenue by Market Segment
Retrieved on: 2026-06-08  
Retrieved from: https://investor.nvidia.com/financial-info/financial-reports/default.aspx  

#### Notes on our processing step for this indicator
NVIDIA publishes its quarterly revenue split by market segment. We combine all of its historical disclosures (covering fiscal years 2016 through 2027) into a single time series with two main categories — "Data centers and AI" and "Gaming, devices, automotive" — alongside the overall total.

In the first quarter of fiscal 2027 (the quarter ending April 26, 2026), NVIDIA changed the structure of these disclosures. Until Q4 FY26 (the quarter ending January 25, 2026), NVIDIA reported five market segments: "Data Center", "Gaming", "Professional Visualization", "Auto", and "OEM & Other". From Q1 FY27 onward, it reports just two segments — "Data Center" (further broken down into "Hyperscale" and "AI Clouds, Industrial & Enterprise") and "Edge Computing". Reconciling the eight quarters that appear in both presentations confirms that NVIDIA's new "Edge Computing" segment equals the sum of the previous categories labeled as "Gaming", "Professional Visualization", "Auto", and "OEM & Other".

To keep the time series consistent over the full period, we display data under two labels — "Data centers and AI" and "Gaming, devices, automotive". For quarters before Q1 FY27, the second bucket is the sum of NVIDIA's four older non-data-center segments ("Gaming", "Professional Visualization", "Auto", and "OEM & Other"). From Q1 FY27 onward, NVIDIA reports a single "Edge Computing" segment for everything outside data centers; we display this under the "Gaming, devices, automotive" label for continuity with the historical breakdown. Data center revenue is taken as reported in both presentations.

Each data point is dated by NVIDIA's reported fiscal-quarter end — the last Sunday of April, July, October, or January (for example, Q4 FY26 is dated January 25, 2026).


    