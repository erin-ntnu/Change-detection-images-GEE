# dNDVI-greenest-pixel-composite

Instructions for use:

This script is to be run in Google Earth Engine Code Editor. 
This requires a free user account which can be created here: https://earthengine.google.com/new_signup/ 

Fill in the required user inputs (draw area of interest, define dates and export folder in your Google Drive), then click Run.

The result can be downloaded as a Geotiff by clicking on the Tasks tab, in the panel to the right. 
The images include 5 bands: 'B2' = blue, 'B3' = green, 'B4' = red, 'B8' = near-infrared, 'NDVI' = Normalised Difference Vegetation Index
These can be viewed as RGB composites, false colour composites, or as a single band NDVI. 

How it works:

Cloud filtering is done using the COPERNICUS/S2_CLOUD_PROBABILITY dataset, 
the ee.Algorithms.Sentinel2.CDI() method for computing a cloud displacement index 
and directionalDistanceTransform() for computing cloud shadows.
Source: https://developers.google.com/earth-engine/tutorials/community/sentinel-2-s2cloudless 

Snow filtering is done using the SCL band from the Level-2A product COPERNICUS/S2

Pre- and post-event composite images are made from the filtered Sentinel-2 Level 2A images, using the greenest-pixel method. 
The difference image is created by subtracting the pre-event image from the post-event image. 
