# Moons in Motion: object detection for satellites

Code for cross-identification of point sources detected by DAOPHOT from Mureau et al. (2025) A&A.

The context accurately aligning images of the Uranian system along the planet's center using the ephemerides of the major outer satellites is challenging due to the apparent motion of the latter. Currently, the state-of-the-art approach involves visually inspecting the images and tagging the satellite positions using tools such as DAOPHOT. 
We aim for a computationally efficient, and easily adjustable algorithm to predict and classify the outer moons present in VLT/NACO images, using a minimalist initial training dataset. We fine tuned a ResNet-18 framework that was initially trained on ImageNet classification to predict the satellite photo-centres. This relies on only 40 hand-labelled images, which were automatically augmented to provide sufficient data for our training run. We built a fully automatic pipeline to cross-identify and predict the photo-centre of the outer Uranian satellites in VLT/NACO images. The deep learning part of the pipeline identifies satellites and achieves a mean squared error (MSE) in photo-centre prediction of around 2 pixels which is improved by automatically calling DOAPHOT to refine the result to sub-pixel accuracy.

Moons in motion is open source and can be adpated to a variety of problems and image datasets. The current notebook is meant to be didactic with different cells to custome the training dataset, check the training advancement and the quality of the prediction.

## Getting Started

Open the notebook in a Google Collab environment running on GPU or on a local machine with GPU. Upload the uranus_cropped folder in a Google Drive. The training with our data and parameters takes half an hour. The current code is designed for the detection and cross-identification of three moons, it can be adapted for other numbers of cross-identification.

## Example
A VLT/NACO image with the prediction of the photocentre's coordinates given by the model after training illustrated by the red crosses, and the detected photocentres by DAOPHOT algorithm associated in blue. The code produces a text file with the coordinates of the moons.

<img width="536" height="1072" alt="prediction" src="https://github.com/user-attachments/assets/31b91443-b9e4-4d96-ac6b-917be5397f14" />



## Citations
For additional help please read this paper 
