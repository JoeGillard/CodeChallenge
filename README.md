# Code challenge: self-supervised learning and embeddings generation
## Introduction
This repository contains the code to solve a challenge involving a self-supervised learning task involving pet images. 
## Contents of repo
This repo contains the following items:
* 

## General approach
To address this challenge, the following approach was taken:
* A pre-trained encoder was customised, closely following the approach of [Chen et al. (2020), A Simple Framework for Contrastive Learning of Visual Representation](https://arxiv.org/abs/2002.05709), i.e. the SimCLR approach.
* SimCLR was used to conduct semi-supervised training of this custom model, using augmented versions of the data without labels.
* After the SimCLR step, the projection head was discarded, the encoder and its weights was retained, and a new 3-class classifier was added. 
* The predictive performance of the new model was evaluated by fine-tuning in the context of 5-fold cross-validation, using training data with labels.
* The model was then fine-tuned on the full labelled dataset.
* The performance of the fine-tuned model was evaluated on a hold-out, unseen test set of labelled data.
* An embedding of the model output in a 2D feature-space was demonstrated.
