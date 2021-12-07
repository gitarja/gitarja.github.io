---
layout: inner
position: left
title: myCondifant (UX Research)
date: 2021-02-20 15:56:00
categories: project
tags: UX-Research Mental-Health
featured_image: '/assets/myconfidant/Home-screen.png'
project_link: 'http://github.com/jamigibbs/weathercast'
button_icon: 'github'
button_text: 'Visit Project'
lead_text: 'myConfidant: an app to meet your therapists'
---

### Why I conduct this research?

How often do you feel distressed when you must face things you never imagine? Today’s society changes rapidly and demands us to adapt to new conditions quickly. For example, nowadays, getting a job requires you to have skills that you never heard from or imagined in your high-school.

However, because of the increase in maintaining well-being, people become more frequent to seek help from psychiatrists. But, because of stigma, complicated procedure, unaffordable price, and distrust to share private matters, many of them give up to visit and consult with therapists.

myConfidant is here to help people meet with their therapist. With the app, users can search therapists that match their criteria, select the one that they like, and arrange the schedule with the therapist through smartphone in 5 minutes.



### Problems

1. Many people do not know how to find therapists.
2. People have different preference in communicating with therapists.

### Goals
1. **Discover:** the paint points to find and arrange schedule with therapists
2. **Discover:** users' preference on how they want to counsult with their therapists


### Summary of the study
I conduct secondary and primary research to find what kinds of features that users need in customer service app for therapist. The main users are clients who want to use therapists’ service. Therapists can upload detail of their education background, experience, and schedule to app.

> The study focuses on understanding pain points of “prospective” clients and people who already have regular consultation with therapist. I designed the questions to explore the users’ experience with therapists and their expectation to make an appointment and communicate with the therapists.

### Methodology

To achieve those goals, I interviewed nine participants whose age was from 18 to 35. All of them lived in suburban and metropolitan cities and ever experienced stressful condition in their work or school. They lived in four different countries (5 in Japan, 1 in Australia, 1 in Indonesia, 1 in the USA, and 1 in Nigeria).

<!--
### Scripts

Hi, how is your day?
Before we begin this interview, would you mind if I take audio of this interview?

I want you to know that this is not a test, so there are no right or wrong answers in this interview. If you have any questions, I will be happy to hear about them. I will use this interview to design an app to find therapists and arrange schedule with them.


**Prompt-1:**

1. Have you experienced stressful conditions that affect your well-being? (e.g., you cannot sleep because of work pressure)

2. Have you thought of going to a therapist?

**Prompt-2:**

1. Would you mind sharing with me about your stressful condition?
2. Did you ever go to a therapist to discuss your mental health condition?
 - Yes: How do you find and why do you choose that therapist?
 - No: What makes you put aside the idea of going to a therapist?
3. Could you describe what you think is the most convenient way to make an appointment with the therapist?
 - How do you think if you feel calmer, will you cancel the appointment?
  - Yes: what do you think about cancellation fee?
  - No: why you do not want to cancel it?
4. Are you more comfortable discussing with your therapist in face-to-face conversation or phone calls?
 - Can you tell me the reason for it?
  - Have u ever used AI-boot to chat?
5. Do you think you need to communicate daily with the therapist?
6. If you want to give feedback to a therapist? How will you do that?
-->
### Sentiment Analysis

I performed sentiment analysis using Google NLP and found that **WORK** and **RELATIONSHIP** had negative sentiment and became participants’ main reason for stress. They also thought that asking for help from other people was not helpful.

The good thing I found was that many participants were eager to make an appointment with therapists through apps (**sentiment score: 0.6**) and to have face-to-face consultation with them. Another surprising finding was that most participant had negative sentiment (**score: -0.8**) towards AI-bot as they think AI cannot understand human’s complex emotion.




### Paint Points
I observed four pain points of participants from the interview.

{% include image.html url="/assets/myconfidant/Pain-points.png"%}


### Personas

**Robi's problem statment**

Robi is a shy researcher who needs an app to find affordable therapists and make an appointment privately because they do not have any experience but feel shy about asking their family and friends about it.

{% include image.html url="/assets/myconfidant/Robi-persona.png"%}


**Ayla's problem statment**

Ayla is a busy college student who needs an easy way to arrange an appointment with therapists because they often feel overwhelmed to go through complicated procedure.

{% include image.html url="/assets/myconfidant/Ayla-persona.png"%}


### User-flow
I create a user-flow describing the process to find therapists and arrange a session with them by referring to paint points and persona,. The process includes three steps:

1. Search therapists based on the user’s criteria
2. Pick a schedule for a session
3. Confirm the session and add it to the user’s calendar

{% include image.html url="/assets/myconfidant/User-flow.png"%}

### LF-Digital Wireframes
During ideating process of LF-Digital wireframe, I focused on prioritizing participants’ pain points in creating a simple but informative app to find therapists and arrange a session with them.

{% include image.html url="/assets/myconfidant/Home-screen.png"%}
{% include image.html url="/assets/myconfidant/Search-screen.png"%}
{% include image.html url="/assets/myconfidant/Scheduling-screen.png"%}
{% include image.html url="/assets/myconfidant/Therapists-screen.png"%}

### LF-Prototype
<iframe style="border: 1px solid rgba(0, 0, 0, 0.1);" width="800" height="450" src="https://www.figma.com/embed?embed_host=share&url=https%3A%2F%2Fwww.figma.com%2Fproto%2FecIRKgC2ZeDBWFLkQhHyBN%2FSearchAndBookTherapist%3Fnode-id%3D2%253A2%26scaling%3Dscale-down%26page-id%3D0%253A1%26starting-point-node-id%3D2%253A2" allowfullscreen></iframe>






