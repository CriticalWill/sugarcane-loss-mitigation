# sugarcane-loss-mitigation
<hr>

# **Tropical Cyclone Effects on Sugarcane: A Multivariate Analysis for Assessing Potential Mitigation Strategies**













Michael J. Williams











Supervisors:

Dr. Felin Lai </br>
Dr. Joseph Kruger



A proposed thesis submitted in partial fulfillment of the degree of Master of Science within the Department of Earth and Space Sciences at Lamar University in Beaumont, Texas. 

## **ABSTRACT**


American sugarcane production began its initial decline during the 1950s and has been hastened in recent decades by many factors including political and environmental challenges. To prevent, or at least slow, further U.S. dependence on foreign sources of sugar by retaining and perhaps expanding current sugarcane acreage while maintaining crop diversity in the country’s sugar output, the focus of this study uses modern remote sensing (RS) and Geographic Information Systems (GIS) analysis to provide insights to farmers, insurers, policymakers, and other effected stakeholders to assess crop damage from tropical cyclones that frequently reduce yields to harvests caused by lodging and flooding associated with these extreme weather events. By quantifying damaged acreage amounts and distances from windbreaks with associated windspeeds, flooding damage proximities in relation to drainage with drainage types, and recovery periods or acreage of total loss, this study provides essential data for decision makers to develop and/or implement mitigation of future losses caused by these types of wind and rain events. 



### **KEYWORDS:** <br>
***sugarcane, agriculture, Louisiana, Remote Sensing, Geographic Information Systems, crop monitoring, vegetation index, machine learning***
 

## 1.	Introduction

Sugar production in the United States is wrought with political complexity and strongly held views regarding its trade and domestic subsidies (Colin Grabow 2018). Despite U.S. sugar policy efforts, sugarcane has become a fast-dwindling commodity in the country with only two U.S. States remaining in production of the crop. With the closure of the last sugar mill in Texas in February 2024 (Ron Sterk 2024) following Hawaii’s cessation of production in 2016, future production of the crop must be closely monitored to avoid losing the few remaining growers. While sugarcane has a long history as a profitable crop, alternative sweeteners along with other sources for sugar such as sugar beets, high fructose corn syrup (HFCS), etc., combined with competitive labor markets in other countries have challenged the industry in America.

The value of sugarcane as a commodity cannot be overstated despite any assessment of the U.S. policy on sugar (USGAO 2023). As one of the top ten producers of the crop and the fifth largest supplier of sugar to the world, the United States holds a strategic advantage by maintaining or even increasing the acreage of sugarcane produced. Moreover, it is the highest valued row crop in the State of Louisiana (Kenneth Gravois et al. 2021) and the highest valued field crop in the State of Florida (Odero et al. 2022) with consistently higher than $1 billion in cash receipts from its sales annually (Vidalina Abadam 2021). The recent halt of sugarcane production in Texas underscores the importance this crop be given a high level of priority for assessing risk to its productivity caused by extreme climatic events. The two remaining States producing sugarcane are especially susceptible to tropical cyclones. With sugarcane’s growth cycle beginning in and reaching its peak harvest at the most active time of hurricane season, it is therefore prudent to assess the performance of sugarcane in the face of this type of event.

### 1.1.	 Problem Statement

The recent closure of the last sugar mill in Texas was not due to market pressures from innovation such as HFCS or competitive labor. Instead, growing populations coupled with decreased water availability from a warming climate (Jim Robbins 2022) strained the water supply beyond its sustainability for growing the crop (Dance 2024).  Conversely, the two remaining states that grow the crop are known for their abundance of water resources. Instead, the climate threat posing the greatest risk to sugarcane in both Florida and Louisiana are tropical systems producing high winds, flooding rains, tidal surge, or any combination of the three. While much has been done in the way of engineering resilient varieties of the crop to withstand harsh conditions of these tropical cyclones (Raney Rapp 2024), more study is needed to determine potential mitigation strategies that might add to the crops sustainable production well into the future. 

