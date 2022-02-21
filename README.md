# Change detection images for landslide detection using Google Earth Engine

The scripts in this repository are to be run in Google Earth Engine Code Editor. 
This requires a gmail account, and free Google Earth Engine user account which can be created here: https://earthengine.google.com/new_signup/ 

Options: 
1. GEE Script: dNDVI (fast)
2. GEE Script: dNDVI (slow, cloud filtering)

Both versions of give good results for dNDVI, if used over months with green vegetation. However the fast version does not filter for clouds directly, so there are some strange results over water, and if zoomed in on the RGB image. The slow version gives better RGB image outputs. But takes a lot longer to run. 

How to use: 
Copy-paste the script from 'GEE Script' into the Google Earth Engine Code Editor window, here: https://code.earthengine.google.com/

Fill in the required user inputs (1. draw area of interest, 2. define dates and 3. set export folder in your Google Drive), then click Run.

Inspect the results in the map window.  A grey bar over the map button (right) means the image is loading. If the output images are cloudy, try extending your date ranges. 

The result can be downloaded as a Geotiff by clicking on the Tasks tab, in the panel to the right. 
The images include 5 bands: 'B2' = blue, 'B3' = green, 'B4' = red, 'B8' = near-infrared, 'NDVI' = Normalised Difference Vegetation Index
These can later be viewed as RGB composites, false colour composites, or as a single band NDVI. 
