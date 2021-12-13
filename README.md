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

# Steps
## Step 1
Train the model on GITW_light (https://dept-info.labri.fr/~mansenca/GITW_light/)
### TODO : 
- utiliser une architecture éprouvée (ResNet, VGG, ...)
- utiliser une architecture éprouvée déjà entraînée  (transfer learning/fine tuning)
- utiliser une autre normalization des données (standardization/z-score normalization)
- utiliser de la "data augmentation" (très facile avec Keras ImageDataGenerator)
- essayer d'autres hyper paramètres (optimizer ? batch size ? ...)
- améliorer la partie "rapport" :
   - La présentation de la matrice de confusion pourrait être grandement améliorée (cf https://scikit-learn.org/stable/modules/generated/sklearn.metrics.ConfusionMatrixDisplay.html )
   - les plots de loss/accuracy pourrait être juste après l'entrainement (et pas à la toute fin).
   - discuter vos résultats [le but du projet est de montrer que vous avez essayé plusieurs solutions et de discuter ce que vous avez trouvé].



