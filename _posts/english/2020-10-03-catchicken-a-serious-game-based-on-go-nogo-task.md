---
title: Catchicken a Serious Game Based on Go/NoGo Task
undefined: SUB TITLE
date: 2020-10-09 12:56:54 +0000
ttitle: Catchicken A serious Game Based on Go/NoGo Task
tag: []
categories: english

---

## What is Catchicken?

**Catchicken** is a serious game based on Go/NoGo task that we utilized in our research to measured children response and their gaze behavior during the task. The game represented the Go stimulus and NoGo stimulus as "cat" and "chicken" characters, respectively. So, a child should response only when the cat appeared but he must inhibit his action when the chicken appeared.

## What does matter with children's response and gaze behavior?
Attention Deficit Hyperactive Disorder (ADHD) and Autism Spectrum Disorder (ASD) are examples of invisible disorder whose symptoms often misinterpreted as wilful misconduct or bad character. The children with disorder, however, need early intervention to mitigate the disorder symptoms.

Previous works found that ADHD children's **response time was slower and more varied** compared to the typical one during Go/NoGo task. They also discovered that children with ASD **could not focus** on the conversant's face during face-to-face conversation and **often got distracted with the surronding**.

Hence, we thought that measuring those features may help teachers and clinicians to identify disorders symptoms in early childhood. Also, we hope that we can utilize this system to monitor the disorder children's performance during attention and impulsivity rehabilitation.

## How does the system measure the children's response and gaze behavior?
Our proposed system comprises **game and results interfaces**. We build the game interface using Unity and represents the Go and the NoGo stimulus as chicken and cat characters, respectively. So the user should respond only when the chicken character appears by pressing space bar. The character appears randomly but uniformly at one of nine locations that are represented by red flowers. The system categorizes the user's response into four types: **Go positive** if the user reacts towards Go stimulus; **NoGo positive** if he does not react toward it; **Go negative** if he missess the Go stimulus; and **NoGo negative** if he incorrectly responds towards NoGo stimulus.

{% include image.html url="/assets/attention_test/BG.png" description="<b>Fig 1.</b> The nine locations in which a stimulus can appear." %}
<br/>
<div class="row">
  <div class="column">
{% include image.html url="/assets/attention_test/Chicken.png" description="<b>Fig 2.</b> The Chicken character represents the Go stimulus." %}
  </div>
  <div class="column">
{% include image.html url="/assets/attention_test/Cat.png" description="<b>Fig 3.</b> The Cat character represents the NoGo stimulus." %}
  </div>
 </div>

<br/>
During training, the intsructor can modify the propotion of the stimulus, their appearance time, and the waiting time between two consequitive stimulus. During evaluation, however, the instructor can fix those parameters to create a standarized test. Incorporating Tobii eye tracker, we allow the game to track the user's gaze continously.

**Result interface** shows the user's performance and gaze area after he finish playing the game, so the instructor can assess how much the response and the gaze behavior of the user differs from the typical group. The user's performance includes: correct response (Go positive and NoGo positive), Error response (NoGo negative), Miss (Go negative), and their response time and response time variance.

{% include image.html url="/assets/attention_test/resultInterface_new.png" description="<b>Fig 4.</b> Results interface of our proposed system." %}

<br/>
We also display the detail of the user performance and his gaze area for every minute on the interface. The system compute the gaze area utilizing Convex hull algorithm whose value ranges from 0 to 1.



## What have we found until now?
