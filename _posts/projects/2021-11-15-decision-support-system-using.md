---
layout: inner
position: left
title: PsychiatristHelp
date: 2021-02-20 15:56:00
categories: test
tags: Machine-Learning Eye-tracker Deep-Distance-Learning
featured_image: '/assets/decision_support_system/Proposed-system.png'
project_link: 'http://github.com/jamigibbs/weathercast'
button_icon: 'github'
button_text: 'Visit Project'
lead_text: 'A Diagnosis Support System to Identify Developmental Disorder Symptoms in Children'
---


## Gaze Behavior of Children with ASD Symptoms

What do you think about gaze behavior of typical children and their peers with autism symptoms when you see Vid. 1?

<div style="text-align: center;"><iframe width="560" height="315" src="https://www.youtube.com/embed/8VkFBsE3c14" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div>

As seen in previous works, we observed that gaze allocation of typical and ASD children did not differ. The latter’s gaze modulation, however, was more chaotic than the former. The results may indicate that children with ASD symptoms over-interpreted the information of a stimulus, causing more unintentional viewing behavior.

Respectively, we proposed to use entropy based measurement in measuring children’s gaze behavior to identify developmental disorder symptoms in them. We also computed their performance when they played a game version of Go/NoGo task to understand whether typical children’s response differs from their ASD peers or not.

## A Significant Difference

Employing the extracted features, we performed statistical comparison with Student t and Man-Whitney u test. The results suggested a significant difference between typical and ASD children in their gaze modulation, which was showed by 

1. greater value of ASD group’s fixation time,

2. gaze movement acceleration, and

3. entropy of distance between stimulus and their gaze positions.



{% include image.html url="/assets/decision_support_system/Summary-significant-features.png" description="<b>Fig 1.</b> Features in which typical and ASD groups differed significantly." %}


## A Substantial Difference

Not only less predictable gaze modulation, we also found response time variance and percentage of Go-error response were greater in ASD group than in typical subjects.

{% include image.html url="/assets/decision_support_system/Summary-insignificant-features.png" description="<b>Fig 1.</b> Features in which typical and ASD groups differed significantly." %}

