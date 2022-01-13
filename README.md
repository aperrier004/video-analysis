# Authors
Erwan CADO & Alban PERRIER - Bordeaux INP 2021

# Project
Video analysis research project

Support for gripping by computer vision tools for amputees of the upper limbs, carriers of neuroprostheses.

Hypothesis: the direction of the gaze expresses the intention and makes it possible to know which object the user wants to grasp 

# Dataset
Dataset [GITW_light](https://drive.google.com/drive/folders/1-COL_pTAUgSaK2Wntn_4ckhsCrLkzhhF?usp=sharing)
5 objects (Bowl, Can of Coca Cola, Milk Bottle, Rice, Sugar)
Manual annotation of the objects

# Goal
We are looking to study lifelong learning.
Given a model (CNN) trained to recognize objects, we try to adapt this model to new images arriving on the fly with the “Move-to-Data” method 

# Setting up the project
1. Clone the repository : `git clone https://github.com/aperrier004/video-analysis.git`

2. Modify every path required in the notebook and have the data (such as models, DB, VIDEOS, GT, ...)

# Steps
## Step 1
Train the model on GITW_light (https://dept-info.labri.fr/~mansenca/GITW_light/)

We did the training and evaluating with a mobile net model on the dataset which gave us an accuracy of 0.96.

## Step 2
We implemented a tracker in order to use bounding box on videos.

### Selective Search and classification
This method gave us a poor classification since the objects have several shapes and colors one video from another

### OpenCV Tracker
We chose the Channel and Spatial Reliability Tracker because it is the most accurate according to the benchmarks we found. 
The results of the OpenCV tracker are much better than those of the previous method because of its ability to better generalize its detections. 

### OpenCV with update of the model
We tried to update the model at the end of each video by training it on the objects that were detected during the video. In order not to erase the old weights, we have chosen a very small learning rate. This update of the model will make it possible to strengthen it with new data.

It gaves us average results.

### Contour detection with OpenCV Tracker 
We tried to use contours detection method, which gaves us overfitted results, very good on CanOfCocaCola and the Bowl, but not usable on the other.
It gave us a 20% accuracy.

# Results
Here is an example of some working outputs :
- [CanOfCocaCola](https://drive.google.com/file/d/1-5dxvH4x_q_T_ApGlD0nTzz_xSE2V22N/view?usp=sharing)
- [Bwowl](https://drive.google.com/file/d/1-0byu0ODWlmW1GfJfu_g51G192i1Ukq9/view?usp=sharing)

# How to improve
- Move to data : Manage to use this method
- Use polynomial interpolation to stabilize the tracking in our selective search method
- Try to use forward and backward predictions in order to have more precise predictions
