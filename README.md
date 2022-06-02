# RecBole 2.0
In order to support the study of recent advances in recommender
systems, based on a popular recommendation framework [RecBole](https://github.com/RUCAIBox/Recbole), we develop an extended recommendation library called RecBole 2.0, consisting of benchmarking packages for up-to-date topics and architectures. 

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

## [RecBole-GNN](https://github.com/RUCAIBox/RecBole-GNN)
**RecBole-GNN** is a library built upon [PyTorch](https://pytorch.org) and [RecBole](https://github.com/RUCAIBox/RecBole) for reproducing and developing recommendation algorithms based on graph neural networks (GNNs). Our library includes algorithms covering three major categories:
* **General Recommendation** with user-item interaction graphs;
* **Sequential Recommendation** with session/sequence graphs;
* **Social Recommendation** with social networks.

### 1）Highlights

* **Easy-to-use and unified API**:
    Our library shares unified API and input (atomic files) as RecBole.
* **Efficient and reusable graph processing**:
    We provide highly efficient and reusable basic datasets, dataloaders and layers for graph processing and learning.
* **Extensive graph library**:
    Graph neural networks from widely-used library like [PyG](https://github.com/pyg-team/pytorch_geometric) are incorporated. Recently proposed graph algorithms can be easily equipped and compared with existing methods.

### 2）Implemented Models

We list currently supported models according to category:

**General Recommendation**:

* **[NGCF](recbole_gnn/model/general_recommender/ngcf.py)** from Wang *et al.*: [Neural Graph Collaborative Filtering](https://arxiv.org/abs/1905.08108) (SIGIR 2019).
* **[LightGCN](recbole_gnn/model/general_recommender/lightgcn.py)** from He *et al.*: [LightGCN: Simplifying and Powering Graph Convolution Network for Recommendation](https://arxiv.org/abs/2002.02126) (SIGIR 2020).
* **[SGL](recbole_gnn/model/general_recommender/sgl.py)** from Wu *et al.*: [Self-supervised Graph Learning for Recommendation](https://arxiv.org/abs/2010.10783) (SIGIR 2021).
* **[HMLET](recbole_gnn/model/general_recommender/hmlet.py)** from Kong *et al.*: [Linear, or Non-Linear, That is the Question!](https://arxiv.org/abs/2111.07265) (WSDM 2022).
* **[NCL](recbole_gnn/model/general_recommender/ncl.py)** from Lin *et al.*: [Improving Graph Collaborative Filtering with Neighborhood-enriched Contrastive Learning](https://arxiv.org/abs/2202.06200) (TheWebConf 2022).
* **[SimGCL](recbole_gnn/model/general_recommender/simgcl.py)** from Yu *et al.*: [Are Graph Augmentations Necessary? Simple Graph Contrastive Learning for Recommendation](https://arxiv.org/abs/2112.08679) (SIGIR 2022).

**Sequential Recommendation**:

* **[SR-GNN](recbole_gnn/model/sequential_recommender/srgnn.py)** from Wu *et al.*: [Session-based Recommendation with Graph Neural Networks](https://arxiv.org/abs/1811.00855) (AAAI 2019).
* **[GC-SAN](recbole_gnn/model/sequential_recommender/gcsan.py)** from Xu *et al.*: [Graph Contextualized Self-Attention Network for Session-based Recommendation](https://www.ijcai.org/proceedings/2019/547) (IJCAI 2019).
* **[NISER+](recbole_gnn/model/sequential_recommender/niser.py)** from Gupta *et al.*: [NISER: Normalized Item and Session Representations to Handle Popularity Bias](https://arxiv.org/abs/1909.04276) (GRLA, CIKM 2019 workshop).
* **[LESSR](recbole_gnn/model/sequential_recommender/lessr.py)** from Chen *et al.*: [Handling Information Loss of Graph Neural Networks for Session-based Recommendation](https://dl.acm.org/doi/10.1145/3394486.3403170) (KDD 2020).
* **[TAGNN](recbole_gnn/model/sequential_recommender/tagnn.py)** from Yu *et al.*: [TAGNN: Target Attentive Graph Neural Networks for Session-based Recommendation](https://arxiv.org/abs/2005.02844) (SIGIR 2020 short).
* **[GCE-GNN](recbole_gnn/model/sequential_recommender/gcegnn.py)** from Wang *et al.*: [Global Context Enhanced Graph Neural Networks for Session-based Recommendation](https://arxiv.org/abs/2106.05081) (SIGIR 2020).
* **[SGNN-HN](recbole_gnn/model/sequential_recommender/sgnnhn.py)** from Pan *et al.*: [Star Graph Neural Networks for Session-based Recommendation](https://dl.acm.org/doi/10.1145/3340531.3412014) (CIKM 2020).

**Social Recommendation**:

* **[DiffNet](recbole_gnn/model/social_recommender/diffnet.py)** from Wu *et al.*: [A Neural Influence Diffusion Model for Social Recommendation](https://arxiv.org/abs/1904.10322) (SIGIR 2019).
* **[MHCN](recbole_gnn/model/social_recommender/mhcn.py)** from Yu *et al.*: [Self-Supervised Multi-Channel Hypergraph Convolutional Network for Social Recommendation](https://doi.org/10.1145/3442381.3449844) (WWW 2021).
* **[SEPT](recbole_gnn/model/social_recommender/sept.py)** from Yu *et al.*: [Socially-Aware Self-Supervised Tri-Training for Recommendation](https://doi.org/10.1145/3447548.3467340) (KDD 2021).

## [RecBole-TRM](https://github.com/RUCAIBOX/RecBole-TRM)

