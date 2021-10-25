---
layout: inner
title: Publications
permalink: /publications/
---



### **Markerless Human Activity Recognition Method Based on Deep Neural Network Model Using Multiple Cameras**

[[pdf](/assets/pdfs/markerless_human_activity_recognition.pdf)][<a href="https://github.com/gitarja/HumanActivityRecognition">source code</a>]

**Conference: 2018 5th International Conference on Control, Decision and Information Technologies (CoDIT)**

**Abstract:** Most methods of multi-view human activity recognition can be classified as conventional computer vision approaches. Those approaches separate feature descriptor and discriminator. Hence, the feature extractor cannot learn from the mistakes made by the classifier. In this paper, a deep neural network (DNN) model for human activity estimation using multi-view sequences of raw images is presented. This approach incorporates features extractor and discriminator into a single model. The model comprises three parts, a convolutional neural network (CNN) block, MSLSTMRes, and a dense layer. This method enables discrimination of human activity such as “walk” and “sit down” by merely using sequences of raw images. Experimental results on IXMAS dataset using one-subject cross validation demonstrates high prediction rate that is comparable to other methods in the literature, which utilized preprocessed images such as silhouette and volumetric data and sophisticated feature extractor.

### **A Framework of Human Emotion Recognition Using Extreme Learning Machine**

[[pdf](/assets/pdfs/a_framework_of_human_emotion.pdf)][source code]

**Conference: 2014 1st International Conference on Advanced Informatics: Concepts, Theory, and Applications**

**Abstract:** Human emotion recognition has been challenging issue in field of human-computer interaction. In order to form an interaction that is more natural between human and computer , the computer should be able to discern and respond to human emotion. In this paper, an approach for recognizing human emotion is proposed. The proposed approach operates HAAR-classifier to detect mouth, eyes, and eyebrow on face, and, to extract features from them, it uses Gabor wavelet. Before classifying the features, PCA is performed to reduce its dimension. The proposed framework employs SLFNs with ELM as its learning algorithm to classify the features. In this experimental, the proposed framework is tested in two cases, personalize and generalize face case, with ten subjects expressing six basic emotions and neural state. The robustness of ELM is evaluated with comparing it to K-NN and SVM. Preliminary experiment shows that the proposed approach has promising performance in personalize face case.

### **Catchicken: A Serious Game Based on the Go/NoGo Task to Estimate Inattentiveness and Impulsivity Symptoms**

[pdf][<a href="https://github.com/gitarja/AttentionAnalysis">source code</a>]

**Conference: 2020 IEEE 33rd International Symposium on Computer-Based Medical Systems (CBMS)**

**Abstract:** We present a Go/NoGo 3D game equipped with an eye tracker that records subjects' responses and his gaze position on the monitor over time. The proposed system consists of two functions: training that allows an instructor to modify the game's parameters and make a customized test; and evaluation in which the instructor can fix the parameters to create a standardized test. During the experiment, subjects were required to respond only to Go character by pressing a spacebar. The experimental results from 59 participants demonstrated that one's response time and its variability correlated with one's gaze behavior. Subjects with higher gaze modulation tended to respond faster and more stable. We also observed that utilizing the proposed system we could monitor the improvements in an Autism Spectrum Disorder child during his rehabilitation: his gaze modulation increased and his response time became more steady. In brief, utilizing the proposed system, we could effectively measure participants' response time variability of NoGo errors and their gaze trajectory area, which previous studies found to have a strong relationship with symptoms of mental disorders.

### **Identifying Autism Spectrum Disorder Symptoms Using Response and Gaze Behavior during the Go/NoGo Game CatChicken**

[pdf][<a href="https://github.com/gitarja/AttentionAnalysis">source code</a>]

**Under Revision in Scientific Reports**

**Abstract:** Previous studies have found that Autism Spectrum Disorder (ASD) children scored lower during a Go/No-Go task and faced difficulty focusing their gaze on the speaker's face during a conversation. To date, however, there has not been an adequate study examining children's response and gaze during the Go/No-Go task to distinguish ASD from typical children. We investigated typical and ASD children's gaze modulation when they played a version of the Go/No-Go game. The proposed system represents the Go and the No-Go stimuli as chicken and cat characters, respectively. It tracks children's gaze using an eye tracker mounted on the monitor. Statistically significant between-group differences in spatial and auto-regressive temporal gaze-related features for 21 ASD and 31 typical children suggest that ASD children had more unstable gaze modulation during the test. Using the features that differ significantly as inputs, the AdaBoost meta-learning algorithm attained an accuracy rate of 88.6% in differentiating the ASD subjects from the typical ones.


### **Markerless Behavior Monitoring System for Diagnosis Support of Developmental Disorder Symptoms in Children**

[pdf][source code]

**Conference: 2021 21st International Conference on Control, Automation and Systems (ICCAS)**

**Abstract:** This study presents a markerless behavior evaluation system employing multiple RGB cameras and Kinect V2 sensors to assists clinicians in identifying disorder symptoms in children.  The system utilizes OpenPTrack with Kinect sensors to track children’s and toys’ positions and records their activity using RGB cameras. Children’s activity wasestimated by computing the distance between them and the toys. Children’s behavior was modeled with a Petri net, and four features were extracted from the model.  We conducted preliminary experiments with four typical and three ASD disorder children. The experimental results demonstrated that the frequency of changing activity and playing alone wasmore informative than the others to distinguish ASD children from the typical ones.