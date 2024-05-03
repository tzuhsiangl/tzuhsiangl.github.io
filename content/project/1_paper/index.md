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


The idea of dynamic watermarking is very simple. If we add a small signal at input, the output will be affected. Since watermark is known to us not to the attacker, by checking whether the chagne of the output is corrsponding to the watermarked input, we can tell whether the signal is authentic. Let's see a simple example. The figure below is an example of combination of input siganl and watermark signal. 

![wm](wm_input.png)

The figure below is a pair of watermarked input and system output. As we can see, the output change does follows the change of the watermarked input.
![correct](correct_output.png)

However, the output in the figure below is not the correct output. It is highly likely that the output measurment has been modified or there is something wrong with the system.
![wrong](wrong_output.png)

The watermark that we added to the system will be a white Gaussian sequence.. By doing so, even through the attacker knows that we are using watermark, they can not predict what are we gonna add next. Moreover, since it's a random signal, the attacker cannot distenguish the watermark and the noise in the system.


Now, let's lool at it in detail.A closed-loop dynamical system can be described in the figure below.
![loop](dw1.png)

The system can be described as

$$
 \begin{align*}
      x(t+1)=a&x(t)+bu(t)+w(t+1), w(t)\sim N(0,\sigma_w^2)i.i.d\\\\\\
      u(t)&=g_t(x^t)+\textcolor{red}{e(t)}, e(t)\sim N(0,\sigma_e^2)i.i.d
 \end{align*}
$$

$z(t)$ is the value that we received. If the system is honest, $x(t)\equiv z(t)$. And the two tests that being used to detect cyberattack are

$$
\begin{align*}
    \lim_{T\rightarrow\infty}\frac{1}{T} \sum_{k=0}^{T-1}&(z(k+1)-az(k)-bg_k(z^k)-be(k))^2=\sigma_w^2\\\\\\
    \lim_{T\rightarrow\infty}\frac{1}{T} \sum_{k=0}^{T-1}&(z(k+1)-az(k)-bg_k(z^k))^2=b^2\sigma_e^2+\sigma_w^2
\end{align*}
$$

If the value of one of the test exceed the predifined threshold, then the sensor is not honest.

**ARMAX MODEL**

In order to perform the watermark tests presented above, the model of the system is needed. Here, the ARMAX model has been used. It can presented in the following form
$$
 \begin{align*}
    y(k+1) &= \sum_{i=0}^{p}\alpha_iy(k-i)+ \sum_{i=0}^{q}\beta_iu(k-i-d+1)\\\\\\
    &\underbrace{+ \sum_{i=0}^r \gamma_i w(k-i)+ w(k+1).}_{\text{ colored noise}}
\end{align*}
$$

The Extended Least Square has been used to fit the model to get the coeffient of $\alpha, \beta$ and $\gamma$.


**Result**

The following an example of noise injection attack. At time 150hr, a random noise will be added to the output measurement. This attack might not cause instability to the system, but it will reduce the efficiency of the system.
![noise](m1_noise_value.png)
The following are the value of the watermark tests. As we can see the value exceed the threshold after the attack, which will be classified as detected.
![tests](m1_armax_tests.png)


Here I only provide some simplified concept of the paper. If you want to know more detail, please check the paper. The link is at the top of the page.


