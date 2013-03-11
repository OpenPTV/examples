Two-dimensional flow example
========

In this example we show how to use your 2D flow images and track those using OpenPTV software. 

For this purpose we've downloaded the example data from the [website of Prof. Nick Ouellette](http://leviathan.eng.yale.edu/software_tracking.html). This is a very nice set of data measured in the laboratory of Prof. Nick Ouellette in two-dimensional settings. There is also a Matlab-based two-dimensional tracking that you're welcome to test and compare to the results obtained from OpenPTV.


## Prerequisities
1. Download and install OpenPTV, either Python or C-Tcl/Tk version, <http://www.openptv.net>
2. Download the 2D_jet example <http://github.com/openptv/examples>
3. Unzip the <http://leviathan.eng.yale.edu/code/TrackExample.zip> into ```img``` directory
4. Rename the TIFF files using our convention:  
		
		#!/usr/bin/python
		import os
		import glob
		
		filelist = glob.glob('img/0*.tif') # there is also background.tif
		for f in filelist:
			os.rename(f,'img.1'+f.split('.tif')[0]) 
		

such that ```0100.tif``` becomes ```img.10100```

5. Open the software using Python from PyPTV directory:

		cd openptv/openptv-python
		python pyptv_gui/pyptv_gui.py ../examples/TrackExample
		
or C-Tcl/Tk version **from the TrackExample directory**

	cd openptv/examples/TrackExample
	../build/bin/3dptv ../ptv.tcl &
	
	
In the ```parameters``` change (using GUI !!!)

	Number of cameras = 1
	Image name img/img.10004
	Sequence: img/img.10004 to img/img.10103
	Tracking: dvdx = 0.5, dacc = 0.5 angle = 150
	
**Note** - don't leave parameters empty - if there is a place to fill in the names for 4 cameras, please, just copy/paste the first line or type anything, but not create empty boxes. 





