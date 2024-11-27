---
date: 2023-11-17T11:00:59-04:00
tags: ['LLMs', 'Python', 'Evolutionary Strategies', 'Multi-Agent Systems']
title: "Hackathon: Ebiose"
author: "Corentin"
categories: ['Hackathon']
---

### Introduction 

Participated to a project called Ebiose during a 2 days [hackathon](https://hackatechbordeaux.inria.fr/) with a team of 4 people. It focuses on a multi-language-based-agent system to solve tasks. In this system, agents are composed of LLM (e.g. GPT-3.5) coupled with a specific prompt. The structure of the multi-agent system followes a predetermined sequence, where one agent answers a question, another verifies the answer, and a final agent synthesizes both responses. This collaboration is inspired by the [Autogen Framework](https://microsoft.github.io/autogen/), emphasizing coordinated efforts among agents. In this work, we refer to a group of agents as Individuals.

To enhance the performance of these Individuals, an evolutionary algorithm is employed. The agents of an Individual, comprising an LLM and a prompt, undergo improvement through prompt evolution. To do so, we use the [EvoPrompt](https://arxiv.org/pdf/2309.08532.pdf) method. We first create a population of Individuals, each consisting of three agents (LLM + prompt). Evaluation on a dataset yields the fitness of each Individual. The best-performing Individuals serve as parents, generating offspring through crossovers and mutations of their agents' prompts. Text data operations, such as crossovers and mutations, are executed using an LLM with instructions for prompt fusion and modification.

### Methodology 

We tested our method on the [gmsk8k](https://huggingface.co/datasets/gsm8k) dataset (mathematical questions). We evolved during 20 iterations a population of 25 Individuals, each comprising three agents: actor, critic, and synthesis (utilizing GPT-3.5 as their LLM).
The algorithm begins with the generation of an initial population of 25 Individuals. The initial prompts of their agents have been generated with GPT-4.

##### Examples of GPT-4 Initial Population Generator Prompt:

**Actor agent:**
"Generate 25 different prompts optimized for solving mathematical problems that I can apply to solve any math problem."

**Synthesis agent:**
"Continue this list of example prompts: Analyze the proposed solution and its critique to obtain a better solution, Summarize the results provided in a synthetic manner.”

Then we start the evolutionary process, by testing the performance of this population of individuals on the dataset. The evaluation of an Individual on one question involves the actor answering the question, the critic assessing the response, and the synthesis agent considering the entire conversation to return the final answer. Additionally, each Individual has a prompt to format the final answer. The fitness of an Individual is then defined as the percentage of correct answers on the whole dataset, enabling the ranking of all individuals. 

Classical genetic algorithm principles guide parent selection based on fitness, followed by prompt mutations within parent groups with the EvoPrompt method. Currently, the prompts evolution is done with GPT-4 (but the questions answering is done with GPT-3.5).

##### Example of prompts evolution with EvoPrompt:

![mutation_prompt](/mutation_prompt.png)

The crossover and mutation method described in EvoPrompt is only applied to agents within individuals. We have chosen the simplest approach to apply it to our multi-agent individuals: the crossover and mutation operator between Individual 1 and 2 is applied to each pair of their actor prompts (Actor 1 / Actor 2), their critic prompts (Critic 1 / Critic 2) and their synthesis prompts (Synthesis 1 / Synthesis 2).

The population size, comprising 25 Individuals, remains constant throughout the entire evolutionary phase. After generating a new sub-population of offspring, it undergoes evaluation on the designated task. Subsequently, only the top-performing 25 individuals are retained from both the original population (from which parents were selected) and the offspring population. These selected individuals then form the updated population.

This entire process (evaluation of a population, selection of parents, creation and evaluation of new offsprings and update of the new population) is repeated for the desired number of evolutionary algorithm iterations.

### Results

The preliminary results showcase the evolution of individuals over 20 iterations with 25 agents. Box plots and curves illustrate the distribution of the population performance at each iteration during the evolutionary process.

##### Evolution of the distribution of population performance 

![pop_score_evolution](/pop_score_evolution.png)

Here is below an example of prompts of the best individual on the train dataset : 

**Actor agent:**
"Delve into this mathematical puzzle by merging the study of series or sequences with a strategic and theoretical approach. Explore the depths of the problem's complexity by examining the role of logical sequences and recurring patterns, and how they shape the solutions in diverse situations."

**Critic agent:**
"Investigate different problem-solving approaches with an emphasis on retaining critical nuances without sacrificing speed, aiming to find a balanced method that offers thorough, expeditious resolutions to complicated problems."

**Synthesis agent:**
"Develop a refined strategy for tackling mathematical challenges by iteratively improving the problem-solving process, utilizing feedback and critical analysis from earlier attempts to ensure a clear and superior resolution is achieved.”


##### Precision of the last population Individuals and GPT-3.5 / GPT-4 

![precision_comparison](/precision_comparison.png)

The last plot illustrates the precision of each Individual of the final population (iteration 19) on both the  train and test sets on the gsm8k dataset, as well as the precision obtained with GPT 3.5 and GPT 4. As depicted, it demonstrates that the proposed method effectively enhances the precision of GPT 3.5 and that the performance of the best individual is close to the performance of GPT 4 which is a much larger model.

