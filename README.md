# Introduction
This is the source code of our TIP 2020 paper "Video Captioning with Object-Aware Spatio-Temporal Correlation and Aggregation". Please cite the following paper if you use our code.

Junchao Zhang and Yuxin Peng, "Video Captioning with Object-Aware Spatio-Temporal Correlation and Aggregation", IEEE Transactions on Image Processing (TIP), Vol. 29, No. 1, pp. 6209-6222, Dec. 2020.

# Dependency
This code is implemented with tensorflow (1.13.1).

# Data Preparation
Here we take MSVD (Microsoft video description corpus) dataset as an example. For each video, 40 frames are extracted, and 5 objects are detected for each frame with Mask RCNN model. Then we use Resnet-200 model to extract features for frames and object images.

The temporal trajectory graph and spatial relation graph can be found in 'features/msvd/SimilarityGraph' and 'features/msvd/similarity_s_c_i', respectively.

# Usage
Start training and tesing by executiving the following commands. This will train and test the model on MSVD datatset. 

    - sh run_msvd_train_forwardgraph.sh  ## train the model with forward temporal graph
    - sh run_msvd_train_backwardgraph.sh ## train the model with backward temporal graph
    - sh run_msvd_train_relationgraph.sh ## train the model with relation graph
    
    - python msvd_main_fusion_test_temporal.py ## test the models with two temporal graphs
    - python msvd_main_fusion_test_temporal_ralation.py ## test the models with both temporal graphs and relation graph
    
For more information, please refer to our [TIP paper](https://ieeexplore.ieee.org/document/9079611).

Welcome to our [Laboratory Homepage](http://www.wict.pku.edu.cn/mipl/home/) for more information about our papers, source codes, and datasets.

# Related repositories

[sam-tensorflow](https://github.com/HuiyunWang/sam-tensorflow)
[seqvlad](https://github.com/youjiangxu/seqvlad-pytorch)