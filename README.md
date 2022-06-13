# Suitability analysis for generally locating Priority Projects
Document describing data inputs and workflow process for developing priority projects suitability map for 3 county area. 

## Project Consisted of Multiple input datasets in two categories: 

### Climate Resilience:

1. Sea level rise inundation raster, bayside at maximum inundation 108" above current conditions at MHHW tidal datum from [Adapting to Rising Tides](https://explorer.adaptingtorisingtides.org/download)  
2. Sea level rise inundation vector, coastside areas inundated by unimpeded Pacific coastal flooding under a scenario of 1.4-meter (55-inch) sea-level rise in 2100 [Pacific Institute](https://www.pacinst.org/reports/sea_level_rise_data/Ca_coast_yr2100_flood.zip)  
3. Fire Hazard Severity Zones, these map areas of significant fire hazards based on fuels, terrain, weather, and other relevant factors. Vector feil from the California Department of Forestry and Fire Protection. 2007. [FRAP Statewide Fire Hazard Severity](https://osfm.fire.ca.gov/divisions/community-wildfire-preparedness-and-mitigation/wildland-hazards-building-codes/fire-hazard-severity-zones-maps/#panel-fe9aa269-fa8e-4501-8f75-cce08c29b227)  
4. Relative heat severity for every pixel for every city in the contiguous United States. This 30-meter raster was derived from Landsat 8 imagery band 10 (ground-level thermal sensor) from the summers of 2021, patched with data from summer 2020 where necessary. [Heat Severity - USA 2021](https://parksconservancy.maps.arcgis.com/home/item.html?id=cdd2ffd5a2fc414ca1a5e676f5fce3e3)  

### Racial Justice:

1. CalEnviro Screen pollution data included values in the 60th percentile and above were included in data and get a score of 5 and values below that received a score of 1 [CalEnviroScreen 4.0 Geodatabase](https://oehha.ca.gov/media/downloads/calenviroscreen/document/calenviroscreen40gdbf2021gdb.zip)
2. CalEnviro Screen poverty (Percent of the population living below two times the federal poverty Level) data includes values in the 40th percentile and above were included in data. Gets a value of 5 (highest suitability) and values below that get a score of 1 [CalEnviroScreen 4.0 Geodatabase](https://oehha.ca.gov/media/downloads/calenviroscreen/document/calenviroscreen40gdbf2021gdb.zip)
