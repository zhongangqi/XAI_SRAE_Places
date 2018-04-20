# XAI_SRAE_Places
**Embedding Deep Networks into Visual Explanations** ([PDF](https://arxiv.org/abs/1709.05360))<br>
Zhongang Qi, Saeed Khorram, Fuxin Li, in arXiv preprint arXiv:1709.05360. 

For project details, please see:<br>
http://web.engr.oregonstate.edu/~qiz/

Please download the data and the model from the following links:<br>
The original CNN model: [pytorch_vgg16_places365.pth](http://web.engr.oregonstate.edu/~qiz/DATA/XAI_Places/pytorch_vgg16_places365.pth)<br>
The input positive training data for category bedroom: [ALLfeaturesbedroom.mat](http://web.engr.oregonstate.edu/~qiz/DATA/XAI_Places/ALLfeatures_bedroom.mat)<br>
The input negative training data: [ALLfeaturesnegAll.mat](http://web.engr.oregonstate.edu/~qiz/DATA/XAI_Places/ALLfeatures_negAll.mat)

The original CNN model (pytorch_vgg16_places365.pth) should be put in the path: **‘./Model/’**, which is converted from a caffe model (VGG16-places365) in the following link:<br>
https://github.com/CSAILVision/places365

The input positive training data (ALLfeatures_bedroom.mat) and negative training data (ALLfeatures_negAll.mat) are extracted from the mentioned pretrained caffe model. You need to put them to the path: **‘./Model/’**.

The images are from ADE20K dataset. You can download more images from the following link:<br>
http://groups.csail.mit.edu/vision/datasets/ADE20K/

Run **Main_run_visual_all.py** to train a new XNN model, combine the trained XNN model with the original CNN model, and visualize the x-features of the combined model.

There is also a trained XNN model for the category of bedroom: [SRAE_52_201803071339.pth](http://web.engr.oregonstate.edu/~qiz/DATA/XAI_Places/SRAE_52_201803071339.pth). <br>
You can download it and put it in path: **‘./Results/52/201803071339/’**, then run **ModelCombineTorch.py** to combine this trained XNN model with the original CNN model, and run **XnnVisualizeTorch.py** to visualize the x-features of the combined model.

All code is written in Python 3.6. You will need PyTorch 0.3+ to run the excitation bp code. <br> 
The excitation bp code is from the following link: https://github.com/greydanus/excitationbp. But we revised a little to the original code, thus please use the excitation bp code we provided here.
