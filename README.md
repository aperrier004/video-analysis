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

2. Install the dependencies of the project that are required: `pip install -r requirements.txt`

3. Download the zip containing the labeled training and testing data: `https://dept-info.labri.fr/~mansenca/GITW_light/DB.zip` and unzip it into the cloned repo at the root

# Steps
## Step 1
Train the model on GITW_light (https://dept-info.labri.fr/~mansenca/GITW_light/)



## Step 2
Tracking from a first detection

### Tracking OpenCV


### Incremental learning

### Move-to-Data



