## CSE 517 NLP

This codebase was used to recreate the results found in the following paper [HENIN](https://www.aclweb.org/anthology/2020.emnlp-main.200.pdf). The author's codebase can be found at the following link: [Codebase](https://github.com/HsinYu7330/HENIN)

### Directories

Here is a description of each subfolder and what it contains:

- Preprocessing: Contains code and notebooks for the generation of the three datasets used: Vine, Instagram, unlabeled Vine.
- Models: Contains code and notebooks pertaining to the creation and training of models used within the paper.

### Data dowload instructions

- Instagram dataset: contains image description and user comments.
- Vine dataset: a mobile application website that allows users to record and edit a few seconds looping videos. Each vine session also contains video description and user comments.
- Unlabeled Vine: This is set of raw Vine sessions and posts. Unlike the preceding two datasets, these were manually processed and labeled

Dataset available at https://sites.google.com/site/cucybersafety/home/cyberbullying-detection-project/dataset

Once acquired, the datset can be preprocessed using the files in the preprocessing folder. We are unable to upload processed data due to signed End User Agreements with the source institution. However, please feel free to email us for processed code if you are running into trouble. 

### Dependencies
To run the HENIN model code, the following are required
- python>=3.5
- keras == 2.24
- tensorflow == 1.13
- gensim, network, nltk

Higher versions of tensor flow and keras are incompatible with the current HENIN codebase. Our experiments and comparison models can be run on google colab.

### Commands
The provided notebooks can be used to preprocess and run the models. The datasets have to be uploaded onto your google drive (file paths may have to be modified to match your directory). The cells can be run in the notebook.

### Table of results

