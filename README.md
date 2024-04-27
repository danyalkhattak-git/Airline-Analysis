# Airline-Analysis
Canonical and Principal Component Analysis of Airline delay data.
The code focuses on analyzing airline delay data to understand the relationship between airport locations and various causes of delays. It follows a structured process:

Part 1 - Data Preparation

Import Data: Reads a CSV file named "AirlineDelayData.csv" into a pandas DataFrame.
Airport Averaging: Calculates average delays, number of flights, and other metrics per airport, addressing potential inconsistencies from multiple carriers serving the same airport.
Coordinate Conversion:
Extracts longitude and latitude data.
Defines a function (convert_dms_to_radians) to convert coordinates from the Degree-Minute-Second (DMS) format to radians, which is suitable for calculations on a sphere.
Part 2 - Data Visualization

3D Earth Model: Creates a 3D sphere representing the Earth using a wireframe and constants for Earth's radius.
Coordinate Transformation: Converts airport coordinates (longitude, latitude) into spherical coordinates (x, y, z) for plotting on the Earth model. This aligns with the real-world representation of locations.
Scatter Plot: Generates a 3D scatter plot where:
Airports are represented as red dots on the 3D Earth.
Plot boundaries are adjusted for better visualization.
View settings (elev, azim) are optimized for the best angle.
Part 3 - Delay Analysis

Relative Delays: Calculates percentages for each delay type (carrier, weather, NAS, security, late aircraft) relative to the total delay, indicating their proportional significance at each airport.
PCA on Delay Data:
Performs Principal Component Analysis (PCA) on the relative delay data.
Implements a custom function (my_pca) for calculating principal components.
Visualizes the first two principal components using a scatter plot to identify patterns within the delay patterns across airports.
CCA: Location vs. Delays:
Applies Canonical Correlation Analysis (CCA) to study the relationship between airport locations (longitude, latitude) and the original delay variables.
Creates a correlation matrix and heatmap to visualize these relationships.
CCA: Location vs. Delay Proportions:
Repeats the CCA analysis, this time considering the number of flights at each airport. Delay proportions are calculated to adjust for differences in airport traffic.
Generates another correlation matrix and heatmap to analyze the impact of airport size.
Key Insights

Here are some potential insights and conclusions that might be drawn from the analysis (Note: the specific insights would depend on the actual results of the CCA and visualizations):

Regional Delay Patterns: The 3D plot could highlight if certain regions of the US tend to experience more delays, potentially indicating infrastructural or traffic congestion issues.
Dominant Delay Factors: PCA helps identify the most influential delay types and how they might co-occur. This could inform airlines and airports about areas to prioritize for improving efficiency.
Geographical Correlations: CCA with raw delay data could reveal whether delays caused by factors like weather or NAS efficiency correlate with airport location.
Impact of Airport Size: CCA with delay proportions lets the analysis consider whether geographical trends change when adjusting for the scale of operations at each airport.
Limitations and Extensions

Dataset: The analysis is limited to the data in "AirlineDelayData.csv". A larger, more comprehensive dataset would yield more reliable conclusions.
Data Cleaning: Potential errors or outliers in the dataset should be addressed before drawing strong conclusions.
Additional Analysis:
Analyze delays over time (seasonality, trends).
Incorporate additional factors like airport infrastructure, flight routes etc.
