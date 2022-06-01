# Spatial Variation of Geospatial Jobs in England(October and November, 2021)
**Tools Used: Python, Selenium, Geopandas, Numpy, Matplotlib** 

**Description:** 
For the months, October and November, 2021, in order to see how geospatial jobs varied from one English
region to another, job posts that contained the word geospatial(either in the job title or description) 
were scraped from LinkedIn, cleaned and stored in a csv file, in order to explore and visualize the data.

After exploring the csv data(non-spatial data), it was merged with England shapefile(spatial data) obtained 
from on a column('FILE_NAME') which was common to both data sets. The combined data was then visualized with 
geopandas and matplotlib. 

<img src="images/spatial_var_gspl_jobs.PNG?raw=true"/>
[Github link for code and data](https://github.com/Alyeko/Geospatial-jobs-England-OctNov-21)
