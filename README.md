# SemEval-2023
Final Project for the "Natural Language Processing" course of the Artificial Intelligence Master's Degree at University of Bologna

# Task Description
The sexist classification task is the process of categorizing textual data into predefined classes.
The project is divided in 3 tasks:
* Task A -> Binary classification of sexist (sexist, not sexist)
* Task B -> Classification of sexism categories (threats, derogation, animosity, prejudiced discussion)
* Task C -> Classification of sexism subcategories (e.g. threats of harm, descriptive attacks)
The entire structure can be represented as follow:

![image](https://github.com/DANIELEMARINI99/SemEval-2023/blob/main/edos_vectors.png)

# Authors
* Daniele Marini
* Davide Brescia
* Iulian Zorila

# Data
The [dataset](https://codalab.lisn.upsaclay.fr/competitions/7124#learn_the_details), provided by CodaLab include about 14000 labeled sentences.
Since the dataset is hierarchical, each sentence is associated with 3 features, one for each task, so the sentences classified as not sexist will be removed for the other tasks.

# Goal
The goal of this project is to obtain the best possible results on each singular task by training different models and enhancing their performance.

# Approach
Given that all three tasks proposed by the competition are classification tasks, it was considered useful to employ a consistent pipeline for each task.
Specifically, we designed two stages for each task:
* Baseline models -> use of simple models to ensure the correct functionality of the code, and to initially evaluate which models work best for the given task
* Advanced models -> following the identification of the most effective baseline model, advanced techniques were then applied to further improve the results

In order to improve the results we applied the following techniques:
    * Use of larger models
    * Pretrained models
    * Learning rate scheduling 
    * Data augmentation


# Models
The models we used for the classification, taken from [huggingface](https://huggingface.co/models), are the following:
* Baseline models
    * LSTM with GloVe embedding
    * BertTiny
    * DistilRoberta
* Advanced models
    * DistilRoberta with Learning rate scheduler
    * DistilRoberta with data augmentation
    * RoBERTa pretrained on hate speech
    * RoBERTa pretrained on hate speech with Learning rate scheduler
    * RoBERTa pretrained on hate speech with Learning rate scheduler and data augmentation
    * HateBERT
    * HateBERT with Learning rate scheduler
    * HateBERT with Learning rate scheduler and data augmentation

# Results
The referment metrics we used is the F1-score.
The results of all the models in the respective task can be summarized by the following tabel:

![image](https://github.com/DANIELEMARINI99/SemEval-2023/blob/main/results.png)

As we can see the best models for each task are:
* Task A -> RoBERTa pretrained on hate speech [0.83%]
* Task B -> HateBERT with Learning rate scheduler [0.62%]
* Task A -> RoBERTa pretrained on hate speech with Learning rate scheduler and data augmentation [0.38%]
