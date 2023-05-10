# TumorDetection_in_3DCNNmodel

## Aim:
The main goal of this challenge is the automatic classification of chest CT scans according to the 2017 Fleischner society pulmonary nodule guidelines for patient follow-up recommendation. The Fleischner guidelines are widely used for patient management in the case of nodule findings, and are composed of 4 classes, taking into account the number of nodules (single or multiple), their volume (<100mm³, 100-250mm³ and ⩾250mm³) and texture (solid, part solid and ground glass opacities (GGO)). Furthermore, three additional sub-challenges will be held related to the different tasks needed to calculate a Fleischner score. The challenge is thus made up of four different parts:  

Main Challenge - Fleischner Classification: From chest CT scans, participants must predict the correct follow-up according to the 2017 Fleischner guidelines;<br>
Sub-Challenge A - Nodule Detection: From chest CT scans, participants must detect pulmonary nodules;<br>
Sub-Challenge B - Nodule Segmentation: Given a list of >3mm nodule centroids, participants must segment the nodules in the corresponding chest CT scans;<br>
Sub-Challenge C - Nodule Texture Characterization: Given a list of nodule centroids, participants must classify nodules into three texture classes - solid, sub-solid and GGO.   


## How to reach:
Reconstructed the 3D CNN architecture inspired by this paper (Q Dou, “Multilevel Contextual 3-D CNNs for False Positive Reduction in Pulmonary Nodule Detection”, Nov 2018)  
Paper reference:   
Q, Dou; "Multilevel Contextual 3-D CNNs for False Positive Reduction in Pulmonary Nodule Detection"; IEEE; Nov 2018  

Architecture:   
![Screen Shot 2023-05-09 at 11 19 45 PM](https://github.com/btbbtzhang/TumorDetection_in_3DCNNmodel/assets/34163897/15d47fbe-d2b6-4ea4-8830-5e90051bc77f)

Based on the modules size, used different cube size and different CNN architecture  
![Screen Shot 2023-05-09 at 11 21 03 PM](https://github.com/btbbtzhang/TumorDetection_in_3DCNNmodel/assets/34163897/15aac3c9-0de1-4672-9625-d12de8c945f6)

Workflow:  
![Screen Shot 2023-05-09 at 11 21 17 PM](https://github.com/btbbtzhang/TumorDetection_in_3DCNNmodel/assets/34163897/62a9b38d-64cc-438b-8fdc-0a7fa6dbea64)

Tuning:
Learning rate	= 	0.00001 (adjusted from 0.01 with 10x decrements)  
Optimizer 		= 	Adam (tried SGD, MomentumOptimizer) (most increase in accuracy)  
Batch size 		= 	128  
Loss function 	= 	softmax_cross_entropy_with_logits  
Initializers 		= 	Xavier (tried truncated normal and constant initializers)
Different channel number of convolution filters  


## Result:
Visualizations of cube selections in CT views and in 3D plottings  
![Screen Shot 2023-05-09 at 11 25 23 PM](https://github.com/btbbtzhang/TumorDetection_in_3DCNNmodel/assets/34163897/382c27dd-47f8-4c70-955e-170ebf8ef9e7)

Training and Validation Results  
![Screen Shot 2023-05-09 at 11 26 07 PM](https://github.com/btbbtzhang/TumorDetection_in_3DCNNmodel/assets/34163897/808f4355-b05f-4046-960d-25308e249ea1)

