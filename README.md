![RecBole Logo](logo.png)

--------------------------------------------------------------------------------
# RecBole (伯乐) 2.0
*“世有伯乐，然后有千里马。千里马常有，而伯乐不常有。”——韩愈《马说》*

[![Home](https://img.shields.io/badge/Home-RecBole-red)](https://github.com/RUCAIBox/RecBole)
[![arXiv](https://img.shields.io/badge/arXiv-RecBole-%23B21B1B)](https://arxiv.org/abs/2206.07351)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](./LICENSE)

[RecBole 1.0] | [HomePage] | [Datasets] | [Paper] 

[RecBole 1.0]: https://github.com/RUCAIBox/RecBole
[HomePage]: https://recbole.io/
[Datasets]: https://github.com/RUCAIBox/RecDatasets
[Paper]: https://arxiv.org/abs/2206.07351



Based on a popular recommendation framework [RecBole](https://github.com/RUCAIBox/Recbole), we develop an extended recommendation library called RecBole 2.0, consisting of benchmarking packages for up-to-date topics and architectures. 

RecBole 2.0 includes 8 packages covering the up-to-date research topic in recommender system:

* [Data augmentation (**RecBole-DA**)](#recbole-da)
* [Meta recommendation (**RecBole-MetaRec**)](#recbole-metarec)
* [Debiased recommendation (**RecBole-Debias**)](#recbole-debias)
* [Fairness-aware recommendation (**RecBole-FairRec**)](#recbole-fairrec)
* [Cross-domain recommendation (**RecBole-CDR**)](#recbole-cdr)
* [Graph-based recommendation (**RecBole-GNN**)](#recbole-gnn)
* [Transformer-based recommendation (**RecBole-TRM**)](#recbole-trm)
* [Person-job fit (**RecBole-PJF**)](#recbole-pjf)

For each package, we provide complete implementations from data loading, experimental
setup, evaluation and algorithm implementation. This library is of great value to facilitate the up-to-date research in recommender
systems. 


## [RecBole-DA](https://github.com/RUCAIBox/RecBole-DA)
**RecBole-DA** is a library built upon [PyTorch](https://pytorch.org) and [RecBole](https://github.com/RUCAIBox/RecBole) for reproducing and developing data augmentation for sequential recommendation. 

### 1）Highlights

* **Easy-to-use API**:
    Our library provides extensive API based on common data augmentation strategies, users can further develop own new models based on our library.
* **Full Coverage of Classic Methods**:
    We provide seven data augmentation methods based on recommender systems in three major categories.

### 2）Implemented Models

Our library includes algorithms covering three major categories:

* **Heuristic-based Methods**: CL4SRec, DuoRec
* **Model-based Methods**: MMInfoRec, CauseRec
* **Hybird Methods**: CASR, CCL, CoSeRec

### 3）The Team

RecBole-DA is developed and maintained by members from [RUCAIBox](http://aibox.ruc.edu.cn/), the developer is Shuqing Bian ([@fancybian](https://github.com/fancybian)).



## [RecBole-MetaRec](https://github.com/nuster1128/RecBole-MetaRec)

**RecBole-MetaRec** is an extended package for [RecBole](https://recbole.io/), which aims to help researchers to compare and develop their own models in the field of meta learning recommendation.

### 1) Highlights

The package can mainly provide researchers with the following advantages:

- **Conveniently develop** new meta learning recommendation models with the general meta learning framework.
- **Conveniently learn and compare** the meta learning recommendation models that we have implemented. 
- **Conveniently use** the advantages and features of RecBole.

Moreover, we provide a [document](https://recbole-metarec-doc.readthedocs.io/en/latest/) in detail for researchers.

### 2) Implemented Models

Our package includes three main types of algorithms:

- **Meta learn to predict**: MeLU, MAMO
- **Meta learn to parameterize**: LWA, NLBA, TaNP
- **Meta learn to embed**: MetaEmb, MWUF

### 3) Extended Modules

**(1) MetaDataset**: the meta learning task splitter. **(2) MetaDataLoader**: the meta learning task translator. **(3) MetaRecommender**: the template for meta learning models. **(4) MetaTrainer**: the base trainer for meta learning training process. **(5) MetaCollector**: the evaluation class for meta learning tasks. **(6) MetaUtils**: the toolkit for meta learning.

### 4) The Team

RecBole-MetaRec is developed and maintained by Zeyu Zhang ([@Zeyu Zhang](https://github.com/nuster1128)).

## [RecBole-Debias](https://github.com/JingsenZhang/RecBole-Debias)
**RecBole-Debias** is a toolkit built upon [RecBole](https://github.com/RUCAIBox/RecBole) for reproducing and developing debiased recommendation algorithms.

### 1）Highlights

* **Unified**

    A unified framework, which includes several algorithms for different kinds of biases. Meanwhile, three datasets with the different distributions of training set and test set are provided for training and evaluation.

* **Adaptive**

    Adaptive to many base recommendation models. For simplicity, the current implementation is only based on MF model.
    
* **Closely**

    Closely related to Recbole. The toolkit fully adopts the functions of Recbole, except that certain algorithms need to design unique components like trainer.

### 2）Implemented Models

We list currently supported models according to category:

* **Base Model**: MF
* **Selection Bias**: MF-IPS
* **Popularity Bias**: PDA, MACR, DICE, CausE
* **Exposure Bias**: Rel-MF


### 3）The Team

RecBole-Debias is developed and maintained by members from [RUCAIBox](http://aibox.ruc.edu.cn/), the main developers is Jingsen Zhang ([@Jingsen Zhang](https://github.com/JingsenZhang)).

## [RecBole-FairRec](https://github.com/TangJiakai/RecBole-FairRec)

**RecBole-FairRec** is a library toolkit built upon [PyTorch](https://pytorch.org) and [RecBole](https://recbole.io) for reproducing and developing fairness-aware recommendation algorithms.

### 1）Highlights
* **Easy-to-use**: Our library shares unified API and input(atomic files) as RecBole.
* **Conveniently learn and compare**: Our library provides several fairess-metrics and frameworks for learning and comparing.
* **Extensive FairRec library**: Recently proposed fairness-aware algorithms can be easily equipped in our library.

### 2）Implemented Models

We list the models and fairness-metrics that we have implemented up to now:

* **Models**: FOCF, PFCN(including PFCN_MLP, PFCN_BiasedMF, PFCN_DMF, PFCN_PMF), FairGo(including FairGo_PMF_WAP, FairGo_PMF_LBA, FairGo_PMF_LVA, FairGo_GCN_WAP, FairGo_GCN_LBA, FairGo_GCN_LVA), NFCF
* **Fairness-Metrics**:
  * **Item-Oriented**: GiniIndex, PopularityPercentage
  * **User-Oriented**: DifferentialFairness,ValueUnfairness, AbsoluteUnfairness, UnderUnfairness, OverUnfairness, NonParityUnfairness


### 3）The Team

RecBole-FairRec is developed and maintained by Jiakai Tang ([@Jiakai Tang](https://github.com/TangJiakai)).

## [RecBole-CDR](https://github.com/RUCAIBox/RecBole-CDR)
**RecBole-CDR** is a library built upon [RecBole](https://github.com/RUCAIBox/RecBole) for reproducing and developing cross-domain recommendation algorithms.

### 1) Highlights

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
**RecBole-TRM** is a library built upon [PyTorch](https://pytorch.org) and [RecBole](https://github.com/RUCAIBox/RecBole) for reproducing and developing recommendation algorithms based on Transformers (TRMs).

### 1）Highlights

* **Easy-to-use API**:
    Our library shares unified API and input (atomic files) as RecBole.
* **Fair reproducibility and comparison**:
    Our library provides fair reproducibility and comparison in a systematic mechanism.
* **Extensive Transformer library**:
    Our library provides extensive API based on common Transformer layers, one can further develop new models easily based on our library.

### 2）Implemented Models

Our library includes algorithms covering two major categories:
* **Sequential Recommendation**: TiSASRec, SSE-PT, LightSANs, gMLP, CORE
* **News Recommendation**: NRMS, NAML, NPA

### 3）The Team

RecBole-TRM is developed and maintained by members from [RUCAIBox](http://aibox.ruc.edu.cn/), the main developers are Wenqi Sun ([@wenqisun](https://github.com/wenqisun)) and Xinyan Fan ([@BELIEVEfxy](https://github.com/BELIEVEfxy)).

## [RecBole-PJF](https://github.com/RUCAIBox/RecBole-PJF)

**RecBole-PJF** is a library built upon [PyTorch](https://pytorch.org) and [RecBole](https://github.com/RUCAIBox/RecBole) for reproducing and developing recommendation algorithms for person-job fit (PJF).

### 1）Highlights

* **Unified framework**: Our library build a unified framework for different methods, including collaborative methods,  content-based methods and hybrid methods;
* **Evaluate from two perspective**: Our library evaluate for both candidates and employers, which is not contained in previous frameworks;
* **Easy to extend**: Models for person-job fit can be easily extend to our library, as we provide multiple input interfaces for both interaction and text data. 

### 2）Implemented Models

Our library includes algorithms covering three major categories:

* **CF-based Models**: LFRR and other models in RecBole
* **Content-based Models**: PJFNN, BPJFNN, APJFNN, BERT

* **Hybrid Models**: IPJF, PJFFF, SHPJF

### 3）The Teams

RecBole-PJF is developed and maintained by members from [RUCAIBox](http://aibox.ruc.edu.cn/), the main developers are Chen Yang ([@flust](https://github.com/flust)), Yupeng Hou ([@hyp1231](https://github.com/hyp1231)), Shuqing Bian ([@fancybian](https://github.com/fancybian)).

## About RecBole 2.0
With the rapid advancement of recommender systems, we are receiving an increasing number of requests from RecBole users for support the most recent advances (like debiased, fairness and GNNs). Meanwhile, members of our team are conducting research on these emerging topics or models.
As a result, we build up this extended library based on [RecBole 1.0](https://github.com/RUCAIBox/RecBole) and we believe this extension is a significant contribution to RecBole, which is a valuable resource to the research community.

In order to facilitate the retrieval of models based on RecBole, we have summarized all implemented model information and see [model list](model_list.md) for details.


## Open Source Contributions
As a one-stop framework from data processing, model development, algorithm training to scientific evaluation, RecBole has a total of 11 related GitHub projects including 
- two versions of RecBole ([RecBole 1.0](https://github.com/RUCAIBox/RecBole) and [RecBole 2.0](https://github.com/RUCAIBox/RecBole2.0));
- 8 benchmarking packages ([RecBole-MetaRec](https://github.com/nuster1128/RecBole-MetaRec), [RecBole-DA](https://github.com/RUCAIBox/RecBole-DA), [RecBole-Debias](https://github.com/JingsenZhang/RecBole-Debias), [RecBole-FairRec](https://github.com/TangJiakai/RecBole-FairRec), [RecBole-CDR](https://github.com/RUCAIBox/RecBole-CDR), [RecBole-TRM](https://github.com/RUCAIBox/RecBole-TRM), [RecBole-GNN](https://github.com/RUCAIBox/RecBole-GNN) and [RecBole-PJF](https://github.com/RUCAIBox/RecBole-PJF));
- dataset repository (<a href="https://github.com/RUCAIBox/RecSysDatasets">RecSysDatasets</a>).

In the following table, we summarize the open source contributions of GitHub projects based on RecBole.


| **Projects**                                                 | **Stars**                                                    | **Forks**                                                    | **Issues**                                                   | **Pull requests**                                            | Contributors                                                 |
| :----------------------------------------------------------- | :----------------------------------------------------------- | :----------------------------------------------------------- | :----------------------------------------------------------- | :----------------------------------------------------------- | :----------------------------------------------------------- |
| [**RecBole**](https://github.com/RUCAIBox/RecBole)           | [![Stars](https://img.shields.io/github/stars/RUCAIBox/RecBole?style=social&logo=ApacheSpark&logoColor=yellow)](https://github.com/RUCAIBox/RecBole/stargazers) | [![Forks](https://img.shields.io/github/forks/RUCAIBox/RecBole?style=social&logo=github)](https://github.com/RUCAIBox/RecBole/network/members) | [![Issues](https://img.shields.io/github/issues/RUCAIBox/RecBole?style=social&logo=git)](https://github.com/RUCAIBox/RecBole/issues) | [![Pull requests](https://img.shields.io/github/issues-pr/RUCAIBox/RecBole?style=social&logo=githubactions)](https://github.com/RUCAIBox/RecBole/pulls) | [![Contributors](https://img.shields.io/github/contributors/RUCAIBox/RecBole?style=social&logo=GitHubSponsors)](https://github.com/RUCAIBox/RecBole/graphs/contributors) |
| [**RecBole2.0**](https://github.com/RUCAIBox/RecBole2.0)     | [![Stars](https://img.shields.io/github/stars/RUCAIBox/RecBole2.0?style=social&logo=ApacheSpark&logoColor=yellow)](https://github.com/RUCAIBox/RecBole2.0/stargazers) | [![Forks](https://img.shields.io/github/forks/RUCAIBox/RecBole2.0?style=social&logo=github)](https://github.com/RUCAIBox/RecBole2.0/network/members) | [![Issues](https://img.shields.io/github/issues/RUCAIBox/RecBole2.0?style=social&logo=git)](https://github.com/RUCAIBox/RecBole2.0/issues) | [![Pull requests](https://img.shields.io/github/issues-pr/RUCAIBox/RecBole2.0?style=social&logo=githubactions)](https://github.com/RUCAIBox/RecBole2.0/pulls) | [![Contributors](https://img.shields.io/github/contributors/RUCAIBox/RecBole2.0?style=social&logo=GitHubSponsors)](https://github.com/RUCAIBox/RecBole2.0/graphs/contributors) |
| [**RecBole-DA**](https://github.com/RUCAIBox/RecBole-DA)     | [![Stars](https://img.shields.io/github/stars/RUCAIBox/RecBole-DA?style=social&logo=ApacheSpark&logoColor=yellow)](https://github.com/RUCAIBox/RecBole-DA/stargazers) | [![Forks](https://img.shields.io/github/forks/RUCAIBox/RecBole-DA?style=social&logo=github)](https://github.com/RUCAIBox/RecBole-DA/network/members) | [![Issues](https://img.shields.io/github/issues/RUCAIBox/RecBole-DA?style=social&logo=git)](https://github.com/RUCAIBox/RecBole-DA/issues) | [![Pull requests](https://img.shields.io/github/issues-pr/RUCAIBox/RecBole-DA?style=social&logo=githubactions)](https://github.com/RUCAIBox/RecBole-DA/pulls) | [![Contributors](https://img.shields.io/github/contributors/RUCAIBox/RecBole-DA?style=social&logo=GitHubSponsors)](https://github.com/RUCAIBox/RecBole-DA/graphs/contributors) |
| [**RecBole-MetaRec**](https://github.com/nuster1128/RecBole-MetaRec) | [![Stars](https://img.shields.io/github/stars/nuster1128/RecBole-MetaRec?style=social&logo=ApacheSpark&logoColor=yellow)](https://github.com/nuster1128/RecBole-MetaRec/stargazers) | [![Forks](https://img.shields.io/github/forks/nuster1128/RecBole-MetaRec?style=social&logo=github)](https://github.com/nuster1128/RecBole-MetaRec/network/members) | [![Issues](https://img.shields.io/github/issues/nuster1128/RecBole-MetaRec?style=social&logo=git)](https://github.com/nuster1128/RecBole-MetaRec/issues) | [![Pull requests](https://img.shields.io/github/issues-pr/nuster1128/RecBole-MetaRec?style=social&logo=githubactions)](https://github.com/nuster1128/RecBole-MetaRec/pulls) | [![Contributors](https://img.shields.io/github/contributors/nuster1128/RecBole-MetaRec?style=social&logo=GitHubSponsors)](https://github.com/nuster1128/RecBole-MetaRec/graphs/contributors) |
| [**RecBole-Debias**](https://github.com/JingsenZhang/RecBole-Debias) | [![Stars](https://img.shields.io/github/stars/JingsenZhang/RecBole-Debias?style=social&logo=ApacheSpark&logoColor=yellow)](https://github.com/JingsenZhang/RecBole-Debias/stargazers) | [![Forks](https://img.shields.io/github/forks/JingsenZhang/RecBole-Debias?style=social&logo=github)](https://github.com/JingsenZhang/RecBole-Debias/network/members) | [![Issues](https://img.shields.io/github/issues/JingsenZhang/RecBole-Debias?style=social&logo=git)](https://github.com/JingsenZhang/RecBole-Debias/issues) | [![Pull requests](https://img.shields.io/github/issues-pr/JingsenZhang/RecBole-Debias?style=social&logo=githubactions)](https://github.com/JingsenZhang/RecBole-Debias/pulls) | [![Contributors](https://img.shields.io/github/contributors/JingsenZhang/RecBole-Debias?style=social&logo=GitHubSponsors)](https://github.com/JingsenZhang/RecBole-Debias/graphs/contributors) |
| [**RecBole-FairRec**](https://github.com/TangJiakai/RecBole-FairRec) | [![Stars](https://img.shields.io/github/stars/TangJiakai/RecBole-FairRec?style=social&logo=ApacheSpark&logoColor=yellow)](https://github.com/TangJiakai/RecBole-FairRec/stargazers) | [![Forks](https://img.shields.io/github/forks/TangJiakai/RecBole-FairRec?style=social&logo=github)](https://github.com/TangJiakai/RecBole-FairRec/network/members) | [![Issues](https://img.shields.io/github/issues/TangJiakai/RecBole-FairRec?style=social&logo=git)](https://github.com/TangJiakai/RecBole-FairRec/issues) | [![Pull requests](https://img.shields.io/github/issues-pr/TangJiakai/RecBole-FairRec?style=social&logo=githubactions)](https://github.com/TangJiakai/RecBole-FairRec/pulls) | [![Contributors](https://img.shields.io/github/contributors/TangJiakai/RecBole-FairRec?style=social&logo=GitHubSponsors)](https://github.com/TangJiakai/RecBole-FairRec/graphs/contributors) |
| [**RecBole-CDR**](https://github.com/RUCAIBox/RecBole-CDR)   | [![Stars](https://img.shields.io/github/stars/RUCAIBox/RecBole-CDR?style=social&logo=ApacheSpark&logoColor=yellow)](https://github.com/RUCAIBox/RecBole-CDR/stargazers) | [![Forks](https://img.shields.io/github/forks/RUCAIBox/RecBole-CDR?style=social&logo=github)](https://github.com/RUCAIBox/RecBole-CDR/network/members) | [![Issues](https://img.shields.io/github/issues/RUCAIBox/RecBole-CDR?style=social&logo=git)](https://github.com/RUCAIBox/RecBole-CDR/issues) | [![Pull requests](https://img.shields.io/github/issues-pr/RUCAIBox/RecBole-CDR?style=social&logo=githubactions)](https://github.com/RUCAIBox/RecBole-CDR/pulls) | [![Contributors](https://img.shields.io/github/contributors/RUCAIBox/RecBole-CDR?style=social&logo=GitHubSponsors)](https://github.com/RUCAIBox/RecBole-CDR/graphs/contributors) |
| [**RecBole-GNN**](https://github.com/RUCAIBox/RecBole-GNN)   | [![Stars](https://img.shields.io/github/stars/RUCAIBox/RecBole-GNN?style=social&logo=ApacheSpark&logoColor=yellow)](https://github.com/RUCAIBox/RecBole-GNN/stargazers) | [![Forks](https://img.shields.io/github/forks/RUCAIBox/RecBole-GNN?style=social&logo=github)](https://github.com/RUCAIBox/RecBole-GNN/network/members) | [![Issues](https://img.shields.io/github/issues/RUCAIBox/RecBole-GNN?style=social&logo=git)](https://github.com/RUCAIBox/RecBole-GNN/issues) | [![Pull requests](https://img.shields.io/github/issues-pr/RUCAIBox/RecBole-GNN?style=social&logo=githubactions)](https://github.com/RUCAIBox/RecBole-GNN/pulls) | [![Contributors](https://img.shields.io/github/contributors/RUCAIBox/RecBole-GNN?style=social&logo=GitHubSponsors)](https://github.com/RUCAIBox/RecBole-GNN/graphs/contributors) |
| [**RecBole-TRM**](https://github.com/RUCAIBox/RecBole-TRM)   | [![Stars](https://img.shields.io/github/stars/RUCAIBOX/RecBole-TRM?style=social&logo=ApacheSpark&logoColor=yellow)](https://github.com/RUCAIBOX/RecBole-TRM/stargazers) | [![Forks](https://img.shields.io/github/forks/RUCAIBox/RecBole-TRM?style=social&logo=github)](https://github.com/RUCAIBox/RecBole-TRM/network/members) | [![Issues](https://img.shields.io/github/issues/RUCAIBox/RecBole-TRM?style=social&logo=git)](https://github.com/RUCAIBox/RecBole-TRM/issues) | [![Pull requests](https://img.shields.io/github/issues-pr/RUCAIBox/RecBole-TRM?style=social&logo=githubactions)](https://github.com/RUCAIBox/RecBole-TRM/pulls) | [![Contributors](https://img.shields.io/github/contributors/RUCAIBox/RecBole-TRM?style=social&logo=GitHubSponsors)](https://github.com/RUCAIBox/RecBole-TRM/graphs/contributors) |
| [**RecBole-PJF**](https://github.com/RUCAIBox/RecBole-PJF)   | [![Stars](https://img.shields.io/github/stars/RUCAIBox/RecBole-PJF?style=social&logo=ApacheSpark&logoColor=yellow)](https://github.com/RUCAIBox/RecBole-PJF/stargazers) | [![Forks](https://img.shields.io/github/forks/RUCAIBox/RecBole-PJF?style=social&logo=github)](https://github.com/RUCAIBox/RecBole-PJF/network/members) | [![Issues](https://img.shields.io/github/issues/RUCAIBox/RecBole-PJF?style=social&logo=git)](https://github.com/RUCAIBox/RecBole-PJF/issues) | [![Pull requests](https://img.shields.io/github/issues-pr/RUCAIBox/RecBole-PJF?style=social&logo=githubactions)](https://github.com/RUCAIBox/RecBole-PJF/pulls) | [![Contributors](https://img.shields.io/github/contributors/RUCAIBox/RecBole-PJF?style=social&logo=GitHubSponsors)](https://github.com/RUCAIBox/RecBole-PJF/graphs/contributors) |
| [**RecSysDatasets**](https://github.com/RUCAIBox/RecSysDatasets) | [![Stars](https://img.shields.io/github/stars/RUCAIBox/RecSysDatasets?style=social&logo=ApacheSpark&logoColor=yellow)](https://github.com/RUCAIBox/RecSysDatasets/stargazers) | [![Forks](https://img.shields.io/github/forks/RUCAIBox/RecSysDatasets?style=social&logo=github)](https://github.com/RUCAIBox/RecSysDatasets/network/members) | [![Issues](https://img.shields.io/github/issues/RUCAIBox/RecSysDatasets?style=social&logo=git)](https://github.com/RUCAIBox/RecSysDatasets/issues) | [![Pull requests](https://img.shields.io/github/issues-pr/RUCAIBox/RecSysDatasets?style=social&logo=githubactions)](https://github.com/RUCAIBox/RecSysDatasets/pulls) | [![Contributors](https://img.shields.io/github/contributors/RUCAIBox/RecSysDatasets?style=social&logo=GitHubSponsors)](https://github.com/RUCAIBox/RecSysDatasets/graphs/contributors) |


## Cite
If you find RecBole useful for your research or development, please cite the following [paper](https://arxiv.org/abs/2206.07351):

```bibtex
@article{zhao2022recbole2,
  author    = {Wayne Xin Zhao and Yupeng Hou and Xingyu Pan and Chen Yang and Zeyu Zhang and Zihan Lin and Jingsen Zhang and Shuqing Bian and Jiakai Tang and Wenqi Sun and Yushuo Chen and Lanling Xu and Gaowei Zhang and Zhen Tian and Changxin Tian and Shanlei Mu and Xinyan Fan and Xu Chen and Ji{-}Rong Wen},
  title     = {RecBole 2.0: Towards a More Up-to-Date Recommendation Library},
  journal   = {arXiv preprint arXiv:2206.07351},
  year      = {2022}
}

@inproceedings{zhao2021recbole,
  author    = {Wayne Xin Zhao and Shanlei Mu and Yupeng Hou and Zihan Lin and Yushuo Chen and Xingyu Pan and Kaiyuan Li and Yujie Lu and Hui Wang and Changxin Tian and Yingqian Min and Zhichao Feng and Xinyan Fan and Xu Chen and Pengfei Wang and Wendi Ji and Yaliang Li and Xiaoling Wang and Ji{-}Rong Wen},
  title     = {RecBole: Towards a Unified, Comprehensive and Efficient Framework for Recommendation Algorithms},
  booktitle = {{CIKM}},
  pages     = {4653--4664},
  publisher = {{ACM}},
  year      = {2021}
}
```
