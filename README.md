# Amazon Rainforest Deforestation Analysis

This project uses Google Earth Engine's (GEE) platform to analyze deforestation in the Amazon rainforest. The analysis is based on the Hansen Global Forest Change dataset.

## Project link

[GEE Project Link](https://code.earthengine.google.com/349b4b05936a77786f0ebf0b5c839db5?noload=true)

## Features

- Load and visualize the Amazon region geometry
- Load the Hansen Global Forest Change dataset
- Calculate and visualize deforestation area for each year
- Calculate and visualize cumulative deforestation over the years
- Calculate and visualize deforestation rate over the years

## Code Explanation

The code begins by loading the geometry of the Amazon region from a feature collection asset. This geometry is then added to the map for visualization. The Hansen Global Forest Change dataset is loaded next, and the 'lossyear' band is selected and clipped to the Amazon region geometry.

The map is then centered on the Amazon region, and the forest loss image is displayed on the map. A list of years of interest is defined, and a map function is used to iterate over these years. For each year, the code calculates the deforestation area by creating a mask of pixels where forest loss occurred in that year, multiplying this mask by the pixel area, and reducing this to a sum over the Amazon region.

This list of images is converted into an ImageCollection, and the 'year' and 'area' properties are aggregated into lists. These lists are then used to create a dictionary of deforestation data, with years as keys and deforestation areas as values. This data is used to create an area chart showing deforestation over the years.

The code then calculates the cumulative deforestation by iterating over the deforestation areas list and adding each area to the sum of the previous areas. This cumulative list is converted into a dictionary and used to create an area chart showing cumulative deforestation over the years.

Finally, the code calculates the deforestation rate by dividing each cumulative deforestation value by its index in the list (which represents the number of years). This results in a list of deforestation rates, which is converted into a dictionary and used to create an area chart showing the deforestation rate over the years.

## Usage

To use this code, you need to have access to Google Earth Engine and the Hansen Global Forest Change dataset. You also need to have the Amazon region geometry asset in your GEE account. Once you have these, you can simply copy the code into the GEE code editor and run it. The results will be displayed in the console and on the map.
