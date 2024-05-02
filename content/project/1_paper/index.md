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


Tennessee Eastman Process is a model of an industrial chemical process for developing, studying and evaluating process control technology. The model involves five major unit operations. The relationship between each unit is in the figure at the top. There are 12 control inputs and 41 measurments. 


**ARMAX MODEL**

$$
\begin{aligned}
y(k+1) = \sum_{i=0}^{p}\alpha_iy(k-i)+ \sum_{i=0}^{q}\beta_iu(k-i-d+1)\\
+\sum_{i=0}^r\gamma_i w(k-i)+ w(k+1)
\end{aligned}
$$

$$
\begin{aligned}
FPR = \frac{FP}{N} = \dfrac{FP}{FP+TN}\\
TPR = \frac{TP}{P} = \dfrac{FP}{FP+FN} 
\end{aligned}
$$



Aliquam in turpis accumsan, malesuada nibh ut, hendrerit justo. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Quisque sed erat nec justo posuere suscipit. Donec ut efficitur arcu, in malesuada neque. Nunc dignissim nisl massa, id vulputate nunc pretium nec. Quisque eget urna in risus suscipit ultricies. Pellentesque odio odio, tincidunt in eleifend sed, posuere a diam. Nam gravida nisl convallis semper elementum. Morbi vitae felis faucibus, vulputate orci placerat, aliquet nisi. Aliquam erat volutpat. Maecenas sagittis pulvinar purus, sed porta quam laoreet at.
