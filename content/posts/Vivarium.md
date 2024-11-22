---
date: 2024-11-21T11:00:59-04:00
tags: ['Multi-Agent Systems', 'Jax', 'Software Engineering']
title: "Software: Vivarium"
author: "Corentin"
---

With members of the Flowers team, we developed [Vivarium](https://github.com/flowersteam/vivarium), a multi-agent simulator in Jax. It serves both research and teaching in Artificial Intelligence and Artificial Life. 

This software enables creating simple agents with two motors and two sensors, inspired by [Braitenberg Vehicles](https://en.wikipedia.org/wiki/Braitenberg_vehicle), in a 2D rigid-body physics world (the physics engine is written in Jax-MD). Despite the simplicity of the agents at an individual level, the interactions between them can lead to complex emergent behaviors and scenarios ! You can easiely launch custom or predefined simulations with config files. The code is still in development, but here is a an example of simulation that can be done at the moment: 
 
 ![vivarium_sim](/vivarium_sim.gif)

The simulations can either run alone, or can be hosted on a server and interacted with in real time from a web interface or Jupyter Notebooks. The web interface mode enables to easiely play with a simulation, and the Notebook case aims to teach students how to program behaviors on these simulated robots with simple Python code ! For example, one can program an eco-evolutionary simulation with preys, predator, ressources and poison, and even evolve the agent's behaviors with a genetic algorithm.

 [Code](https://github.com/flowersteam/vivarium)
 


