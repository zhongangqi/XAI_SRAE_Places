# XAI_SRAE_Places
This is a pytorch implementation of the Explainable Deep Networks (XNN) described in
>**Embedding Deep Networks into Visual Explanations** ([PDF](https://arxiv.org/abs/1709.05360))<br>
Zhongang Qi, Saeed Khorram, Fuxin Li, in arXiv preprint arXiv:1709.05360. 

For project details, please see:<br>
http://web.engr.oregonstate.edu/~qiz/

## Data and Model
Please download the data and the model from the following links:<br>
1. The original CNN model: [pytorch_vgg16_places365.pth](http://web.engr.oregonstate.edu/~qiz/DATA/XAI_Places/pytorch_vgg16_places365.pth)<br>
2. The input positive training data for category bedroom: [ALLfeaturesbedroom.mat](http://web.engr.oregonstate.edu/~qiz/DATA/XAI_Places/ALLfeatures_bedroom.mat)<br>
3. The input negative training data: [ALLfeaturesnegAll.mat](http://web.engr.oregonstate.edu/~qiz/DATA/XAI_Places/ALLfeatures_negAll.mat)

## Quick Start
1. The original CNN model (pytorch_vgg16_places365.pth) should be put to the path: **‘./Model/’**, which is converted from a pretrained caffe model (VGG16-places365) in the following link:<br>
https://github.com/CSAILVision/places365

2. The features of the positive training data (ALLfeatures_bedroom.mat) and the negative training data (ALLfeatures_negAll.mat) are extracted from the previously mentioned pretrained caffe model. You need to put them to the path: **‘./Model/’**.

3. The images in **‘./Images/’** are from ADE20K dataset. You can download more from the following link:<br>
http://groups.csail.mit.edu/vision/datasets/ADE20K/

4. Run **Main_run_visual_all.py** to train a new XNN model, combine the trained XNN model with the original CNN model, and visualize the x-features of the combined model.

There is also a trained XNN model for the category of bedroom: [SRAE_52_201803071339.pth](http://web.engr.oregonstate.edu/~qiz/DATA/XAI_Places/SRAE_52_201803071339.pth). <br>
You can:<br>
- Download the trained XNN model and put it to the path: **‘./Results/52/201803071339/’**, <br>
- Then run **ModelCombineTorch.py** to combine this trained XNN model with the original CNN model, <br>
- Finally run **XnnVisualizeTorch.py** to visualize the x-features of the combined model.

## Dependencies
All code is written in Python 3.6. You will need PyTorch 0.3+ to run the excitation bp code. <br> 
The excitation bp code is from the following link: <br>
https://github.com/greydanus/excitationbp. <br>
We revised a little to the original code, thus please use the excitation bp code we provided here.
