# Single Image Depth Estimation Using FPN

## Acknowledgement:
**This project is based on**

Paper: https://arxiv.org/pdf/1406.2283.pdf

Dataset: https://cs.nyu.edu/~silberman/datasets/nyu_depth_v2.html

We upgraded this paper's architecture with FPN.

<br>

**Reference github 1 and 2 are used for their example of NYU dataset dataloaders.**

Reference github 1: https://github.com/zzzyq/Depth-Map-Prediction-with-Multi-Scale-Deep-network

Reference github 2:
https://github.com/imran3180/depth-map-prediction


**Reference github 3 is for architecture of the estimation network.**

Reference github 3: https://github.com/haofengac/MonoDepth-FPN-PyTorch

Reference github 4 (adapted parts of the dataloader and training process): https://github.com/wolverinn/Depth-Estimation-PyTorch

## Adaption of code
We tried to build our own dataloader by using the NYUV2 dataset in mat format. But it is hard to combine the depth and image data in dataloader together. So we adapted parts of the dataloader code in github4 to create the NYUV2 dataloader.  

## Our own work:
We modified parts of the dataloader so all of our group members have access to the training, evaluating and testing datasets. We can train the model and save it in our shared drive.<br />
We created our own model. The original model only deals with p2 in feature maps. We did pixel-shuffle to p3, p4, p5 and concatenated them together for convolution in the next step. We trained our own model for ten epochs and compared it with the model in github 4 (keeping same hyperparameters and same loss function), the loss in our model drops more quickly. <br />
We used different loss functions in the training and validating process. <br />
Used log10 loss and RMSE_log loss function in our test dataset for evaluation. The loss is lower than the baseline methods.

