---
date: 2026-01-20
categories:
  - AI Research
  - EdTech
authors:
  - alex
---

# Giving Feedback at Scale: Our Journey into Fine-Tuning GPT for Education

We have all felt that moment of frustration: you put hours of thought into a complex response, only to receive a generic "Good job" or a cold numerical score. As a researcher at **Acuity Insights**, I have spent years looking at how we can make educational assessment more human, even when we are dealing with thousands of students.

My team and I recently presented our findings on this challenge at **The 40th ACM/SIGAPP Symposium on Applied Computing (SAC '25)** in Catania, Italy. We wanted to know: Can we actually teach an AI to give feedback that feels personal, supportive, and—most importantly—useful?

DOI: 10.1145/3672608.3707735

<!-- more -->

---

### The "Casper" Challenge

We decided to test this on **Casper**, a high-stakes situational judgment test (SJT) that assesses social intelligence and professionalism. Unlike a math quiz, there are no strictly right or wrong answers in Casper; instead, applicants describe how they would handle complex ethical dilemmas or social challenges.

Because these responses are so unique and diverse, you cannot just use a pre-written template for feedback. You need a system that can truly "understand" the nuances of a student’s reasoning.


---

### Moving Beyond Simple Chatbots

Most research to date has focused on using standard "off-the-shelf" AI models with basic prompting. But for high-stakes education, we needed more precision.

We took **GPT-3.5-Turbo** and applied **Parameter-Efficient Fine-Tuning (PEFT)**. Specifically, we used **Low-Rank Adaptation (LoRA)** to update the model’s parameters specifically for the task of generating feedback.

The most surprising part? We didn’t need a massive amount of data. We developed a high-quality training set of just **124 hand-crafted feedback examples**. We also integrated **Chain-of-Thought (CoT) prompting**, requiring the model to "think step-by-step" and explain its reasoning before writing the final message to the student.


---

### What We Discovered

To see if our fine-tuned tutor actually worked, we had independent judges, test experts, and real students evaluate the results.

* **Structure & Tone:** **72.9%** of the generated messages met every single structural criterion for effective feedback.
* **Personalization:** Over **94.9%** of the messages were successfully tailored to the specific elements of the applicant's response.
* **Actionability:** Every single message—except for those responding to perfect scores—included concrete suggestions for improvement.
* **User Satisfaction:** In our survey of 164 participants, **84.8%** expressed satisfaction with the feedback they received.
* **Supportive Environment:** Over **70%** of respondents agreed the feedback was clear, logically organized, and supportive.


---

### The Path Forward

Is it perfect? Not yet. Some users wanted even more detail, and we observed occasional linguistic slips. There is also a delicate balance to strike: we want to give students helpful tips without compromising the security of a high-stakes test.

However, this study shows that we are on the right track. By combining expert human knowledge with specialized AI training, we can provide the kind of timely, personalized support that every learner deserves—at a scale that was previously impossible.

---
