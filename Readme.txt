
![Tremors](tremors.png)



Tremors – a Software App for the Analysis of the Completeness Magnitude


Tremors is MATLAB App with a graphical interface, designed for manipulating and studying seismic catalogs, in particular the estimation of the Magnitude of Completeness (MC). Tremors is a standalone App, i.e. you don’t need a MATLAB license to install and run it. Once installed, you will see on your laptop/PC two windows, the command prompt window (black left window in Fig. 1), which will notice you in the case of error (don’t close this window!), and the Tremors window (right window in Fig. 1), that you have to use to work on your seismic catalog.

Figure 1: the two windows of Tremors.
----------------------------
Installation of Tremors
In the GitHub repository GammaArietis/Tremors (github.com), there are three versions of the App, one for MATLAB, one for Windows, and one for Linux/macOS. 

----------------------------

Installation of Tremors on MATLAB
The installation in the case of MATLAB is quite easy, you have just to download the file, and double-click on it or drag it into the command window. Once the installation window opens, MATLAB will ask you if you want to install the App. Give consent and wait. Once the installation is complete, you will be able to see and launch Tremors from the apps menu.
You need to create a work folder and inside the following folders inside to avoid encountering missing folder errors (“catalog”, “grid”, “pictures”, “polygon”, and “station”).

--------------

Installation of Tremors on Windows
The installation in the case of Windows is quite easy, you have just to download the file, and double-click on it. Once opened, Windows will ask you to authorize the App (required administrator permission), please allow this permission to properly install the App.
Once installed, you need to create a work folder, put the desktop shortcut to the app inside it, create the following folders inside to avoid encountering missing folder errors (“catalog”, “grid”, “pictures”, “polygon”, and “station”).
In the installation folder you will find a complete example. If you want to work on this directory just start Tremors inside of this directory with administrator permissions.
MATLAB runtime set the folder in which you start Tremors as the working folder, regardless of whether it is the executable or a link to it. So it is possible to create different work folder and not crowd the folders with data from other analyzes or projects.

--------------

Installation of Tremors on Linux and macOS
In this case, the installation is less straightforward; please use the following link to properly install the App: https://it.mathworks.com/help/compiler/install-deployed-application.html

--------------

How to use Tremors
The catalog format for Tremors is the same of ZMAP, i.e. it must have 10 columns defined as follows: 
      1               2           3        4        5           6              7        8          9          10
Longitude, Latitude, Year, Month, Day, Magnitude, Depth, Hour, Minute, Second.
The GUI
The graphical user interface (GUI) of Tremors contains seven different sub-sections; to access these sub-sections, please click on the horizontal bar located on the upper part of the interface.

1) Spatial

Figure 2: “Spatial” section of the interface.

This sub-section contains the spatial analysis of the catalog, it allows you to plot the catalog graphically, and by right-clicking, you have the option of selecting a smaller area if you want to go for a specific analysis. Also, from this function, you have the possibility to load and plot the list of seismic stations. 

With the "without internet" button you have the possibility to work on the map without internet using other maps uploaded by the authors automatically. 
with "you have a polygon" you have the ability to flag and load your own polygon of the area you want to examine. 
"Load Polygon" gives you the option to load the polygon. 
"Load Catalog" gives you the option to load the catalog. 
"Catalog selection" gives you the ability to make the spatial selection of the catalog having loaded or drawn the polygon. 


2) Depth


Figure 3: “Depth” section of the interface.

This sub-section contains the depth selection of the data. Here you can select a characteristic depth range within your catalogue. 

"Load Catalog" allows you to load the catalog. 
"Depth max" sets the maximum survey depth you want; expressed in meters
"Depth min" sets the minimum survey depth you want;expressed in meters
"Depth selection" button will take the min and max depth parameters into consideration and you will get the catalog to save and the plot with magnitude and depth. 

On the right side we find the Bin Density Plot setting parameters. 
"Distance" allows you to set the desired distance in meters. 
Magnitude"


3) Time

Figure 4: “Temporal” section of the interface.


This sub-section contains the temporal selection of the data. Time selection allows you to filter the data by selecting a characteristic time band within your catalogue.
 
"Load Catalog" allows you to load the catalog with already the spatial and temporal selection made.  
"Start time" allows you to select the desired start time. 
"End time" allows you to select the desired end time

At the end you will get two plots, one of the whole catalog and one related to the time selection made. Then you have the option of saving the catalog in .txt format
4) Magnitude

Figure 5: “Magnitude” section of the interface.

This sub-section contains the temporal selection of the data. Magnitude selection allows you to filter out the data by selecting a characteristic magnitude range within your catalogue, and speed up some types of calculations.

"Load Catalog" allows you to load the catalog. 
"Magnitude_Max" allows you to select the desired maximum survey magnitude 
"Magnitude_Min" allows to select the minimum desired survey magnitude 
The "magnitude selection" button pulls up the time-magnitude graph for you, with the selection you just made. It allows you to save the filtered catalog in .txt format



5) General Mc Estimation

Figure 6: “General Mc Estimation” section of the interface.


This sub- section allows the estimation of the magnitude of completeness using various methodologies, including: Maximum Curvature, Lilliefors Test, and Magnitude Transformation. As an output, we will have a graph representing the Frequency Magnitude Distribution (FMD) and a graph Quantity of Events with Magnitude. This step should be done before moving to STAI. 

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

6) STAI

Figure 7: “STAI” section of the interface.


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


7) Mc Map

Figure 8: “Mc Map” section of the interface.


This final “Mc Map” section allows to load the catalogue previously saved during the generation of the Mc calculation, and subsequently to obtain the spatial distribution of the Mc. The same three methods for general Mc computation can be applied here; however, the MAXC method is much faster than the other methods (although less reliable).
Also in this case the seismic stations can be plotted. 
"Load Catalog" allows you to load the catalog. With the "Poligon" button, load the polygon chosen or drawn in the spatial section. 
"Mc Method" allows you to select the method for analysis.
"Correction" is used to set a correction parameter related to the measurement of Mc
"Binning" allow you to set the bin you want to use
"McMax" allow you to set the maximum magnitude of completeness 
"McMin" allow you to set the magnitude of minimum completeness 
"McStep" allow you to set the interval between one Mc and the next.
"p-value" allows you to set the desired p-value as input. 
With the "Station" button load the list of stations you want to take in consideration, and then flag the "station" button if you want to plot them in the graphs. 
"Mapping Method" allows selection of the method for spatial kernel. 
"Bin Magnitude" binning of the magnitudes in the catalog (usually 0.1 for ML and 0.01 for Mw).
"Bin Degree" binning for the spatial grid (usually is 0.1° for regional catalogues, or 0.05° for local catalogues).  
"Max Distance" maximum distance considered for spatial calculation (circular search).
"Min of Event" minimum events to be considered, within a single circle. 
"Sigma Kernel" input parameter that is chosen by the operator. 

With the "Mc Maps" key you will put the calculation into execution. 
Several maps will be generated in this sub-section, in .tif format, already georeferenced. 

--------------

Contacts 
For any technical information, bug reports, or other questions, please contact: 
Giovanni Vitale: giovanni.vitale@ingv.it
Matteo Taroni: matteo.taroni@ingv.it

(This README file is updated to May 2024).
