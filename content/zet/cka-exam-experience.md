---
title : "CKA Exam Experience"
subtitle : "Cleared the Certified Kubernetes Administrator certification"
date : 2024-08-07
tags:
- Certification
- CKA
- kubernetes
- study
---


Well, I was initially planning to give my exam on 8th August but decided to prepone it to 4th August, at night 10:30 PM.

This was because:
1. I think I could do it, If I fail I can simply retake the exam on 8th.
2. Gives me more time for the CKS and other stuff ;)

### Killercoda

I did all the scenarios for the CKA on Killercoda. This took me nearly 2 days to finish. I would suggest that you at least do the scenarios by Kim, as they helped me troubleshoot a lot better in the exam.

### Killershell

I started the exam simulator nearly 26 hours before the actual exam. It was by far the most fun. I attempted the simulator three times. This is how they went:

#### First Attempt:

I was mentally prepared for it to go bad, but surprisingly, it didn't! Kinda.

There were a lot of questions, for sure, but unlike the CKAD simulator, they didn't feel out of reach. However, I did face a lot of environment issues with tmux and vi mode in bash.

I am so used to using the two together that without them, it became irritating to run commands. Additionally, I found out that the bash PS1 prompt loses its color when you're in tmux, which made identifying which machine I'm on quite tough.

In the end, I finished about 15 questions, skipping a few. **I got a final score of 65/125.**

#### Second Attempt:

After the first attempt, I went to sleep and purposefully didn't look at the solutions, thinking I could do better if I configured the environment beforehand. The next morning, I made the following changes to my environment:


```bash
echo "set -o vi " >> ~/.bashrc
echo "force_color_prompt=yes" >> ~/.bashrc
echo "setw -g mode-keys vi" >> ~/.tmux.conf
```


This time was much better. **I did about 20 questions, again skipping many. I scored 88/125.** 

I struggled especially with pod scheduling, specifically pod affinity/anti-affinity. Troubleshooting the kubelet felt challenging as well.

#### Third Attempt:

With 6 hours to the exam, I decided to look at the solutions. The explanations were so helpful that I ended up reading the entire thing for 45 minutes to an hour, trying stuff and failing miserably at times.

After some time off, I gave my third attempt, as I did not want to blindly solve stuff from memory. I am not solving rubix-cube am I?!

**I did all the questions with 5 minutes to spare and got a final score of 115/125.** I still messed up pod affinity but learned a lot in the process.


### Exam Experience:

The exam was relatively easy. Doing the simulator really helps. I finished all the questions in nearly 1 hour and 20 minutes and then spent the remaining time revisiting flagged questions and verifying everything.

The PSI environment and proctoring were fine. I had to wait 10-15 minutes to get a proctor assigned, but other than that, everything went smoothly.

#### Result:

![CKA certificate](img/cka-cert.webp)

***I received my results after 24 hours and passed the CKA with a score of 98/100!*** :D

Har Har Mahadev!
