# Decoding Brain Signals Convolutional Neural Networks (CNN)


This repository contains a Convolutional Neural Network (CNN) implemented using the Keras deep learning framework. The purpose of this network is to decode EEG data, specifically for object recognition tasks. The EEG data was collected from participants who viewed images belonging to six distinct categories: human body, human face, animal body, animal face, inanimate natural objects, and inanimate man-made objects. The test set included 72 images presented to participants, and the CNN aims to classify the category of the image a participant was viewing based on their recorded EEG signals.

For more details about the data collection methodology, experimental setup, and to access the public dataset, please visit the original research article by Stanford [here](https://purl.stanford.edu/bq914sc3730).

## Overview 

Electroencephalography (EEG) is a widely used non-invasive technique to monitor electrical activity in the brain. Traditionally, EEG data is highly dimensional and requires extensive preprocessing for effective classification. This project addresses that challenge by leveraging CNNs a class of deep learning models particularly well-suited for feature extraction from high-dimensional data to operate directly on raw EEG data, eliminating the need for traditional preprocessing steps.

## Data Structure

The dataset comprises EEG signals from multiple subjects, with data stored in MATLAB files (.mat format). Each file corresponds to a subject and contains:

-X_3D: A 3-dimensional array of EEG signal data.
-categoryLabels: Labels for each EEG trial.

Each file includes up to 5184 EEG trials. During the data loading process, only the first 5184 trials are used to ensure consistency across subjects.