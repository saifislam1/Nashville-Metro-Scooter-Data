# Nashville-Metro-Scooter-Data
## Project to address a major planning question for scooters
 * What is the ideal density of available scooters to:
    * enable scooters to serve our transportation goals,
    * discourage scooters piling up on sidewalks,
    * keep it economically viable for companies to operate equitably in the city?
### Points to consider
* Major planning goal to reduce the number of people driving alone
* 3 rides (of 3 meters or more) per day per scooter is our baseline for ridership goals
* Original pilot program limited scooter density to 340 scooters per square mile
* Other cities have limited the number of scooters per block face


### The data
#### Shared Urban Mobility Device (SUMD) availability data for May, June, and July 2019  
```
    May data shape:  (20292503, 9)
   June data shape:  (28046095, 9)
   July data shape:  (25075445, 9)
   ```

**pubdatetime** - date and time that the device was polled  
**latitude** - latitude location of device when polled  
**longitude** - longitude location of device when polled  
**sumdid** - unique identifier for the device  
**sumdtype** - one of two types (powered or standard)  
**chargelevel** - battery charge level of the device when polled  
**sumdgroup** - type of device (scooter or bicycle)  
**costpermin** - the cost per minute of device use  
**companyname** - the company that owns the device

Per [ordinance](https://www.nashville.gov/Metro-Clerk/Legislative/Ordinances/Details/7d2cf076-b12c-4645-a118-b530577c5ee8/2015-2019/BL2018-1202.aspx): 
```
All permitted operators will first clean data before providing or reporting data to Metro. Data 
processing and cleaning shall include:  
 1. Removal of staff servicing and test trips
 2. Removal of trips below one minute
 3. Trip lengths are capped at 24 hours
 ```
Anecdotally, per metro ITS staff, some of these observations may still be in the data.

#### Shapefiles for Nashville Promise Zone 
SUMD devices are thought to be of particular use in the [Promise Zone](https://www.nashville.gov/Mayors-Office/Promise-Zone/Basics.aspx) to help mitigate the "last mile" problem that exists in connecting people where they live to public transportation.

Remember that you need to keep the shapefiles together. Even though you will point to the `.shp` file to create polygons, that file references other files in the `MDHA_Promise_Zones` folder to create the geoDataFrame.


