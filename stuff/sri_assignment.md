---
title: "Coding Task: Summer Research Internship"
layout: page
excerpt: Summer Research Opportunities
permalink: /stuff/sri_assignment/
---


### Guidelines:
- There are 4 tasks in total for different project-openings.
- You are required to solve and submit at least 1 of these 4 tasks of your choice, before the deadline.
- Each participant can solve and submit as many tasks.
- The submission deadline is strict and no exceptions will be made for extensions.
- You can submit a Google Colab/ Jupyter notebook (.ipynb) or a zip of .py files.
- Ensure that all links in the submitted form are accessible (not private).
- The deadline to submit is **1:00 PM (IST) 6th February (Tuesday), 2024**.
- Submission link- [https://forms.office.com/r/QRsi0ju9pY](https://forms.office.com/r/QRsi0ju9pY)

### Task 1: Prepare a custom pipeline for data preparation and CNN training

1. Use the TinySOL dataset: [https://zenodo.org/records/3685367](https://zenodo.org/records/3685367). You can download this by using the following commands-
   ```console
    user:~$ wget https://zenodo.org/records/3685367/files/TinySOL.tar.gz
    user:~$ wget https://zenodo.org/records/3685367/files/TinySOL_metadata.csv
    user:~$ unzip TinySOL.tar.gz && rm TinySOL.tar.gz
   ```
2. Train a small CNN for classificying the instruments being played, given an audio file from this dataset for 30 epochs. You are free to choose all other hyperparmeters. Save this trained model.
3. Write a general dataset class, which takes as input the path to the csv file and the folder with the audio files. When called with some input index *i*, it should return a dictionary with the following items-
   ```python
   {'file': filename, #name of the audio file,
    'audio': audio, #Processed ith audio of shape [1,T]
    'mel': mel_spectrogram, #Mel Spectrogram of the audio. Shape- [1,F,T]. Choose the parameters yourself.
    'gt': ground_truth, #The label mapped with the corresponding audio file.
    'pseudo': pseudo_label #Predicted label in the inference from the trained model in step-2.
   }
   ```
4. Now train the same CNN from scratch (untrained), but use the *'psuedo_label'* in the dict output of the dataset as in step-3 as target variable in your loss function.
5. Now analyze the results (accuracy, loss) and plot some graphs to contrast in the CNN's performance when trained using the correct ground truth labels (step-2) with the case when trained using the pseudo labels.
6. **BONUS**: What can you do to improve the performance of the CNN in step-4 (other than increasing num_epochs in step-2)?

### Task 2: Use relevant features for Raga Identification

1. Train a simple CNN for raga identification using relevant features.
2. Play around with different types of extracted features from the music audio files, to deduce the most relevant before finally training the model.
3. Use the dataset available here- [https://www.kaggle.com/datasets/kcwaghmarewaghmare/indian-music-raga](https://www.kaggle.com/datasets/kcwaghmarewaghmare/indian-music-raga).

### Task 3: Build Symbolic Equation from Neural Network Output
In this task, you will develop a program that takes the output of a 2-hidden layer feedforward neural network as input and 
constructs a symbolic equation representing the network's output. The goal is to understand and interpret the neural network's
decision-making process through symbolic representation.

1. Train a 2-hidden layer feedforward neural network with sparse connections (as in the figure below) on a dataset of your choice. Save the trained model.
2. Extract the symbolic expression representing the output layer of the neural network. Can use [SymPy](https://www.sympy.org/en/index.html).
3. Implement a Python program that takes the symbolic expression from the output layer as input. Construct a symbolic equation using the input features as variables.
4. Allow users to input a set of values for the input features. Use the symbolic equation to compute and display the corresponding predicted output.
5. Document the code with comments and explanations. Provide instructions on how to run the program and interpret the symbolic equation.

<div align="center">
  <img class="width-score" src="{{ "./stuff/sri.png" | relative_url }}" width="60%">
</div>

### Task 4: Implement paper/s on Generative Modelling
In this task, you are required to implement either (or both) of the following papers from scratch-

1. #### [Image Inpainting using GAN with contextual attention](https://arxiv.org/pdf/1801.07892.pdf)
Dataset: [CIFAR-10](https://www.cs.toronto.edu/~kriz/cifar.html). 
Repo: [https://github.com/jiajunhua/JiahuiYu-generative_inpainting](https://github.com/jiajunhua/JiahuiYu-generative_inpainting)

2. #### [Image Inpainting using Partial Convolution](https://arxiv.org/pdf/1804.07723.pdf)
Dataset: [CIFAR-10](https://www.cs.toronto.edu/~kriz/cifar.html). 
Repo: [https://github.com/Shivkumar25/Image-Inpainting](https://github.com/Shivkumar25/Image-Inpainting)


-----------------------------
In case you have any queries/doubts on the problem statements, feel free to contact [akshayr@iitk.ac.in](akshayr@iitk.ac.in).
