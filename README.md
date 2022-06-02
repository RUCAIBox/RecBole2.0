# RecBole 2.0
Based on a popular recommendation framework [RecBole](https://github.com/RUCAIBox/Recbole), we develop an extended recommendation library called RecBole 2.0, consisting of benchmarking packages for up-to-date topics and architectures. 

RecBole 2.0 includes 7 packages covering the up-to-date research topic in recommender system:

* Data augmentation
* Meta recommendation
* Debiased recommendation
* Fairness-aware recommendation
* Cross-domain recommendation
* Graph-based recommendation
* Transformer-based recommendation

For each package, we provide complete implementations from data loading, experimental
setup, evaluation and algorithm implementation. This library is of great value to facilitate the up-to-date research in recommender
systems. 


## [RecBole-DA](https://github.com/RUCAIBox/RecBole-DA)

## [RecBole-MetaRec](https://github.com/nuster1128/RecBole-MetaRec)

## [RecBole-debias](https://github.com/JingsenZhang/RecBole-Debias)

## [RecBole-FairRec](https://github.com/TangJiakai/RecBole-FairRec)

## [RecBole-CDR](https://github.com/RUCAIBox/RecBole-CDR)
**RecBole-CDR** is a library built upon [RecBole](https://github.com/RUCAIBox/RecBole) for reproducing and developing cross-domain recommendation algorithms.

### 1)Highlights

* **Automatic and compatible data processing for cross-domain recommendation**:
    Our library designs a unified data structure for cross-domain recommendation, which inherits all the data pre-processing strategies in RecBole. The overlapped data in different domains can be matched automatically.
* **Flexible and customized model training strategies**:
    Our library provides four basic training modes for cross-domain recommendation, which can be combined arbitrarily by users. It is also easy to customize training strategy in original way.
* **Extensive cross-domain recommendation algorithms**:
    Based on unified data structure and flexible training strategies, several cross-domain recommendation algorithms are implemented and compared with others fairly.

### 2) Implemented Models

Our library includes algorithms covering three major categories:

* Algorithms based on the collective matrix factorization, such as CMF and CLFM.
* Algorithms that share or combine the representations of the overlapped data, for example, DTCDR, DeepAPF and NATR.
* Algorithms that transfer or map knowledge between different domains, such as CoNet, BiTGCF, EMCDR, SSCDR and DCDCSR.

### 3) The Team

RecBole-CDR is developed and maintained by members from [RUCAIBox](http://aibox.ruc.edu.cn/), the main developers are Zihan Lin ([@linzihan-backforward](https://github.com/linzihan-backforward)), Gaowei Zhang ([@Wicknight](https://github.com/Wicknight)) and Shanlei Mu ([@ShanleiMu](https://github.com/ShanleiMu)).


## [RecBole-GNN](https://github.com/RUCAIBox/RecBole-GNN)
**RecBole-GNN** is a library built upon [PyTorch](https://pytorch.org) and [RecBole](https://github.com/RUCAIBox/RecBole) for reproducing and developing recommendation algorithms based on graph neural networks (GNNs). 

### 1）Highlights

* **Easy-to-use and unified API**:
    Our library shares unified API and input (atomic files) as RecBole.
* **Efficient and reusable graph processing**:
    We provide highly efficient and reusable basic datasets, dataloaders and layers for graph processing and learning.
* **Extensive graph library**:
    Graph neural networks from widely-used library like [PyG](https://github.com/pyg-team/pytorch_geometric) are incorporated. Recently proposed graph algorithms can be easily equipped and compared with existing methods.

### 2）Implemented Models

Our library includes algorithms covering three major categories:

* **General Recommendation**: NGCF, LightGCN, SGL, HMLET, NCL, SimGCL
* **Sequential Recommendation**: SR-GNN, GC-SAN, NISER, LESSR, TAGNN, GCE-GNN, SGNN-HN
* **Social Recommendation**: DiffNet, MHCN, SEPT

### 3）The Team

RecBole-GNN is developed and maintained by members from [RUCAIBox](http://aibox.ruc.edu.cn/), the main developers are Yupeng Hou ([@hyp1231](https://github.com/hyp1231)), Lanling Xu ([@Sherry-XLL](https://github.com/Sherry-XLL)) and Changxin Tian ([@ChangxinTian](https://github.com/ChangxinTian)).

## [RecBole-TRM](https://github.com/RUCAIBOX/RecBole-TRM)

