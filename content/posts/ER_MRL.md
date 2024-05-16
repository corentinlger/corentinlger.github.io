---
date: 2023-12-12T11:00:59-04:00
tags: ['Meta RL', 'Evolutionary Computation', 'Reservoir Computing']
title: "Research: Evolving Reservoirs for Meta Reinforcement Learning"
author: "Corentin"
---

Paper presented at [EvoStar 2024](https://www.evostar.org/2024/) (Oral).

### Abstract

Animals often demonstrate a remarkable ability to adapt to their environments during their lifetime. They do so partly due to the evolution of morphological and neural structures. These structures capture features of environments shared between generations to bias and speed up lifetime learning. 

![er_mrl_fig](/er_mrl.png)

In this work, we propose a computational model for studying a mechanism that can enable such a process. We adopt a computational framework based on meta reinforcement learning as a model of the interplay between evolution and development. At the evolutionary scale, we evolve reservoirs, a family of recurrent neural networks that differ from conventional networks in that one optimizes not the synaptic weights, but hyperparameters controlling macro-level properties of the resulting network architecture. At the developmental
scale, we employ these evolved reservoirs to facilitate the learning of a behavioral policy through Reinforcement Learning (RL). Within an RL agent, a reservoir encodes the environment state before providing it to an action policy. 

We evaluate our approach on several 2D and 3D simulated environments. Our results show that the evolution of reservoirs can improve the learning of diverse challenging tasks. We study in particular three hypotheses: the use of an architecture combining reservoirs and reinforcement learning could enable (1) solving tasks with partial observability, (2) generating oscillatory dynamics that facilitate the learning of locomotion tasks, and (3) facilitating the generalization of learned behaviors to new tasks unknown during the evolution phase

[paper](https://arxiv.org/abs/2312.06695) - [code](https://github.com/corentinlger/ER-MRL)


 

