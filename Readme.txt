# Tremors
MATLAB app with graphical interface, designed for manipulating, studying, and modeling seismic catalogs. Useful tool for all initial operations, i.e. up to the estimation of the MC of the catalogue and spatial study of the Mc. There is also a stand-alone version: this version does not require a MATLAB installation on the computer.


------------------------------------------------------------------------------------------------------------------------------------


## System Requirements
Having downloaded Matlab in its updated version, once the app is downloaded, one simply has to click on 'Run'.


-------------------------------------------------------------------------------------------------------------------------------------
## Installation
1. Clone or download the repository from the URL.
2. Run the application by running the main `main.m` file.
-------------------------------------------------------------------------------------------------------------------------------------


## Usage 
In initializing the app, the operator must be set as administrator, as it would give error. 
A basic requirement to start analysing the seismic catalogue is that it must be in ZMAP format. 
That is, it must have 10 columns defined as follows: Longitude, Latitude, Years, Months, Days, Magnitude, Depth, Hours, Minutes, Seconds.


1. Spatial analysis allows you to plot the catalogue graphically, and by right-clicking, you have the option of selecting a smaller area if you want to go for a specific analysis. Also, from this function, you have the possibility to load and plot the list of seismic stations. 


With the "without internet" button you have the possibility to work on the map without internet using other maps uploaded by the authors automatically. 
with "you have a polygon" you have the ability to flag and load your own polygon of the area you want to examine. 
"Load Polygon" gives you the option to load the polygon. 
"Load Catalog" gives you the option to load the catalog. 
"Catalog selection" gives you the ability to make the spatial selection of the catalog having loaded or drawn the polygon. 


2. Time selection allows you to filter the data by selecting a characteristic time band within your catalogue. 


"Load Catalog" allows you to load the catalog with already the spatial and temporal selection made.  
"Start time" allows you to select the desired start time. 
"End time" allows you to select the desired end time


At the end you will get two plots, one of the whole catalog and one related to the time selection made. Then you have the option of saving the catalog in .txt format


3. Depth selection allows you to filter the data by selecting a characteristic depth range within your catalogue. 


"Load Catalog" allows you to load the catalog. 
"Depth max" sets the maximum survey depth you want; expressed in meters
"Depth min" sets the minimum survey depth you want;expressed in meters
"Depth selection" button will take the min and max depth parameters into consideration and you will get the catalog to save and the plot with magnitude and depth. 


On the right side we find the Bin Density Plot setting parameters. 
"Distance" allows you to set the desired distance in meters. 
Magnitude" allows you to set the desired magnitude


4. Magnitude selection allows you to filter the data by selecting a characteristic magnitude range within your catalogue.


"Load Catalog" allows you to load the catalog. 
"Magnitude_Max" allows you to select the desired maximum survey magnitude 
"Magnitude_Min" allows to select the minimum desired survey magnitude 
The "magnitude selection" button pulls up the time-magnitude graph for you, with the selection you just made. It allows you to save the filtered catalog in .txt format


5. The 'General Mc Estimation' section allows estimation of the magnitude of completeness using various methodologies, including: Maximum Curvature, Lilliefors Test and Magnitude Transformation. As an output, we will have a graph representing the Frequency Magnitude Distribution (FMD) and a graph Quantity of Events with Magnitude. This step should be done before moving to STAI. 


"Load Catalog" allows you to load the catalog. 
with the "Method" button we select the methodologies for calculating the magnitude of completeness. 
"Correction" is used to set a correction parameter related to the measurement of Mc
"Binning" allow you to set the bin you want to use
"McMax" allow you to set the maximum magnitude of completeness 
"McMin" allows you to set the magnitude of minimum completeness 
"McStep" allow you to set the interval between one Mc and the next.
"p-value" allow you to set the desired p-value as input
The "Mc" key starts the processing of the Mc. The user has at his disposal the visualization of the calculation status, at the end he will get a graph in which he will see the FMD and time-magnitude graph with the bar in red representing the Mc. This is when we are in MAXC mode. In Lilliefors and Magnitude Transformation mode, we get a graph in which we have the p-value represented, magnitude-time graph. 
"Mc value" allow to display the calculated Mc value.


6. The STAI section allows you to study the Short-Term Aftershock Incompleteness (STAI).  It allows you to better detect incompleteness within a catalogue during a seismic sequence, in particular after strong events. 
"Load Catalog" allows you to load the catalog. 
"Mc" general magnitude of completeness, estimated from the previous analysis. 
"McMin" magnitude threshold, lower than Mc (usually Mc - 0.5 is enough), is useful to catch the STAI periods in the Incremental number vs magnitude plot. 
"M1,M2,M3" mainshock magnitudes allow you to have three different thresholds for the events that will generate the STAI: must be M3 >= M2 >= M1. 
"T1,T2,T3" temporal lengths of STAI periods, one for each of the three magnitude thresholds M1, M2, M3. 
"DMC1,DMC2,DMC3" increases of completeness levels (starting from the general completeness Mc) during STAI periods, one for each of the three magnitude thresholds M1, M2, M3.  
The parameters M and DMC are dimensionless, while T is expressed in days. 
The STAI key initializes execution, then the wait bar will appear. 
At the end of the run, two representative graphs will be obtained: one for calculating the STAI and another M-Mc with the incremental number. 


7. The Mc Map section makes it possible to load the catalogue previously saved during the generation of the Mc calculation, and subsequently to obtain the spatial distribution of the Mc. The same three methods for general Mc computation can be applied here; however, the MAXC method is much faster than the other methods (although less reliable).
Seismic stations can also be plotted in this case. 


"Load Catalog" allows you to load the catalog. With the "Poligon" button, load the polygon chosen or drawn in the spatial section. 


"Mc Method" allows you to select the method for analysis.
"Correction" is used to set a correction parameter related to the measurement of Mc
"Binning" allow you to set the bin you want to use
"McMax" allow you to set the maximum magnitude of completeness 
"McMin" allow you to set the magnitude of minimum completeness 
"McStep" allow you to set the interval between one Mc and the next.
"p-value" allow you to set the desired p-value as input. 


With the "Station" button load the list of stations you want to take in consideration, and then flag the "station" button if you want to plot them in the graphs. 


"Mapping Method" allow selection of the method for spatial kernel. 
"Bin Magnitude" binning of the magnitudes in the catalog (usually 0.1 for ML and 0.01 for Mw).
"Bin Degree" binning for the spatial grid (usually is 0.1° for regional catalogues, or 0.05° for local catalogues).  
"Max Distance" maximum distance considered for spatial calculation (circular search).
"Min of Event" minimum events to be considered, within a single circle. 
"Sigma Kernel" input parameter that is chosen by the operator. 


With the "Mc Maps" key bring the calculation into execution. 
Eventually several maps will come out, in .tif format, already georeferenced. 


------------------------------------------------------------------------------------------------------------------------------------


## Contact 
For any technical information please contact: giovanni.vitale@ingv.it or matteo.taroni@ingv.it