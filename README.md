# Shopping-recommendation-algorithm-based-on-knowledge-graph-and-dynamic-association-graph-model-
A repository for implementing and reproducing the Shopping recommendation algorithm based on knowledge graph and dynamic association graph model

## Abstract
With the maturation of deep learning and big data technologies, the application of recommendation algorithms can help e-commerce platforms acquire new users and enhance conversion rates. This paper proposes a novel e-commerce recommendation algorithm, which is based on a combination model of knowledge graphs and dynamic association graphs and is designed in two stages: offline and online. In the offline stage: Firstly, a knowledge graph attention network is built based on the features of product attributes and consumers' historical shopping behaviour, thereby obtaining key feature attributes of the products. Secondly, a dynamic association graph network is built by connecting the consumer behaviour sequence with a dynamic graph structure, and key features of the selection behaviour are obtained successively through a Graph Convolutional Neural Network (GCN), a Gated Recurrent Unit (GRU), and an attention mechanism. Thirdly, the output features are fused to generate a recommendation list. On the online stage, the algorithm records the consumer's shopping path, updates the database and dynamic association graph, and can automatically adjust according to the shopping path. Experiments on three Amazon datasets demonstrate that the algorithm exhibits superior recommendation performance and robustness in actual online shopping scenarios with complex association features.
## Overview of ORKDG framework
In this section, the ORKDG algorithm is introduced, and its general framework is shown in Figure. This system consists of the following four parts. 1) Online tuning module: After prepossessing the characteristics of consumer purchasing behaviour, the database and dynamic association graph are updated. 2) Collaborative knowledge graph Neural Network: This module constructs a collaborative knowledge graph and a knowledge graph attention network in the combined model. 3) Dynamic association graph neural network: A dynamic association graph neural network is constructed in the composite model, and the message-passing mechanism and update method are introduced. 4) Prediction layer: This module fuses the user and item features obtained in the combined model. Finally, the predicted preference score was calculated according to the obtained fusion information.
<div align="center">
  <img width="544" height="427" alt="image" src="https://github.com/user-attachments/assets/352003d3-d53e-47a4-bdc1-0ea1e37bd0bc" />
</div>

## 📑 Todo List
  - [ ] 1. Open source code for reproducing the experiment
  - [ ] 2. Open source preprocessing and training code
  - [ ] 3. Future online optimization

