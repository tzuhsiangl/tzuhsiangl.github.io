---
title: The Dynamic Watermarking Method for the Cybersecurity of the Tennessee Eastman Process Control System

# Authors
# If you created a profile for a user (e.g. the default `admin` user), write the username (folder name) here
# and it will be replaced with their full name and linked to their profile.
authors:
  - Tzu-Hsiang Lin
  - P. R. Kumar

# Author notes (optional)
author_notes:
  - 'Equal contribution'
  - 'Equal contribution'

date: '2013-07-01T00:00:00Z'
doi: ''

# Schedule page publish date (NOT publication's date).
publishDate: '2017-01-01T00:00:00Z'

# Publication type.
# Accepts a single type but formatted as a YAML list (for Hugo requirements).
# Enter a publication type from the CSL standard.
publication_types: ['paper-conference']

# Publication name and optional abbreviated publication name.
publication: In *Hugo Blox Builder Conference*
publication_short: In *ICW*

abstract: Networked cyber-physical systems are central to several critical infrastructures such as process industries, energy systems, and transportation systems. However, as several recent incidents have shown, they are vulnerable to cyber attacks. Sensors or networks carrying sensor measurements can be compromised, and the resulting malfunctioning of the control system can cause misbehavior. Since the infrastructure systems are safety and economy critical, it is important to detect such attacks and take appropriate steps to make them resilient. This paper addresses the first step:How to detect such attacks? It studies this problem for the process industries by studying the cyber-security of the Tennessee Eastman Process (TEP), which is an open source benchmark that has been developed for the purpose of evaluating process control technology \cite{te} used in industries such as chemical plants and oil refineries.
We explore the use of Dynamic Watermarking \cite{dw}, a pro-active method for detecting attacks. One can employ recursive system identification to develop ARMAX models of the system. The models show that the TEP is non-minimum phase, placing it outside the scope of previous methods. So motivated, we develop a new method that allows the use of Dynamic Watermarking for detecting attacks on non-minimum phase systems. We explore the use of this method to detect a range of attacks on the TEP, including replay attacks, noise injection attacks, and bias injection attacks.  

# Summary. An optional shortened abstract.
summary: Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis posuere tellus ac convallis placerat. Proin tincidunt magna sed ex sollicitudin condimentum.

tags: []

# Display this page in the Featured widget?
featured: true

# Custom links (uncomment lines below)
# links:
# - name: Custom Link
#   url: http://example.org

url_pdf: ''
url_code: ''
url_dataset: ''
url_poster: ''
url_project: ''
url_slides: ''
url_source: ''
url_video: ''

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
image:
  caption: 'Image credit: [**Unsplash**](https://unsplash.com/photos/pLCdAaMFLTE)'
  focal_point: ''
  preview_only: false

# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.
projects:
  - example

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example"` references `content/slides/example/index.md`.
#   Otherwise, set `slides: ""`.
#slides: example
---

{{% callout note %}}
Click the _Cite_ button above to demo the feature to enable visitors to import publication metadata into their reference management software.
{{% /callout %}}

{{% callout note %}}
Create your slides in Markdown - click the _Slides_ button to check out the example.
{{% /callout %}}

Add the publication's **full text** or **supplementary notes** here. You can use rich formatting such as including [code, math, and images](https://docs.hugoblox.com/content/writing-markdown-latex/).
