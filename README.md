# One-shot-learning-thesis
# StoreNet
Learn from storepal images from previous loyalty programs to train a new neural net quickly for a new loyalty program

This repo represents the code of Wiebe Vossen's thesis on one-shot learning.

<i>StoreNet: An Application of One-Shot Learning on Point-of-Sale Materials from Loyalty Programs</i>

<b>Abstract</b>

Humans are able to recognise new patterns after seeing one or more examples. In the era of deep learning, computers are able to recognise many concepts. The downside is that it requires 1000s of images to train a classifier to recognise concepts. One-shot learning can reduce data hungriness for retraining a classifier to one or a few images. The objective of this thesis is to research to what extent one-shot learning reduces data hungriness as compared to transfer learning. The task of the classifier is to recognise in-store marketing material from loyalty programs held in supermarkets. With StoreNet, we implement state-of-the-art siamese neural networks and meta-learning networks. Furthermore, we implement our own k-nearest neighbour-based noise reduction method. StoreNet reduces the data hungriness for recognising loyalty program marketing material from 450-2000 images per image class to 1-30 images per image class with an accuracy of 64%, whereas the transfer learning baseline achieves 78% accuracy. Our noise reduction method improves the accuracy for few-shot learning, (i.e. 5-10 samples) with 2-5 percentage points. Despite transfer learning outperforming one-shot learning in terms of accuracy, one-shot learning is favourable when availability of labelled images is limited.

Keywords: one-shot learning, loyalty programs, siamese neural networks, meta-learning, retail

Contact: www.wiebevossen.com

## How-to-use

### Experiments
All experiments are located in the folder [thesis](thesis). Two main experiments have been done. The first one is metric learning where a triplet network is used which can be found in [Siamese network](thesis/siamese_own_implementation/). The second experiment is the application of [meta-learning networks](thesis/few-shot). Three different networks have been applied: matching networks, prototypical networks and model-agnostic meta-learning (MAML) networks.
For visualisation of the siamese network, t-SNE is used. This can be found in [TSNE-Embedding-Visualisation](thesis/TSNE-Embedding-Visualisation).

### Train
With the notebook [train_siamese.ipynb](thesis/siamese_own_implementation/train_siamese.ipynb) a siamese neural network can be trained. In specific a triplet network. The weights are saved per epoch. In our case the network is trained on IN32 and evaluated on IN32. 

### Evaluate
With [Demo.ipynb](thesis/siamese_own_implementation/Demo.ipynb) an evaluation of the trained siamese neural network can be run. This can be done on a custom dataset where each image class can be saved in a separate folder in the folder demo_data.
