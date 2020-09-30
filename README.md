# Introduction
This is the source code of our TIP 2020 paper "Video Captioning with Object-Aware Spatio-Temporal Correlation and Aggregation" and CVPR 2019 paper "Object-aware Aggregation with Bidirectional Temporal Graph for Video Captioning". Please cite the following papers if you use our code.

Junchao Zhang and Yuxin Peng, "Video Captioning with Object-Aware Spatio-Temporal Correlation and Aggregation", IEEE Transactions on Image Processing (TIP), Vol. 29, No. 1, pp. 6209-6222, Dec. 2020.

Junchao Zhang and Yuxin Peng, "Object-aware Aggregation with Bidirectional Temporal Graph for Video Captioning", 32nd IEEE Conference on Computer Vision and Pattern Recognition (CVPR), pp. 8327–8336, 2019.

# Dependency
This code is implemented on PyTorch with GPUs.

# Data Preparation
Here we take MSVD (Microsoft video description corpus) dataset as an example. For each video, 40 frames are extracted, and 5 objects are detected for each frame with Mask RCNN model. Then we use Resnet-200 model to extract features for frames and object images.

The temporal trajectory graph and spatial relation graph can be found in 'features/msvd/SimilarityGraph' and 'features/msvd/similarity_s_c_i', respectively.

# Usage
Start training and tesing by executiving the following commands. This will train and test the model on MSVD datatset. 

    - sh run_msvd_train_forwardgraph.sh  ## train the model with forward temporal graph
    - sh run_msvd_train_backwardwardgraph.sh ## train the model with backward temporal graph
    - sh run_msvd_train_relationgraph.sh ## train the model with relation graph
    
    - python msvd_main_fusion_test_temporal.py ## test the models with two temporal graphs
    - python msvd_main_fusion_test_temporal_ralation.py ## test the models with both temporal graphs and relation graph
    
For more information, please refer to our [TIP paper](https://ieeexplore.ieee.org/document/9079611) and [CVPR paper](https://openaccess.thecvf.com/content_CVPR_2019/html/Zhang_Object-Aware_Aggregation_With_Bidirectional_Temporal_Graph_for_Video_Captioning_CVPR_2019_paper.html).

Welcome to our [Laboratory Homepage](http://www.wict.pku.edu.cn/mipl/home/) for more information about our papers, source codes, and datasets.

# Related repositories

[seqvlad](https://github.com/youjiangxu/seqvlad-pytorch)