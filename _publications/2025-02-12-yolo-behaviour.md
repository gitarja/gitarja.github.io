---
title: "YOLO-Behaviour: A simple, flexible framework to automatically quantify animal behaviours from videos"
collection: publications
category: manuscripts
permalink: /publication/2025-02-12-yolo-behaviour
excerpt: "A flexible YOLO-based framework for automated animal behaviour quantification."
date: 2025-02-12
venue: "Methods in Ecology and Evolution 16(4)"
citation: "Chan, A.H.H., Putra, P., Schupp, H., Köchling, J., Straßheim, J., Renner, B., et al. (2025). YOLO-Behaviour. *Methods in Ecology and Evolution*, 16(4), 760–774."
---

Manually coding behaviours from videos is essential to study animal behaviour but it is labour-intensive and susceptible to inter-rater bias and reliability issues. Recent developments of computer vision tools enable the automatic quantification of behaviours, supplementing or even replacing manual annotation. However, widespread adoption of these methods is still limited, due to the lack of annotated training datasets and domain-specific knowledge required to optimize these models for animal research.
Here, we present YOLO-Behaviour, a flexible framework for identifying visually distinct behaviours from video recordings. The framework is robust, easy to implement, and requires minimal manual annotations as training data. We demonstrate the flexibility of the framework with case studies for event-wise detection in house sparrow nestling provisioning, Siberian jay feeding, human eating behaviours and frame-wise detections of various behaviours in pigeons, zebras and giraffes.
Our results show that the framework reliably detects behaviours accurately and retrieve comparable accuracy metrics to manual annotation. However, metrics extracted for event-wise detection were less correlated with manual annotation, and potential reasons for the discrepancy between manual annotation and automatic detection are discussed. To mitigate this problem, the framework can be used as a hybrid approach of first detecting events using the pipeline and then manually confirming the detections, saving annotation time.
We provide detailed documentation and guidelines on how to implement the YOLO-Behaviour framework, for researchers to readily train and deploy new models on their own study systems. We anticipate the framework can be another step towards lowering the barrier of entry for applying computer vision methods in animal behaviour.