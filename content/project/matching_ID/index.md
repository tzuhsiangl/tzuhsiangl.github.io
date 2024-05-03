---
title: 'ID Matching for Autonomous Vehicle'
summary: "     "
tags:
  - 
date: '2022-04-27T00:00:00Z'

# Optional external URL for project (replaces project detail page).
external_link: ''

image:
  caption: Photo by rawpixel on Unsplash
  focal_point: Smart

#links:
#  - icon: pdf
#    icon_pack: fab
#    name: Paper
#    url: https://ieeexplore.ieee.org/document/9769979
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


*I am in charge of the experiment of this work.*

The goal of the project is to identify a specific car in a platoon of autonomous vehicle. Let's see an example to know why it is needed.

![platoon](platoon.PNG)

There are four autonomous vehicle in the platoon in the figure above. Each one of them has a unique ID. For the controller, we only know there are four cars in the platoon but we do not know the order. Let's say the car with ID 21 is gonna turn left at the next intersection and the rest is gonna continue to move forward. The platoon should be break into two platoons, which means car ID 5 adn car ID 21 should slow down. However, without the knowledge of the relative location of the car in the platoon, we do not know how to break the platoon.

The method of how to identify a car in a platoon is the following: we added a small signal in the control input and use a road side sensor to capture the movement of the car. The movement can be capture either by camera or radar. For example, if we send the commend to car ID 21 to move slightly left, then the car that moves left in the platoon will be car 21. By doing so,we can identify relative location of each car in the platoon.

The experiment of this project is use an autonomous vechile and a road side radar to prove that this method works. The autonomous vechile we used is a Lincoln MKZ modified by Dataspeed, which is in the picture at the top. The vehicle includes a pair of lidars, a camera, a radar, a high-precision GPS, and an IMU. A Linux-based rugged PC is used for interfacing with the vehicle. The primary means of message passing and communication is achieved through the robot operating system (ROS). The simulation allows me to get familiar to the system. Before we do the experiment in the field, I ran a simulation first. The simulator has been provided by the Dataspeed. The structure of the simulator is same as the system in real MKZ except the control commend is being send to the Gazebo and visualize in rviz. The configuration of the car and sensors has been provided. Based on the simulator they provided, I implement our controller to the simulator. The picure below is a screenshot of the simulation.

![sim](sim.PNG)

The radar that we used is in the figure below. It is a traffic radar from Smartmicro. It can provide the information of position, speed, and heading of the vehicle.

![sim](radar.PNG)

This project is now being writing to a paper. More details will be shared after the paper is being published.