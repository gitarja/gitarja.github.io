---
title: Implementing Hierarchical RNN for Skeleton Based Action Recognition Using Tensorflow 2
undefined: SUB TITLE
date: 2017-03-26 12:56:54 +0000
ttitle: Implementing Hierarchical RNN for Skeleton Based Action Recognition Using Tensorflow 2
tag: []
categories: english

---

Human action recognition is one of challenging issue in Computer Vision (CV) that predicts actions of one or more subjects based on sequence of images. We have seen many approaches have been proposed for this issue that can be categorized into two categories: conventional CV dan DNN approaches. Conventional CV method separates feature extractor and classifier. While DNN approaches employ data representation learning to figure out the features and pattern in the data.

In this article, we will implement hybrid method proposed in this paper. Instead of using raw images, the authors extracted sequence of skeleton from the images and feeded it to hierarchical RNN. The architecture comprises nine layers that is depicted in Fig.1 . The architecture comprises seven layers to extract representation of human body parts and combine them hierarchically and two layers to classify the actions.