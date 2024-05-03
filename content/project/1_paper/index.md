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

Networked cyber-physical systems core of critical infrastructures such as process industries, energy systems, and transportation systems. However, as several recent incidents have shown, sensors or networks carrying sensor measurements can be compromised. It can make the system misbehave.  Since the infrastructure systems are safety and economy critical, it is important to detect such attacks. The Dynamic Watermarking is one of the method.

**Tennessee Eastman Process**

Tennessee Eastman Process is a model of an industrial chemical process for developing, studying and evaluating process control technology. The model involves five major unit operations. The relationship between each unit is in the figure at the top. There are 12 control inputs and 41 measurments in the system.




 **Dynamic Watermarking**

A closed-loop dynamical system can be described in the figure below. Setpoint is the value that we would like the system to be at.
![loop](dw1.png)


$$
 \begin{align*}
      x(t+1)=a&x(t)+bu(t)+w(t+1), w(t)\sim N(0,\sigma_w^2)i.i.d\\\\\\
      u(t)&=g_t(x^t)+\textcolor{red}{e(t)}, e(t)\sim N(0,\sigma_e^2)i.i.d
 \end{align*}
$$



The idea of dynamic watermarking is very simple. If we add a small signal at input, the output will be affected. Since watermark is known to us not to the attacker, by checking whether the chagne of the output is corrsponding to the watermarked input, we can tell whether the signal is authentic. Let's see a simple example. The figure below is an example of combination of input siganl and watermark signal. 

![wm](wm_input.png)

The figure below is a pair of watermarked input and system output. As we can see, the output change does follows the change of the watermarked input.
![correct](correct_output.png)

However, the output in the figure below is not the correct output. It is highly likely that the output measurment has been modified or there is something wrong with the system.
![wrong](wrong_output.png)

The watermark that we added to the system will be a white Gaussian sequence with mean equals to 0 and variance equals to $\sigma^2_e$. By doing so, even through the attacker knows that we are using watermark, they can not predict what are we gonna add next. Moreover, since it's a random signal, the attacker cannot distenguish the watermark and the noise in the system. To detect the attack, there are two tests that being used to check the 




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



