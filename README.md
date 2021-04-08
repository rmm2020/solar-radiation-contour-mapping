# solar-radiation-contour-mapping
 Solar radiation data pulling using NREL's PVWatts API and contour mapping using Cartopy

Several Jupyter notebooks I used for a solar radiation mapping project. The National Renewable Energy Lab (NREL) website has an app called PVWatts that allows you to enter an address anywhere in the world and enter data about a solar installation and it will return solar radiation and power output information. I was interested in gathering just the solar radiation data at a variety of different angles and directional facings (e.g. N, E, S, W). For example, for solar windows, the solar panels would be tilt oriented vertically (90° angle), or perhaps 30° for a skylight. I used NREL's built-in API to pull data from locations around the world and create my own solar radiation database that I then used to create contour maps at different configurations. 

## Example Map Images

#### Horizontal Irradiance in October
![example3](/Images/Example3.png)

#### 30° Tilt in December
![example2](/Images/Example2.png)

#### 90° Tilt (Vertical) Annual Average Irradiance
![example1](/Images/Example1.png)


## Database Creation
DatabaseSetup.ipynb file is where I created an SQLite database and table for storing the output of interest from the PVWatts API call

## Query Setup
PVWatts Query Testing.ipynb file is code where I tested single queries to make sure my API calls were working correctly 

## Pulling Solar Radiation Data
PVWatts to Excel.ipynb file is where I iterated through some different configurations and added the data directly to an excel sheet for further anlysis

PVWatts Lat Lon Iterate.ipynb file is where I iterated through different latitude/longitudes and configuations to pull data using the PVWatts API and store it to my database. 

There is a use limit to the API call so the strategy I used to get latitude/longitude values for running the API calls was to use a list of US cities and another list of World cities and loop through their latitude/longitude locations, usually starting with higher population locations first. I went back and filled in more detail as needed by adding new latitude/longitude ranges.  

## Plotting the Data
PVWattsCartopyMap.ipynb and PVWattsCartopyMap-World.ipynb are the files where I queried location data from my solar radiation database, interpolated the values for contour mapping, and plotted them using the Cartopy mapping library. I mostly focused on the US and Europe. I would need to pull additional data to make completed maps for world mapping.

![world map](/Images/World_West Vertical Solar Irradiance.png)
