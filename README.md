# Single Image Depth Estimation Using FPN

## Acknowledgement:
**This project is based on**

Paper: https://arxiv.org/pdf/1406.2283.pdf

Dataset: https://cs.nyu.edu/~silberman/datasets/nyu_depth_v2.html

We upgraded this paper's architecture with FPN.

<br>

**Github 1 and 2 are used for reference of baseline models**

Reference github 1: https://github.com/zzzyq/Depth-Map-Prediction-with-Multi-Scale-Deep-network

Reference github 2:
https://github.com/imran3180/depth-map-prediction


**We adapted portion of code from github 3**

Reference github 3 (useful for the NYU datasetloaders): https://github.com/wolverinn/Depth-Estimation-PyTorch


## Adaption of code
We tried to build our own dataloader by using the NYUV2 dataset in mat format. But it is hard to combine the depth and image data in dataloader together. So we adapted parts of the dataloader code in github3 to create the NYUV2 dataloader.  

## Our own work:
We modified parts of the dataloader so all of our group members have access to the training, evaluating and testing datasets. We can train the model and save it in our shared drive.<br /><br />
We created our own model. The original model only deals with p2 in feature maps. We did pixel-shuffle to p3, p4, p5 and concatenated them together for convolution in the next step. We trained our own model for ten epochs and compared it with the model in github 3 (keeping same hyperparameters and same loss function), the loss in our model drops more quickly.<br /><br />
We used different loss functions in the training and validating process to get our final Depth Eestimation model. <br /><br />
Used log10 loss and RMSE_log loss function in our test dataset for evaluation. The loss is lower than the baseline methods.

## Notification:
The training epoch in the ipynb file is set to 1, because it is fully trained before. If you want to get a similar output, the training epoch needs to be greater than 10. If you want to use NYUV2 basements datasets and same dataloader, you can refer to github3 and use process_dataset.py to get the desired datasets.
