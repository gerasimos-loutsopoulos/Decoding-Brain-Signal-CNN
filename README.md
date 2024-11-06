# Decoding Brain Signals Convolutional Neural Networks (CNN)


This repository contains a Convolutional Neural Network (CNN) implemented using the Keras deep learning framework. The purpose of this network is to decode EEG data, specifically for object recognition tasks. The EEG data was collected from participants who viewed images belonging to six distinct categories: human body, human face, animal body, animal face, inanimate natural objects, and inanimate man-made objects. The test set included 72 images presented to participants, and the CNN aims to classify the category of the image a participant was viewing based on their recorded EEG signals.

For more details about the data collection methodology, experimental setup, and to access the public dataset, please visit the original research article by Stanford [here](https://purl.stanford.edu/bq914sc3730).

## Overview 

Electroencephalography (EEG) is a widely used non-invasive technique to monitor electrical activity in the brain. Traditionally, EEG data is highly dimensional and requires extensive preprocessing for effective classification. This project addresses that challenge by leveraging CNNs a class of deep learning models particularly well-suited for feature extraction from high-dimensional data to operate directly on raw EEG data, eliminating the need for traditional preprocessing steps.

## Variables contained in each Matlab file:

The dataset comprises EEG signals from multiple subjects, with data stored in MATLAB files (.mat format). Each file corresponds to a subject and contains:

- sub : Experimental participant identifier (e.g. 'S1', 'S2'…. 'S10')
- N : Number of time samples per trial (always 32)
- Fs : Sampling frequency of the data (always 62.5Hz)
- T : Number of experimental trials (around 5,184 per dataset)
- exemplarLabels : A vector of length T containing the exemplar label of each trial.
- categoryLabels : A vector of length T containing the category label of each trial.
1=Human Body, 2=Human Face, 3=Animal Body, 4=Animal Face, 5=Fruit Vegetable,
6=Inanimate Object (as illustrated in Figure 4):

- X_3D: The 3D EEG data matrix is a 3-dimensional electrodes-by-time-by-trial matrix of size 124-by-32-by-T. 
Each slice of X_3D along the trial dimension represents one experimental trial. Trial labels are corresponding elements in the exemplarLabels and categoryLabels vectors. This form of the EEG data allows for easier subsetting by time and space.

## How to Run

1 Clone the repository.
2 Ensure the MATLAB files (S1.mat, S2.mat, etc.) are in the same directory.
3 Run the main script to initiate model training and evaluation.

  ```bash
  python main_script.py
  ```


## Expected Output

The script will output performance metrics and generate confusion matrix heatmaps for each subject. The average metrics across subjects will be printed at the end.