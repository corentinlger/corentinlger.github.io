---
date: 2024-07-05T11:00:59-04:00
tags: ['LLMs', 'Cultural Evolution', 'Natural Language Processing']
title: "Research: When LLMs Play the Telephone Game"
author: "Jérémy Perez, Corentin Léger, Grgur Kovač, Cédric Colas, Gaia Molinaro, Maxime Derex, Pierre-Yves Oudeyer, Clément Moulin-Frier"
# resources:
# - name: "featured-image"
#   src: "featured-image.jpg"
---
Arxiv preprint (Under Review)

### Abstract

As large language models (LLMs) start interacting with each other and generating an increasing amount of text online, it becomes crucial to better understand how information is transformed as it passes from one LLM to the next. While significant research has examined individual LLM behaviors, existing studies have largely overlooked the collective behaviors and information distortions arising from iterated LLM interactions. Small biases, negligible at the single output level, risk being amplified in iterated interactions, potentially leading the content to evolve towards attractor states. In a series of telephone game experiments, we apply a transmission chain design borrowed from the human cultural evolution literature: LLM agents iteratively receive, produce, and transmit texts from the previous to the next agent in the chain. By tracking the evolution of text toxicity, positivity, difficulty, and length across transmission chains, we uncover the existence of biases and attractors, and study their dependence on the initial text, the instructions, language model, and model size. 

![telephone_llm_fig](/TelephoneLLM.png)

For instance, we find that more open-ended instructions lead to stronger attraction effects compared to more constrained tasks. We also find that different text properties display different sensitivity to attraction effects, with toxicity leading to stronger attractors than length. These findings highlight the importance of accounting for multi-step transmission dynamics and represent a first step towards a more comprehensive understanding of LLM cultural dynamics. 

[Paper](https://arxiv.org/abs/2407.04503) - [Website](https://sites.google.com/view/telephone-game-llm)

 

