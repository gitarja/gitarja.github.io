---
title: Catchicken a Serious Game Based on Go/NoGo Task
undefined: SUB TITLE
date: 2020-10-09 12:56:54 +0000
ttitle: Catchicken A serious Game Based on Go/NoGo Task
tag: []
categories: english

---

## What is Catchicken?

**Catchicken** is a serious game based on the Go/NoGo task that we utilized in our research to measured children's response and their gaze behavior during the task. The game represented the Go stimulus and NoGo stimulus as "cat" and "chicken" characters, respectively. So, a child should respond only when the cat appeared, but he must inhibit his action when the chicken appeared.

## What does matter with children's response and gaze behavior?
Attention Deficit Hyperactive Disorder (ADHD) and Autism Spectrum Disorder (ASD) are examples of invisible disorder whose symptoms are often misinterpreted as willful misconduct or bad character [1]. The children with the disorder, however, need early intervention to mitigate the disorder symptoms.

Previous works found that ADHD children's **response time was slower and more varied** compared to the typical one during the Go/NoGo task [2]. They also discovered that children with ASD **could not focus** on the conversant's face during face-to-face conversation and **often got distracted with the surronding** [3].

Hence, we thought that by utilizing those features we can identify the possibility of a child having a disorder, thereby allowing clinicians to make further investigation of him. Also, we hope that we can utilize this system to monitor the disorder children's performance during attention and impulsivity rehabilitation.

## How does the system measure the children's response and gaze behavior?
Our proposed system comprises **game and results interfaces**. We build the game interface using Unity and represent the Go and the NoGo stimulus as chicken and cat characters, respectively. So the user should respond only when the chicken character appears by pressing the space bar. The character appears randomly but uniformly at one of nine locations that are represented by red flowers. The system categorizes the user's response into four types: **Go positive** if the user reacts towards Go stimulus; **NoGo positive** if he does not react toward it; **Go negative** if he misses the Go stimulus; and **NoGo negative** if he incorrectly responds towards NoGo stimulus.

<div style="text-align: center;"><iframe width="560" height="315" src="https://www.youtube.com/embed/LFQNXBAqEfY" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div>

<br/>
During training, the instructor can modify the proportion of the stimulus, their appearance time, and the waiting time between two consecutive stimuli. During the evaluation, however, the instructor can fix those parameters to create a standardized test. Incorporating the Tobii eye tracker, we allow the game to track the user's gaze continuously.

Result interface shows the user's performance and gaze area after he finishes playing the game, so the instructor can assess how much the response and the gaze behavior of the user differ from the typical group. The user's performance includes correct response (Go positive and NoGo positive), Error response (NoGo negative), Miss (Go negative), and their response time and response time variance.

{% include image.html url="/assets/attention_test/resultInterface_new.png" description="<b>Fig 1.</b> Results interface of our proposed system." %}

<br/>
We also display the detail of the user performance and his gaze area for every minute on the interface. The system compute the gaze area utilizing Convex hull algorithm whose value ranges from 0 to 1.



## What have we found until now?
We observed two interesting findings in our preliminary results involving healthy 59 participants [4]. First, we found that participants tend to **react faster when they responded incorrectly towards the NoGo stimulus**. The variance of the response time was also higher compared to when they responded correctly towards the Go stimulus. Second, we noticed a positive relationship between participants' gaze area and their response time and response time variance. In brief, the participants with **a bigger gaze area tended to respond slower with higher variance**.

{% include image.html url="/assets/attention_test/Correlation_table.png" description="<b>Fig 2.</b> The average of response time and respons time variance." %}

In addition, our clustering results with K-means suggested that there may be two groups among the participants. The first group was the subjects who respond **faster and more stable**.

{% include image.html url="/assets/attention_test/RT-RTVar.png" description="<b>Fig 3.</b> The average of respons time and response time variance of each cluster." %}



The subjects that belong to this cluster had gaze distribution that **concentrated on the center of the screen**. The members of the second cluster, however, tended to respond slower with higher variance. Their gaze distribution also was more **dispersed over the screen**, thereby having a bigger gaze area.

{% include image.html url="/assets/attention_test/cluster1_group.png" description="<b>Fig 4.</b> The gaze distribution of participants belong to the first cluster." %}

{% include image.html url="/assets/attention_test/cluster2_group.png" description="<b>Fig 5.</b> The gaze distribution of participants belong to the second cluster." %}

## Next?
This study proposed a system that can identify symptoms relating to invisible disorders in early childhood. We intend to measure the response and gaze behavior of typical and disorder children. The results from the preliminary experiment suggest that how the participant responds and how their gaze behavior may relate. Also, the results imply that how typical and disorder move their gaze towards the stimulus may differ.

## Where can I download the software?
You can download [here](https://sourceforge.net/projects/catchicken/ ). Please contact me if you have any questions or troubles when installing the software.

## References
1. American Psychiatric Association. Diagnostic and statistical manual of mental disorders (DSM-5®). American Psychiatric Pub, 2013.
2. Bezdjian, Serena, Laura A. Baker, Dora Isabel Lozano, and Adrian Raine. "Assessing inattention and impulsivity in children during the Go/NoGo task." British Journal of Developmental Psychology 27, no. 2 (2009): 365-383.
3. Swanson, Meghan R., and Michael Siller. "Patterns of gaze behavior during an eye-tracking measure of joint attention in typically developing children and children with autism spectrum disorder." Research in Autism Spectrum Disorders 7, no. 9 (2013): 1087-1096.
4. Putra, Prasetia, Keisuke Shima, and Koji Shimatani. "Catchicken: A Serious Game Based on the Go/NoGo Task to Estimate Inattentiveness and Impulsivity Symptoms." In 2020 IEEE 33rd International Symposium on Computer-Based Medical Systems (CBMS), pp. 152-157. IEEE, 2020. 
