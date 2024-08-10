---
date: 2024-06-12T11:00:59-04:00
tags: ['Open Source', 'Python', 'Deep Learning']
title: "Software: Open Source Contributions"
author: "Corentin"
---

- Developed the [LLM-Culture](https://github.com/jeremyperez2/LLM-Culture) library. This software enables simulating networks composed of LLMs agents, that can generate text over multiple generations based on their neighbors input, personnality and task. 
The project also provides tools for analyzing the resulting text dynamics and offers an user-friendly web interface, making it accessible to non-programmers.

- Developed a [turorial for hyper parameter search](https://github.com/reservoirpy/reservoirpy/tree/master/tutorials/4.a-Hyperparameter%20search%20with%20Optuna) using Optuna in the [ReservoirPy](https://github.com/reservoirpy/reservoirpy) machine learning library. The tutorial covers sequential and parallelized hyperparameter search on local machines using the joblib package. It also demonstrates how to scale up this process by utilizing [Slurm](https://slurm.schedmd.com/documentation.html) files to parallelize the search on remote clusters of CPUs.

- Contributed to the development of [KanRL](https://github.com/riiswa/kanrl), a project studying the combination of Reinforcement Learning and Kolmogorov-Arnold Networks (KANs). I helped creating this [Hugging Face space](https://huggingface.co/spaces/riiswa/RL-Interpretable-Policy-via-Kolmogorov-Arnold-Network) to facilitate the interpretation of trained RL policies, and led experiments to compare the performance of simple Policy Gradient and PPO algorithms using both KANs and MLPs on [this branch](https://github.com/riiswa/kanrl/tree/ppo).

- Contributed to the [Stable-Baselines3](https://github.com/DLR-RM/stable-baselines3) and [Stable-Baselines3-Contrib](https://github.com/Stable-Baselines-Team/stable-baselines3-contrib) Reinforcement Learning Libraries by fixing several minor bugs.
