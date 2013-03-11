Two dimensional (2D) example 
========

This example data set is an example of how to prepare your data for the two-dimensional tracking using our OpenPTV software. 

The structure of the directory as follows:

	examples/2D_jet:
	
		 /calibration
		 /img
		 /parameters
		 /res
		 

It is possible that ```/res``` folder does not exist and the user has to create it before running the software.

```/calibration``` folder includes:

	calibration_block.txt
	cam1.ori
	cam1.addpar
	
	
where ```calibration_block.txt``` gives the physical coordinates of the calibration target body (if used) and allows to measure 2D tracking in a plane using a camera at some angle. The file is an ASCII table with 4 columns:

	#counter	x	y	z
	
e.g. 

	1	0	0	0
	2	25	0	0
	3	50	0	0
	4	75	0	0
	5	100	0	0
	6	0	25	0
	
In two-dimensional case the last column, ```z``` is by convention 0. If the calibration target was also inclined, the user has to supply the correct ```x,y,z``` combinations in order to allow for this correction. 

```cam1.ori``` file is the orientation file of the camera, it's bundle adjustment. In the simplest 2D case it will be:

	0	0	100
	0	0	0
	
	1	0	0
	0	1	0
	0	0	1
	
	0	0
	100
	
	0	0	20
	
where the first row is the ```x,y,z``` of the camera from the observation volume, the second row is the there angles around ```x,y,z``` axis respectively. The unity matrix is a fundamental matrix that will be automatically updated by the software, in 2D case has little meaning. The next two numbers are ```xp,yp```, the offset of the imaging axis at the sensor plane (some sensors are not precisely parallel or measure the flow at some angle) and the next row with a single number is the back focal length. We refer the user to Dracos (1996) collection of papers for the detailed information regarding the photogrammetry principles. 
The last row is the vector that describes the position of the interface (glass cover of the flow field, a glass wall of the container, etc.), allowing us to measure 2D tracking through a multi-media: air-glass-water or air-PDMS-silicon oil. 

```cam1.addpar``` lists the additional parameters used in the calibration of the camera, allowing for shear, fish-eye and other aberrations to be included in the image-to-world and world-to-image mapping. In total 16 parameters can be optimized in order to get the best image-to-world model. 

Subdirectory ```/img``` will contain images. The Tcl/Tk version of OpenPTV works only with TIF images and we recommend this format for the general use. Python version can work with JPEG, PNG, BMP, TIF, etc. However, we believe that TIFF is the most practical and useful format in this case. Images are numbered (some historical reasons involved in this convention) as: 
	
	cam1.10000, cam1.100001, …., cam1.101000

of course ```cam1.``` is an arbitrary name, but the files are with a numeric counter instead of an extension. 


	/parameters
	
includes all the parameter files that the user can set up using our Tcl/Tk or Python GUIs. The parameters are explained in our general tutorial. Important to note that for the 2D case a user shall set the ```number of cameras``` parameter to 1. 