The reduced yields caused by crop loss from tropical cyclones impacts regional and global economies, and studies have shown that extreme climatic events are increasing in frequency (Field et al. 2012), with models predicting that the trend will continue with increases the frequency of temperature extremes (Rahmstorf and Coumou 2011). Processes and methodologies to assess damages caused by these extreme events has been well documented using RS technologies enhanced with analysis in geographic information systems GIS (Sahoo, Ray, and Manjunath 2015; Thenkabail and Lyon 2016; Hu and Smith 2018; Chen et al. 2019). To lessen the effect of tropical systems’ impacts on sugarcane and the reduced yields associated with it, more study is needed that factors in the complete landscape of modern agricultural practices using the latest technologies. In order that more comprehensive strategies for mitigation may be developed, this study proposes incorporating an analysis of Vegetation Indices (VI) to determine crop health for Louisiana sugarcane pre and post event with a comprehensive spatial analysis of mitigating factors such as field drainage and windbreaks.

### 1.2.	 Research Gap

Previous work has assessed the economic impact of sugarcane loss caused by saltwater flooding from Hurricane Rita in Louisiana that made landfall in 2005 (Beuzelin et al. 2009) underscoring the threat from not only flooding caused by the heavy rains but also from storm surge as the system works its way inland (This Week in Louisiana Agriculture 2020). Mitigation for flooding has been studied (Halbac-Cotoara-Zamfir et al. 2022), and other work has highlighted sugarcane loss from the Hurricane Iwa in Hawaii (Moore and Osgood 1985). And while vegetation damage from high winds has been shown to have varying effects on different genera of the same plant species (Brokaw and Walker 1991), and Hu and Smith (2018) have shown in their work the viability of assessing vegetation damage from the high winds of hurricanes using RS techniques, to date no study has applied this type of analysis to sugarcane while making use of modern RS technologies with comprehensive GIS analysis as proposed herein. 

This study’s focus will quantify effects of both high wind and flooding on sugarcane crops by combining a spatial analysis of the effects of water drainage and windbreak vegetation and the roles that each of these variables have in damage mitigation and crop recovery time with an overall goal of examining to what extent (if any): 
a) field planning might be modified to lessen any effects caused by temporary flooding, 
b) the effect windbreaks have on preventing crop loss, and
c) soil moisture affects the time needed for the crop to recover, or 
d) soil moisture affects the extent of crop loss.
David Greenland (2005) acknowledges the extreme variability in Louisiana’s climate presenting the greatest challenge to sugarcane for producers. While his work does much to quantify yield data with climate trends in the State, and his model does include the impact on reduced yields from Hurricane Andrew, his study fails to look at specific environmental variables that are proposed herein.  

### 1.3.	 Objectives

From this study several insights are expected for agricultural benefit to sugarcane growers, crop insurers, and policy makers that may provide techniques for new, more effective mitigation strategies against an increased threat of tropical cyclones. Resulting data is expected to quantify protective distances provided by windbreaks for sugarcane as well as potential enhancements to drainage systems and/or field planning design within distances to outflow canals, bayous, and rivers that may decrease flooding periods and thus mitigate additional crop damage. 

## 2.	Study Area Determination
To first determine the extent of potentially damaged sugarcane, tropical cyclonic events had to be chosen that would encompass enough study area for viability. To that end, Louisiana hurricanes provide ample selections for study areas, and the determination was made to use hurricanes dating back to 1985 which coincides with the data collection from the first of the National Aeronautic Space Administration (NASA) Landsat Missions (National Aeronautics and Space Administration, 2015) in 1985. Since hurricanes can vary substantially in geographic sizes regardless of their strength (National Weather Service, 2021), a range buffer was set equivalent to 160.9344 meters multiplied by the windspeed along the reported path of the hurricanes’ traverses (US Department of Commerce, 2021) through Louisiana (Figure 1). This process was accomplished using the mean wind speed between each segment of the hurricanes’ reported locations along the track using the ‘Reconstruct Tracks’ tool within ArcGIS software. This buffer distance equates to one-tenth of a mile for each mile per hour (mph) in the hurricanes’ wind speeds (Figure 1) and serves as an adequate foundation for a study area assessment based upon available guidance from National Weather Service (NWS). While this measure may not be an exact depiction of the storms’ impacts in terms of crop damage from its reported track, it does provide a basis for study areas and gives a generalized overview of impacted areas to be considered for inclusion in the study. 

