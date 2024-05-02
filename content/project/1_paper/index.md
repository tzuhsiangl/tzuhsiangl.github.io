---
title: The Dynamic Watermarking Method for the Cybersecurity of the Tennessee Eastman Process Control System
summary: <ins>Tzu-Hsiang Lin</ins>, P. R. Kumar
tags:
  - Cybersecurity
date: '2023-04-27T00:00:00Z'

# Optional external URL for project (replaces project detail page).
external_link: ''

#image:
#  caption: Photo by rawpixel on Unsplash
#  focal_point: Smart

links:
  - icon: pdf
    icon_pack: fab
    name: Paper
    url: https://ieeexplore.ieee.org/abstract/document/10441912
url_code: ''
url_pdf: ''
url_slides: ''
url_video: ''

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
#slides: example
---

Networked control system are vulernable to cyber attack
![loop](dw1.png)


The idea of dynamic watermarking is very simple. If we add a small signal at input, the output will be affected. By checking whether the chagne of the output is corrsponding to the small signal we added, we can tell whether the signal is authentic. Let's see a simple example. The watermark will be added to the control input signal and the signal will become watermarked input. 

![wm](wm_input.png)

The figure below is a pair of watermarked input and system output. As we can see, the output change does follows the change of the watermarked input.
![correct](correct_output.png)

However, the output in the figure below is not the correct output. It is highly likely that the output measurment has been modified or there is something wrong with the system.
![wrong](wrong_output.png)

Tennessee Eastman Process is a model of an industrial chemical process for developing, studying and evaluating process control technology. The model involves five major unit operations. The relationship between each unit is in the figure at the top. There are 12 control inputs and 41 measurments. 

There

**ARMAX MODEL**

$$
 \begin{align*}
    y(k+1) &= \sum_{i=0}^{p}\alpha_iy(k-i)+ \sum_{i=0}^{q}\beta_iu(k-i-d+1)\\\\\\
    &\underbrace{+ \sum_{i=0}^r \gamma_i w(k-i)+ w(k+1).}_{\text{ colored noise}}
\end{align*}
$$


**Result**

The following an example of noise injection attack. At time 150hr, a random noise will be added to the output measurement. This attack might not cause instability to the system, but it will reduce the efficiency of the system.
![noise](m1_noise_value.png)
The following are the value of the watermark tests. As we can see the value exceed the threshold after the attack, which will be classified as detected.
![tests](m1_armax_tests.png)



