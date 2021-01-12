<img src="obi_logo.png" width="275" height="100">

# San Francisco Bay Area Residential Zoning Data
## Published by The Othering &amp; Belonging Institute

This data repository contains the Othering &amp; Belonging Institute's residential zoning data, originally analyzed and published in the reports [Racial Segregation in the Bay Area, Part 5](https://belonging.berkeley.edu/racial-segregation-san-francisco-bay-area-part-5) and [Single-Family Zoning in the SF Bay Area: Characteristics of Exclusionary Communities](https://belonging.berkeley.edu/single-family-zoning-san-francisco-bay-area). 

## Citation
Menendian, Stephen, Samir Gambhir, Karina French, Arthur Gailes. 2020. *Single-Family Zoning in the San Francisco Bay Area: Characteristics of Exclusionary Communities*. Distributed by Othering &amp; Belonging Institute. 

## About the Data
This repository includes parcel-level shapefiles for all incorporated municipalities and unincorporated areas of the nine bay area counties: Alameda, Contra Costa, Marin, Napa, San Francisco, San Mateo, Santa Clara, Solano, and Sonoma. Each shapefile contains a categorization of residential zoning based on the most recent publicly available zoning maps and municipal code at the time of initial analysis (summer 2020). Zoning has been separated into three main categories, designated under the *Zoning* field: 

Zoning | Category | Description
------------ | ------------- | ------------- 
 1 | Single Family Residential | land zoned for only  detached, single-family residential land use, including two-family detached dwellings 
 2 | Multi-Family Residential | land zoned *not* restricted to single-family residential; zoned for mixed and multiple dwelling units, including apartment buildings, duplexes, townhomes, mobile home parks, and two-family attached dwellings.
 0 | Non-Residential | land zoned for non-residential use, including commercial, industrial, public, and recreation land use 
 3 | Non-Developable | land outside of municipal boundaries or developable land, including water, waterways, and sphere of influence land. *This category was removed from total land area for analysis.*

## About the Project
This residential zoning data and analysis is part of the Othering &amp; Belonging Institute's broader research on [Segregation in the Bay Area](https://belonging.berkeley.edu/segregationinthebay), an effort to unpack the extent, dynamics, and drivers of racial segregation in the Bay Area. 

Exclusionary, single-family zoning has long been cited as a driver for racial segregation. In order to examine the impact of single family zoning in the Bay Area, we gathered and categorized zoning shapefiles to measure the spatial distribution and extent of restricted single family zoning, specifically as a portion of total residential land use. In [Racial Segregation in the Bay Area, Part 5](https://belonging.berkeley.edu/racial-segregation-san-francisco-bay-area-part-5), we used this residential zoning data to analyze measures of segregation against restricted single family zoning to show the role of zoning in driving segregation. In [Single-Family Zoning in the SF Bay Area: Characteristics of Exclusionary Communities](https://belonging.berkeley.edu/single-family-zoning-san-francisco-bay-area), we used this residential zoning data to assess the characteristics of communities within and outside of restricted single family zoning in the Bay Area.

## Methodology
We categorized land parcels using local general plan land use map designations, based on definitions published in municipal general plans and zoning code. We primarily relied upon municipal general plan land use shapefiles and land use designations as our primary source for categorizing zones. General plan land use and zoning map shapefiles were provided by the Association of Bay Area Governments, directly from municipal planning departments, or downloaded from ESRI ArcGIS HUB.     

In instances where general plan land use and municipal zoning maps conflicted, municipal zoning geographic boundaries and designations were used. When land use and zoning definitions for land parcels did not delineate between single and multi-family, such as in mixed-use residential, planned development, and specific plan zoned land areas, we defined the type of residential land by visually examining the current built environment through satellite imagery. Land use and zoning maps were designed and modified using ArcGIS and QGIS, land use category data was processed in R, and satellite imagery was accessed through Google Earth.  When land use and zoning definitions did not delineate between single and multi-family, or there was some discrepancy, researchers referred to the current built environment to determine the type of residential land use by visually examining satellite imagery. Several common land use designations were "special cases" that required this type of manual sorting: 

#### Special Cases. 
* **Mixed Use:**  Mixed use land use and zoning is typically used to enable a mix of residential densities with commercial and public land areas. Mixed use areas defined by their dominant use (i.e. “Mixed Use Commercial”) were categorized accordingly. General mixed use areas that did not designate the type were categorized based on the current built environment, by examining satellite imagery and sorting land areas accordingly. If residential areas could not be parsed out, mixed-use categories were defined by their dominant residential category.
* **Specific Plans:** Specific plan areas are typically open land areas where municipal planners anticipate or intend a high amount of development around a specific vision or purpose, and therefore have a separate planning process and land use map. If a shapefile for the specific plan areas was not available, the residential zoning categories were manually parsed to match the land use in published specific plan documents. If the development depicted in the specific plan map was not complete based on satellite imagery, categorization followed the current built environment and only incorporated built environment that currently exists.
* **Planned Development:**  Planned development is typically a designation that allows for more flexible or dynamic zoning and land use, where planners anticipate or intend future development. If the intended use for each parcel was not defined in municipal zoning code, then planned development land area was categorized manually.    
  + *Low Number of Parcels (<500)*: For each parcel of land, satellite imagery was examined, and land use was categorized manually. If a shapefile parcel included multiple residential densities, it was parsed to delineate the two.  
  + *High Number of Parcels (>500)*: When the number of planned development parcels was too high to manually parse, we applied an automated heuristic based on building footprint shapefiles: OSM building footprint (2017) and Microsoft building footprint (2020). First, we manually categorized planned development parcels using satellite imagery, and then calculated the average area of buildings for each parcel in each category for a baseline city. The reference average building footprint was 2,500 sq ft for single family residential and 8,000 sq ft for multi-family residential. We then applied that reference average building footprint to planned development parcels in other cities’ planned development areas by calculating each parcel’s average building square footage in the Microsoft building footprint shapefile. Those were sorted in ascending order and parcels with building footprint averages between 2,500 and 8,000 were manually examined to determine the specific cut-off between the two categories. Additionally, we randomly selected 15 parcels in each category to manually check the efficacy of the building footprint heuristic. While the average square foot of each category differs for each city, the baseline reference category of average building footprints reduces the number of parcels that require the time-intensive manual categorization using satellite imagery.

## License and Attribution
We are making this data publicly available for broad, noncommercial public use for researchers, policymakers, and the academic community. If you use this data, we request you attribute it to “The Othering &amp Belonging Institute” in your publication and use the citation provided below. If you use it in an online report, we request that you link to our our digital report, [Single-Family Zoning in the SF Bay Area: Characteristics of Exclusionary Communities](https://belonging.berkeley.edu/single-family-zoning-san-francisco-bay-area).  

If you do use the data, we would love to hear about it! Send us an email at <belonging@berkeley.edu>

See our [LICENSE](https://github.com/ksfrench/BayAreaZoning/blob/ksfrench-patch-1/LICENSE.txt) for the full terms of use for this data.

## Contact Us
If you have questions about the data or licensing conditions, please contact us at: <belonging@berkeley.edu>