### 2.1.	 Initial Assessment
By cross referencing the hurricane data with known sugarcane producing Parishes within the State (American Sugar Cane League, 2019), impact areas were assessed initially using the National Agricultural Statistics Service (NASS) cropland data layer (CDL) (U.S. Dept of Agriculture, 2021) and ultimately with visual inspection using Google’s Earth Engine (https://developers.google.com/earth-engine/datasets) available through the company’s free Google Earth Pro GIS platform to isolate chosen study areas to determine available scene coverages for impact times with the best available sensor platforms. 
Figure 1: Tropical cyclone tracks across sugarcane producing Parishes of Louisiana since 1985

### 2.2.	Final Selection
Upon investigation of CDL depicted sugarcane classifications, the discovery was made that areas of sugarcane were missing from the dataset based on field level knowledge of planted acreages. This discovery was addressed with NASS personnel who directed the work to a corrected dataset with a more refined classification of sugarcane allowing narrowing of the search and ultimately to a site selection that can make use of some of the most recent RS technologies. The final site selection falls within the hyperactive 2020 hurricane season in Southwest Louisiana that saw impacts from two storms with only forty-two days between their impacts to the area (Figure 2). Although the study was impacted by both Hurricane Laura and Delta, this work will analyze the impacts of Hurricane Laura only. This is primarily due to the need to confine the study to undamaged pre-event sugarcane. Although, other factors make Laura a more suitable tropical system for study as its damage swath was much wider, its windspeeds much higher, and overall impact much greater.

The study area consists of nine planted fields spanning approximately sixteen miles along the Interstate 10 corridor straddling the Calcasieu and Jefferson Davis Parish line. This is beneficial for the study in that a small measure of ground truthing against the CDL is done using Google’s Street View images. Most fields show evidence of sugarcane planting albeit in various growth stages since the images do not cover every year of the sugarcane’s life cycle, nor are most of the images captured at optimal times to observe whether plantings are active or the field is in a fallow period. Another benefit of the chosen study area is the close proximity to where the data will be processes and analyzed, giving opportunity to make site visits and interviews with farmers if necessary.

Figure 2: Final selection of study area from 2020 hurricane season. 
## 3.	Methodology

### 3.1.	 Calculations
So that determinations can be made on causal variables to damage or complete crop loss, several calculations will be made based on field level parameters. Each of these variables are expected to have a varying degree of impact on the success or failure of the crop in the face of tropical cyclone impact. The significance of each variable will be assessed individually to determine the correlation between the event (wind, flooding, or both) and the weights of each variable below.

### 3.1.1.	Sugarcane varieties 
Sugarcane varieties have evolved over the years to combat a myriad of challenges to producers including pest, disease, drought, wind, flooding, and a host of other environmental influences (Schmitz, Kennedy, and Zhang 2020). In some instances, producers may have more than one variety depending on the event impact date and the release of new varieties. Due to the nature of sugarcane life cycle, producers may choose to replace a crop with new varieties even if crops have additional years of production left in the planted field. Variety assessment is reviewed on a farm level basis for the chosen study area if the data can be obtained from the Farm Service Agency (FSA) of the USDA. If the data is made available, no specific variety name will be given so that proprietary operational data from the producer remains protected. Instead, a percentage calculation of differing varieties will be used to aggregate the data to an acceptable level for disclosure.

### 3.1.2.	Elevation
Point cloud Light Detection and Ranging (LiDAR) data is available nationally through the 3D Elevation Program (3DEP) from U.S. Geological Survey (USGS). Because elevation change in Louisiana does not vary greatly from year to year, the 3DEP data is expected to suffice for the study regardless of the year the data was collected. While micro elevation changes in the field are expected from one planting year to the next or even between harvest years during the growth cycle for the same planting, this micro change is not expected to affect run-off values for the purpose of flooding consideration. Therefore, this data will be used to calculate the slope of the field where the sugarcane crop is planted to determine run-off to nearby outflow sources.

### 3.1.3.	Water levels
There are several sources for hydrologic data available for this study depending on the scope and final study area selected. The USGS offers high water mark data along major water ways during storm events while the NWS has historic precipitation data available for each of the tropical cyclonic events and the Forest Service (FS) of the USDA has additional reporting stations with data available depending upon location and period of the event. These water levels coupled with slope calculations made from the elevation data will aid in determining flood impacts and temporal severity of flooding. RS data may also be used to affirm flooding durations if available based on study area and event time.
 
### 3.1.4.	Wind-induced lodging
Several Vegetation Indices (VI) ranging from the well-established Normalized Difference Vegetation Index (NDVI) to the Green Normalized Vegetation Index (GNVI) and many others for crop monitoring will allow determination of lodged sugarcane using RS. Depending upon the calibration of the sensor and which platform has the best resolution (both spatially and temporally) will determine whether an established VI or a custom VI from a trained model is used to determine lodging. The assessed damages will be correlated to windspeeds recorded by NWS.

### 3.1.5.	Windbreaks
In addition to elevation, the 3DEP data will provide the necessary data for windbreaks as well. Assessing tree canopy surrounding planted fields will allow varying degrees of lodging to be calculated based on windbreak heights and distances of protection. In absence of windbreaks for fields, the windspeed will be assumed to be the full force of the NWS recorded windspeed and act as a control variable for fields that have windbreaks. 

### 3.2.	 RS Data 
Decades of Earth Observation (EO) data is available for use in the study. Over time, these technologies have evolved to include progressively higher resolutions both spatially and temporally (Som-ard et al. 2021). So that the most advanced RS technology might be used, the most recent tracks in Figure 1 are assessed for available sensors and the assessment works its way back in time ultimately choosing RS constellations from the 2020 hurricane season (Figure 2) details of which are outlined in the sub sections below.

### 3.2.1.	Sentinel-2
The atmospheric corrected L2A datatset from Sentinel-2 (https://browser.dataspace.copernicus.eu/?sharedPinsListId=4c69efd5-bf00-43d6-8529-c88f5c28ff6f) will be the primary constellation for calculating damage. The platform was well equipped with high resolution multispectral instruments precisely for the purpose of crop monitoring and capturing imagery and details related to vegetation and soil. With a high temporal resolution of 5 days, and spatial resolution up to 10m, no data from freely available sources from that time frame is better suited.

### 3.2.2.	Soil Moisture Active Passive HydroBlocks (SMAP-HB) or International Soil Moisture Network (ISMN) Sensors with Machine Learning
Current 30m resolution data (SMAP-HB) for the study area has been presented through 2019 (https://zenodo.org/records/5206725) only (Vergopolan et al. 2022). Either through duplicating the HydroBlocks method developed by Vergopolan et al. (2022) or using the machine learning approach developed by Peng et al. (2024) which employs quantile random forest to obtain soil moistures at meter to submeter spatial resolutions for both surface and rootzone moisture levels using daily ISMN sensors (https://ismn.earth/en/dataviewer/), values calculated will aid in determining the rate at which soil moisture returned to acceptable levels after flooding or simply from oversaturation due to torrential rains associated with storm bands pre and post cyclone events.

## 4.	Analysis
The above calculated variables will allow determination of damage severity or total crop loss to the sugarcane in the study area from tropical cyclone winds and rains. For the selected study area, it is unlikely that storm surge induced flooding occurred, but localized flooding in fields from extensive rain is a possibility. The damage from wind induced lodging will be measured by distances from windbreaks. These damages will be categorized as no damage, minor, major, severe, or total loss. 

Soil moisture has a key role in sugarcane crop damage as well as recovery in instances of wind induced lodging (van Heerden et al. 2015). Therefore, pre and post event analysis of soil moisture will be assessed and correlated with lodging damage as well as recovery periods. Soil moisture assessment will also be correlated with slope and drainage sources post event to provide insights into the effectiveness of current field drainage plans.

GIS software will be used to conduct the spatial and RS analysis, and any custom scripts, geoprocessing models, and analysis outcomes will be posted to a GitHub repository that has been established for the work (https://github.com/CriticalWill/sugarcane-loss-mitigation). Additionally, any code used for processing other aspects of the data that may be needed (for instance, to obtain spatial resolution needed for soil moisture) will be posted in the same GitHub repository.

## 5.	Expected Results
The outcome of the analysis will show whether trees along field plantings act as windbreaks and provide any mitigation against hurricane force winds. If some protection is provided to sugarcane along the field boundaries where trees act as natural windbreaks, windbreak heights may play a factor in the distance measures of protection to the crop and will be assessed. Pre impact soil moisture is expected to influence damage outcomes and moisture levels will be correlated to lodged sugarcane to quantify at what levels sugarcane becomes most susceptible to wind induced lodging.

## 6.	Timeline
| Activity                         | Weeks 1&2 | Weeks 3&4 | Weeks 5&6 | Weeks 7&8 | Weeks 9&10 | Weeks 11&12 | Weeks 13&14 | Weeks 15&16 |
| -------------------------------- | --------- | --------- | --------- | --------- | ---------- | ----------- | ----------- | ----------- |
| Data Gathering and Preprocessing |xxxxxxxxxxx|xxxxxxxxxxx|           |           |            |             |             |             |
| Data Processing                  |           |xxxxxxxxxxx|xxxxxxxxxxx|           |            |             |             |             |
| Analysis                         |           |           |xxxxxxxxxxx|xxxxxxxxxxx|xxxxxxxxxxxx|xxxxxxxxxxxxx|             |             |
| Field visits (if required)       |           |           |           |xxxxxxxxxxx|xxxxxxxxxxxx|xxxxxxxxxxxxx|             |             |
| Drafting Thesis                  |           |           |           |           |xxxxxxxxxxxx|xxxxxxxxxxxxx|             |             |
| Revising                         |           |           |           |           |            |xxxxxxxxxxxxx|xxxxxxxxxxxxx|             |
| Submission                       |           |           |           |           |            |xxxxxxxxxxxxx|xxxxxxxxxxxxx|xxxxxxxxxxxxx|
| Defending                        |           |           |           |           |            |             |             |xxxxxxxxxxxxx|								

## 7.	Implications
Quantitative measures of tropical cyclone effects can inform parameters for mitigating future loss from such events. With Florida and Louisiana left as the sole remaining producers of the crop within the United States, the results of this study will give necessary insights to policy makers, producers, insurers, and other stakeholders to protect the remaining acreage and perhaps assess new fields that may be better suited for planting with new methods for mitigation.

## 8.	Acknowledgements
To date, many colleagues at the U.S. Department of Agriculture (USDA) have contributed to developing this study, both through their past work and vast experiences and with recent insights provided. One such notable contribution was from Luca Sartore and Claire Boryan of the USDA National Agricultural Statistics Service (NASS) who helped me address discrepancies in reported sugarcane acreages. Another was Opeyemi Zubair of the USDA Economic Research Service (ERS), who applied his expertise with soils data that helped me understand the impacts from flooding. The encouragement of my Branch Chief at ERS, Trina Weilert as well as my Division Director, Camille Haylock and the Administrator, Spiro Stephanou, all gave me the support and encouragement needed to develop this work. And finally, this study would not have been possible without the support of my supervisors, Felin Lai and Joseph Kruger, who have helped me by assessing prospective research topics, informing the organization of the work, and directed perspective on the time constraints with regard to the amount of work achievable as well as making recommendations on revisions and additional information to include.

## 9.	Literature Citations

 - **Beuzelin, J. M., T. E. Reagan, W. Akbar, H. J. Cormier, J. W. Flanagan, and D. C. Blouin.** 2009. “Impact of Hurricane Rita Storm Surge on Sugarcane Borer (Lepidoptera: Crambidae) Management in Louisiana.” Journal of Economic Entomology 102 (3): 1054–61. https://doi.org/10.1603/029.102.0325.</br>
 - **Brokaw, Nicholas V. L., and Lawrence R. Walker. 1991.** “Summary of the Effects of Caribbean Hurricanes on Vegetation.” Biotropica 23 (4): 442–47. https://doi.org/10.2307/2388264.</br>
 - **Chen, Huili, Qiuhua Liang, Zhongyao Liang, Yong Liu, and Shuguang Xie. 2019.** “Remote-Sensing Disturbance Detection Index to Identify Spatio-Temporal Varying Flood Impact on Crop Production.” Agricultural and Forest Meteorology 269–270 (May):180–91. https://doi.org/10.1016/j.agrformet.2019.02.002.</br>
 - **Colin Grabow. 2018.** “Candy-Coated Cartel: Time to Kill the U.S. Sugar Program.” Cato Institute. April 10, 2018. https://www.cato.org/policy-analysis/candy-coated-cartel-time-kill-us-sugar-program.</br>
 - **Dance, Scott. 2024.** “A Water War Is Brewing between the U.S. and Mexico. Here’s Why.” Washington Post, May 16, 2024. https://www.washingtonpost.com/climate-environment/2024/05/16/texas-mexico-water-shortage-treaty-dispute/.</br>
 - **Field, Christopher B., Vicente Barros, Thomas F. Stocker, and Qin Dahe, eds. 2012.** Managing the Risks of Extreme Events and Disasters to Advance Climate Change Adaptation: Special Report of the Intergovernmental Panel on Climate Change. Cambridge: Cambridge University Press. https://doi.org/10.1017/CBO9781139177245.</br>
 - **Greenland, David. 2005.** “Climate Variability and Sugarcane Yield in Louisiana.” Journal of Applied Meteorology and Climatology 44 (11): 1655–66. https://doi.org/10.1175/JAM2299.1.</br>
 - **Halbac-Cotoara-Zamfir, Rares, Asdrubal Jesus Farias-Ramirez, Jarbas Honorio de Miranda, Maria Alejandra Moreno-Pizani, Sergio Nascimento Duarte, Franklin Javier Paredes-Trejo, Luca Salvati, and Cristina Halbac-Cotoara-Zamfir. 2022.** “Simulation of Subsurface Drainage in the Sugarcane Crop under Different Spacing and Drain Depths.” Land 11 (5): 626. https://doi.org/10.3390/land11050626.
 - **Heerden, P. D. R. van, A. Singels, A. Paraskevopoulos, and R. Rossler. 2015.** “Negative Effects of Lodging on Irrigated Sugarcane Pr</br>oductivity—An Experimental and Crop Modelling Assessment.” Field Crops Research 180 (August):135–42. https://doi.org/10.1016/j.fcr.2015.05.019.</br>
 - **Hu, Tangao, and Ronald B. Smith. 2018.** “The Impact of Hurricane Maria on the Vegetation of Dominica and Puerto Rico Using Multispectral Remote Sensing.” Remote Sensing 10 (6): 827. https://doi.org/10.3390/rs10060827.</br>
 - **Jim Robbins. 2022.** “The Vanishing Rio Grande: Warming Takes a Toll on a Legendary River.” Yale E360. June 2, 2022. https://e360.yale.edu/features/warming-and-drought-take-a-toll-on-the-once-mighty-rio-grande.</br>
 - **Kenneth Gravois, Albert Orgeron, Paul White, and Brenda Tubana. 2021.** “Cover Crops for Louisiana Sugarcane Production.” LSU AgCenter. May 4, 2021. https://www.lsuagcenter.com/profiles/aiverson/articles/page1620152413689.</br>
 - **Moore, Paul H., and Robert V. Osgood. 1985.** “Assessment of Sugarcane Crop Damage and Yield Loss Caused by High Winds of Hurricanes.” Agricultural and Forest Meteorology 35 (1): 267–79. https://doi.org/10.1016/0168-1923(85)90089-9.</br>
 - **Odero, D. C., J. M. Beuzelin, M. VanWeelden, C. L. Kammerer, R. N. Raid, S. Swanson, P. Rott, and M. Mossler. 2022.** “Florida Crop/Pest Profile: Sugarcane: PI207/PI-171, Rev. 12/2022.” EDIS 2022 (6). https://doi.org/10.32473/edis-pi207-2022.</br>
 - **Peng, Yuliang, Zhengwei Yang, Zhou Zhang, and Jingyi Huang. 2024.** “A Machine Learning-Based High-Resolution Soil Moisture Mapping and Spatial–Temporal Analysis: The Mlhrsm Package.” Agronomy 14 (3): 421. https://doi.org/10.3390/agronomy14030421.</br>
 - **Rahmstorf, Stefan, and Dim Coumou. 2011.** “Increase of Extreme Events in a Warming World.” Proceedings of the National Academy of Sciences 108 (44): 17905–9. https://doi.org/10.1073/pnas.1101766108.</br>
 - **Raney Rapp. 2024.** “Sugarcane Suffers from Hurricane Francine, but the Season Isn’t over yet.” October 14, 2024. https://www.farmprogress.com/crops/sugarcane-suffers-from-hurricane-francine-but-the-season-isn-t-over-yet.</br>
 - **Ron Sterk. 2024.** “Last Sugar Cane Grower in Texas to Close | Food Business News.” Industry. Food Business News. February 23, 2024. https://www.foodbusinessnews.net/articles/25615-last-sugar-cane-grower-in-texas-to-close.</br>
 - **Sahoo, R. N., S. S. Ray, and K. R. Manjunath. 2015.** “Hyperspectral Remote Sensing of Agriculture.” Current Science 108 (5): 848–59.</br>
 - **Schmitz, Andrew, P. Lynn Kennedy, and Fangyi Zhang. 2020.** “Sugarcane and Sugar Yields in Louisiana (1911–2018): Varietal Development and Mechanization.” Crop Science 60 (3): 1303–12. https://doi.org/10.1002/csc2.20045.</br>
 - **Som-ard, Jaturong, Clement Atzberger, Emma Izquierdo-Verdiguier, Francesco Vuolo, and Markus Immitzer. 2021.** “Remote Sensing Applications in Sugarcane Cultivation: A Review.” Remote Sensing 13 (20): 4040. https://doi.org/10.3390/rs13204040.</br>
 - **Thenkabail, Prasad S., and John G. Lyon. 2016.** Hyperspectral Remote Sensing of Vegetation. CRC Press.</br>
 - **This Week in Louisiana Agriculture, dir. 2020.** Hurricane Laura Aftermath -- Leaned Over. https://www.youtube.com/watch?v=TgKXAwHUt_E.</br>
 - **USGAO, U. S. Government Accountability Office. 2023.** “Sugar Program: Alternative Methods for Implementing Import Restrictions Could Increase Effectiveness | U.S. GAO.” October 31, 2023. https://www.gao.gov/products/gao-24-106144.</br>
 - **Vergopolan, Noemi, Justin Sheffield, Nathaniel W. Chaney, Ming Pan, Hylke E. Beck, Craig R. Ferguson, Laura Torres-Rojas, Felix Eigenbrod, Wade Crow, and Eric F. Wood. 2022.** “High-Resolution Soil Moisture Data Reveal Complex Multi-Scale Spatial Variability Across the United States.” Geophysical Research Letters 49 (15): e2022GL098586. https://doi.org/10.1029/2022GL098586.</br>
 - **Vidalina Abadam. 2021.** “Sugar and Sweeteners Background.” Economic Research Service, USDA. October 19, 2021. https://www.ers.usda.gov/topics/crops/sugar-and-sweeteners/background/.</br>



