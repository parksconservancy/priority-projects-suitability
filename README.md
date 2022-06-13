# Suitability Analysis for Generally Locating Priority Projects
Document describing data inputs and workflow process for developing priority projects suitability map for 3 county area. 

### Project folder:
C:\Users\zstanley\OneDrive - Golden Gate National Parks Conservancy\ClimateResilienceRacialJustice
### ArcGIS Pro Project:
C:\Users\zstanley\OneDrive - Golden Gate National Parks Conservancy\ClimateResilienceRacialJustice\ProjectsCommunityIndicators.aprx  
__Map Title:__ 'ProjectPrioritiesData_GGNRA'


## Project Consisted of Multiple input datasets in three categories: 

### Climate Resilience:

1. Sea level rise inundation raster, bayside at maximum inundation 108" above current conditions at MHHW tidal datum from [Adapting to Rising Tides](https://explorer.adaptingtorisingtides.org/download)  
2. Sea level rise inundation vector, coastside areas inundated by unimpeded Pacific coastal flooding under a scenario of 1.4-meter (55-inch) sea-level rise in 2100 [Pacific Institute](https://www.pacinst.org/reports/sea_level_rise_data/Ca_coast_yr2100_flood.zip)  
3. Fire Hazard Severity Zones, these map areas of significant fire hazards based on fuels, terrain, weather, and other relevant factors. Vector feil from the California Department of Forestry and Fire Protection. 2007. [FRAP Statewide Fire Hazard Severity](https://osfm.fire.ca.gov/divisions/community-wildfire-preparedness-and-mitigation/wildland-hazards-building-codes/fire-hazard-severity-zones-maps/#panel-fe9aa269-fa8e-4501-8f75-cce08c29b227)  
4. Relative heat severity for every pixel for every city in the contiguous United States. This 30-meter raster was derived from Landsat 8 imagery band 10 (ground-level thermal sensor) from the summers of 2021, patched with data from summer 2020 where necessary. [Heat Severity - USA 2021](https://parksconservancy.maps.arcgis.com/home/item.html?id=cdd2ffd5a2fc414ca1a5e676f5fce3e3)  

### Racial Justice:

1. CalEnviro Screen pollution data included values in the 60th percentile [CalEnviroScreen 4.0 Geodatabase](https://oehha.ca.gov/media/downloads/calenviroscreen/document/calenviroscreen40gdbf2021gdb.zip)
2. CalEnviro Screen poverty (percent of the population living below two times the federal poverty Level) data includes values in the 40th percentile and above were included in data. [CalEnviroScreen 4.0 Geodatabase](https://oehha.ca.gov/media/downloads/calenviroscreen/document/calenviroscreen40gdbf2021gdb.zip)

### Open Space:

1. California Protected Areas Database (CPAD) holdings in their most detailed form at the prcel level. [California Protected Areas Database](hhttps://www.calands.org/cpad/)  

## Suitability Analysis
In general terms a suitability analysis overlays geopgraphic data in grid/cell form and outputs a score based a on a common scale i.e. 1 being the least suitable value and 5 the being the most suitable. The values that overlap are added to togehter to create an overall suitability score. The maximum score wil be the number of input layers x the value assigned for the most suitable class. In this case that would be 7 (number of data inputs listed above) x 5 (maximum suitability value for each data input). So, the most suitable areas for siting projects in our analysis have a score of 35 and the least suitable areas have a score of 7.

## Workflow and Data Processing  

1. Compile data
2. Clip all data both vector and raster to the three county area that includes GGNRA lands  
3. Verify the coordinate reference system (crs) is common to all datasets - in this case we use NAD 1983 UTM Zone 10N, epsg: 26910
4. For existing rasters resample all of them to 10-m nearest neighbor algorithm  
5. In order for vector datasets to appear as continuous they are merged, intersected or unioned with the data with county boundaries and assigned a no x value or zero to areas with no data. For example, for example fire hazard areas without the class of moderate, high or very high will receive a ‘no hazard class’. 
6. Fire Hazard classes / suitability values are: No Haz =1, Moderate = 3, High= 4, Very High = 5.  
7. CalEnviro Screen pollution data included values in the 60th percentile and above for **"Pollution Burden"** were included in data and get a score of 5 and values below that received a score of 1  
8. CalEnviro Screen poverty (percent of the population living below two times the federal poverty Level) data includes values in the 40th percentile and above. Census tracts with values in the 40th percentile or above=5 and values below that=1.
9. Heat severity is measured on a scale of 1-5. 1 being a relatively mild heat area and 5 being a severe heat area. The values of 1-5 are used as input to the suitability analysis
