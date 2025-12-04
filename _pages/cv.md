---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

Education
======
* Doctor of Electrical and Computer Engineering, 2022, Yokohama National University, Japan
* Master of Electrical and Computer Engineering, 2019, Yokohama National University, Japan
* Bachelor of Informatics Engineering and Education, 2015, Universitas Negeri Jakarta, Indonesia

Work experience
======
* May 2022 - present: Postdoctoral fellowship
  * University of Konstanz
  * Lead a project of reverse engineering of human coordination
  * Duties includes: setting up multimodal physiological signal lab, designing experiment and writing ethics proposal, disseminating research results.
  * Collaborator: Fumihiro Kano, Harald T. Schupp, and Britta Renner

* April 2019 - March 2022: Doctoral researcher
  * Yokohama National University
  * Lead a project of diagnostic support sytem to identify Autism Spectrum Disorder Symptom in children
  * Manage and coordination collaboration project with Yamaha Motor Company to develop wearable system to estimate affect state
  * Duties includes: conducting experiment, disseminating research results, organizing logistic for experiments.
  
* Februari 2021: Research internship
  * Sony Japan
  * Develop a deep learning model to estimate affect state using facial landmark and images.
  
Skills
======
* Machine learning & AI:
  * Supervised/unsupervised learning
  * Deep learning (CNNs, Siamese networks)
  * Model evaluation (MCC, Jaccard, SHAP, feature importance)
  * Bayesian modeling (PyMC, Bambi, Bayesian Adaptive Trees)
  * Mixture-of-experts, ensemble methods
* Multimodal data acquisition: Motion capture, wearable eye-tracking (Tobii, Pupil Labs), ECG, GSR, EMG, synchronized multi-camera systems
* Signal processing: Physiological signal preprocessing (ECG, GSR, EMG), time-series analysis, event detection
* Statistical analysis: Hierarchical regression, mixed models, Bayesian inference, generative modeling
* Experimental design: Behavioral experiments, psychophysiology studies, child–adult interaction studies
* Data management: High-volume data pipelines, HPC cluster usage, data synchronization & cleaning
* Programming language: Python, C++, C#

Publications
======
  <ul>{% for post in site.publications reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
  
Talks
======
  <ul>{% for post in site.talks reversed %}
    {% include archive-single-talk-cv.html  %}
  {% endfor %}</ul>
  
Teaching
======
  <ul>{% for post in site.teaching reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
  
Service and leadership
======
### Reviewing Experiences
- COSMOS Summer School  
- COGAIN  
- Scientific Reports  
- MDPI Animals  
- ACM Transactions on Human–Robot Interaction  
- Data in Brief  

### Professional Memberships and Community Service
- Program co-Chair COGAIN (2026)
- Member of the Gaze Interaction (COGAIN) Symposium (2024–present)  
- Organized a two-day Deep Reinforcement Learning workshop at the University of Konstanz (September 27–28, 2023)  
- Volunteer moderator during the CASCB Research Workshop with the University of Essex (2022)