# XAI_SRAE_Places
The original CNN model named pytorch_vgg16_places365.pth is in the path: ‘./Model/’, which is converted from a caffe model (VGG16-places365) in the following link:
https://github.com/CSAILVision/places365

The input features for positive training data (ALLfeatures_bedroom.mat) and negative training data (ALLfeatures_negAll.mat) are extracted from the mentioned pretrained caffe model. You need to put them to the path: ‘./Model/’.

The images are from ADE20K dataset. You can download more images from the following link: http://groups.csail.mit.edu/vision/datasets/ADE20K/

Run Main_run_visual_all.py to train a new XNN model, combine the trained XNN model with the original CNN model, and visualize the x-features.

There is also a trained XNN model for the category of bedroom named SRAE_52_201803071339.pth in path: ‘./Results/52/201803071339/’. Run ModelCombineTorch.py to combine this trained XNN model with the original CNN model. Then run XnnVisualizeTorch.py to visualize the x-features of the combined model.

All code is written in Python 3.6. You will need PyTorch 0.3+ to run the excitation bp code.  The excitation bp code is from the following link: https://github.com/greydanus/excitationbp. But we revised a little to the original code, thus please use the excitation bp code we provided here.
