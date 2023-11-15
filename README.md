# CrossSectionsExtractionVisualization (CSEV)
The cross-section extraction visualization tool automates extracting cross-sections with their horizontal distance and elevation. The repository contains notebooks and ArcGIS Pro Tool for cross-section extraction and visualization.

## Usage Guide
The easiest and quickest way to use the cross-section extraction visualization tool is to run it from ArcPro Toolboxes, where the functions can be directly loaded without setup. 


### Example usage
extract_and_visualize_cross_sections('Data\Shapefiles\Cross sections.shp', 'Data\DEM.tif', n_points=3, csv_output_dir='Samples', png_output_dir='Samples')

### Explanation
The code is an ArcGIS Python Toolbox that is designed to be used within ArcGIS Pro. It is a custom geoprocessing tool that performs the following tasks:

1. Takes input parameters:
   - Cross Sections Shapefile (a shapefile containing cross-sectional lines)
   - Digital Elevation Model (DEM) Raster (a raster dataset representing elevation data)
   - CSV Output Directory (a directory for saving CSV files)
   - PNG Output Directory (a directory for saving PNG images)

2. Loads the cross-sectional lines from the provided shapefile as a GeoDataFrame using the `geopandas` library.

3. Iterates through each cross-sectional line in the GeoDataFrame and performs the following operations for each:

   a. Extracts the starting and ending coordinates of the line.

   b. Divides the line into a specified number of points (default: 5) and calculates the latitude and longitude of these points.

   c. Creates a Pandas DataFrame containing latitude and longitude data.

   d. Converts the DataFrame to a GeoDataFrame, specifying the coordinate reference system (CRS).

   e. Calculates the horizontal distance (h_distance) for each point from the starting point of the line.

   f. Extracts elevation data for each point from the DEM raster using `rasterio`.

   g. Extracts h_distance and elevation columns from the GeoDataFrame and stores them in a Pandas DataFrame.

   h. Saves the extracted data as a CSV file in the specified CSV output directory.

   i. Generates a plot of the cross-sectional profile, with h_distance on the x-axis and elevation on the y-axis, and saves it as a PNG image in the specified PNG output directory.

4. If any errors occur during the execution of the tool, it reports the error message.

5. The `postExecute` method is called after the tool has executed, but in this case, it does not perform any additional actions.


## Acknowledgement
I acknowledge the YouTube video made by the GeoDev Tools channel for the video of the crosssection extractor and other contributors for successful implementation.

Dong, P., Zhong, R., Xia, J., & Tan, S. (2020). A semi-automated method for extracting channels and channel profiles from lidar-derived digital elevation models. Geosphere, 16(3), 806-816.

## Contact
We welcome any valuable feedback or suggestions for improvement. If you have any queries about the algorithm, open for discussion and contact:
pthapa2@crimson.ua.edu.
