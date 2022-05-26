# PointClouds
Study of 3D computer Vision using deep learning on PointClouds representation.  

Notes:
(1) When running the JupyterNoteBook project, please make sure to setup the needed Python environment.   I have included a backup of the Anaconda Navigator environment (“PyClouds.yml”) that I used with the notebook.

(2) To run the code, you will need a pickle file (pred_for_dif_rad.pickle.zip) that can be downloaded from:  https://pennstateoffice365-my.sharepoint.com/:u:/g/personal/gxc26_psu_edu/ESTstxY2j_1CiTOiTl8ajt8BAVQmlsNT4AhpDZOvORGkxA?e=miJZJL.   Make sure to unzip the downloaded file

(3) The code for creating the pickle file (pred_for_dif_rad.pickle) is not included here.  However, the principles for generating this pickle file is described below: 

		Run the PointNet++ semantic segmentation algorithm exactly as was done in the original paper Qi et al. (2017) 
		(see 	https://github.com/charlesq34/pointnet2/blob/master/README.md) on the 272 rooms in S3DIS data.   
		Do this 13 times to collect performance data on different radius values 
		r = [0.025, 0.05, 0.075, 0.1, 0.125, 0.15, 0.175, 0.2, 0.225, 0.25, 0.3, 0.35, 0.4].  
		The result would be 13 point level semantic labels for each 3D point that correspond to the 13 different radius setting.  
		These 13 values, together with the 3D coordinates and semantic ground truthfor each point are stored in the PICKLE file.  
		The PICKLE file also stores the room number of each 3D points.  
		

(4) PointNet++ semantic segmentation algorithm is a hierarchical feature learning framework on point clouds. The PointNet++ architecture applies PointNet recursively on a nested partitioning of the input point set. It also proposes novel layers for point clouds with non-uniform densities. For full description of PointNet++ algorithm, please see 
Qi, C. et al. (2017) ‘PointNet++: Deep Hierarchical Feature Learning on Point Sets in a Metric Space’, in NIPS’17: Proceedings of the 31st International Conference on Neural Information Processing Systems, Dec. 4-9, 2017. Long Beach, CA, pp. 5105–5114.

