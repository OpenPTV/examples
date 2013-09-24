# Examples


This repository will include several examples of the OpenPTV working folder setups:

1. Two dimensional setup (2D) with a single camera [](2D_jet/)
2. Three dimensional setup using 4 cameras from two sides of a tank (positive and negative z) [Link to BitBucket repository](https://bitbucket.org/turbulencelabtau/ptv_test_cavity)
3. Three dimensional setup with a single camera and mirror-based four-view splitter, [Link to BitBucket repository](https://bitbucket.org/turbulencelabtau/ptv_test_folder)
4. Short 3D-PTV example from the single camera and the 4-view splitter at Tel Aviv University [/test_splitter](https://github.com/OpenPTV/examples/tree/master/test_splitter)


## Two dimensional (2D) example of OpenPTV


This example shows how to use the excellent tracking capabilities of OpenPTV in two dimensional setup. 

Note that important advantage over a set of other 2D tracking codes:  
1. it's  fluid mechanics based code, not Brownian diffusion based logic  
2. it's a tested and verified code for turbulent flows and sharp angles, twists and turns  
3. it's a tested code for multiple particle tracking and resolution of crossing trajectories  
4. one can work with the camera not necessarily aligned perpendicular to the imaging axis or parallel to the flow field.  
5. one can track a mouse, mutliple moths, ears of bats, fish and even pedestrians with this code.   
