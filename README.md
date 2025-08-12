# Shopping-recommendation-algorithm-based-on-knowledge-graph-and-dynamic-association-graph-model-
A repository for implementing and reproducing the Shopping recommendation algorithm based on knowledge graph and dynamic association graph model

## Abstract
With the maturation of deep learning and big data technologies, the application of recommendation algorithms can help e-commerce platforms acquire new users and enhance conversion rates. This paper proposes a novel e-commerce recommendation algorithm, which is based on a combination model of knowledge graphs and dynamic association graphs and is designed in two stages: offline and online. In the offline stage: Firstly, a knowledge graph attention network is built based on the features of product attributes and consumers' historical shopping behaviour, thereby obtaining key feature attributes of the products. Secondly, a dynamic association graph network is built by connecting the consumer behaviour sequence with a dynamic graph structure, and key features of the selection behaviour are obtained successively through a Graph Convolutional Neural Network (GCN), a Gated Recurrent Unit (GRU), and an attention mechanism. Thirdly, the output features are fused to generate a recommendation list. On the online stage, the algorithm records the consumer's shopping path, updates the database and dynamic association graph, and can automatically adjust according to the shopping path. Experiments on three Amazon datasets demonstrate that the algorithm exhibits superior recommendation performance and robustness in actual online shopping scenarios with complex association features.
## Overview of ORKDG framework
In this section, the ORKDG algorithm is introduced, and its general framework is shown in Figure. This system consists of the following four parts. 1) Online tuning module: After prepossessing the characteristics of consumer purchasing behaviour, the database and dynamic association graph are updated. 2) Collaborative knowledge graph Neural Network: This module constructs a collaborative knowledge graph and a knowledge graph attention network in the combined model. 3) Dynamic association graph neural network: A dynamic association graph neural network is constructed in the composite model, and the message-passing mechanism and update method are introduced. 4) Prediction layer: This module fuses the user and item features obtained in the combined model. Finally, the predicted preference score was calculated according to the obtained fusion information.
<div align="center">
  <img alt="image" src="assets\ORKDG.png" />
</div>

## 📑 Todo List
  - [ ] 1. Open source code for reproducing the experiment ( four weeks)
  - [ ] 2. Open source preprocessing and training code
  - [ ] 3. Future online optimization


## Experimental Objectives
RQ1: How does ORKDG perform in terms of performance compared to state-of-the-art recommendation methods?

RQ2: What is the respective effectiveness of the two networks in the combined ORKDG model?

RQ3: What is the impact of different hyper-parameter settings on ORKDG, and how does it compare to baseline methods?

## Abstract Dataset
To evaluate the performance of ORKDG, this section chooses to use. Three benchmark datasets: Amazon-CDs, Amazon-Games and Amazon-Beauty, these datasets are widely used to evaluate recommendation algorithms, all of which have their characteristics; these three datasets contain rich user behavior data and cover a wider range of people. The Amazon-CDs datasets has longer sequences, while the Amazon-Beauty datasets covers the widest range of product categories. This diversity helps validate the effectiveness of the algorithm on different datasets.
The selected data set contains the source ID and target ID of the interaction, as well as the timestamp and specific date of the interaction. In the data preprocessing stage, the data rows with fewer than 5 interactions are deleted, and the statistics of the processed data are shown in Table

| Dataset      | Beauty  | Games   | CDs     |
|--------------|---------|---------|---------|
| Items        | 57,295  | 23,718  | 35,118  |
| Interactions | 394,918 | 287,117 | 472,275 |
| Avg. Length  | 7.6     | 9.3     | 27.5    |
| Density      | 0.01%   | 0.03%   | 0.07%   |

## Hyperparameter settings
In light of the experimental outcomes pertaining to RQ3, this manuscript specifies the following configurations to achieve optimal performance: all embedding dimensions are unified at 64, the maximum sequence length is capped at 50, and the architecture comprises 4 network layers. Comparatively, the Adam optimizer was observed to achieve convergence more rapidly than SGD. The learning rate is established at 0.01, with a consistent batch size of 50 across experiments. Model parameters are initialized employing the default Xavier method, which selects weights from a uniform distribution and determines the weight range based on the dimensionality. For the methods under comparison, the default hyper-parameters are utilized, complemented by the specified dimensionalities.


