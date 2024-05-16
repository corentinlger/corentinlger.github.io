---
date: 2023-09-12T11:00:59-04:00
tags: ['Open Source', 'Python', 'Deep Learning']
title: "Software: Parallelization computation tutorial"
author: "Corentin"
---

Created an open source [turorial for hyper parameter search](https://github.com/reservoirpy/reservoirpy/tree/master/tutorials/4.a-Hyperparameter%20search%20with%20Optuna) using Optuna for the [ReservoirPy](https://github.com/reservoirpy/reservoirpy) machine learning library.  

First, it explains how to search hyper parameters on your machine sequentially, but also in a parallelized manner using the joblib library. Then, it demonsrates how to perform the same search at a larger scale, by using slurm files to parallelize it on a remote cluster of CPUs. 


 

