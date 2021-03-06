## CSE517 Natural Language Processing Project: Reproducibility Report for HENIN Paper

This codebase was used to recreate the results found in the following paper [HENIN](https://www.aclweb.org/anthology/2020.emnlp-main.200.pdf). The author's codebase can be found at the following link: [Codebase](https://github.com/HsinYu7330/HENIN)

### Directories

Here is a description of each subfolder and what it contains:

- Preprocessing: Contains code and notebooks for the generation of the three datasets used: Vine, Instagram, unlabeled Vine.
- Models: Contains code and notebooks pertaining to the creation and training of models used within the paper.
- - RNN_GRU.ipynb : This notebook contains implementation of baseline RNN and GRU models. It evaluates RNN and GRU on the processed Vine, Instagram and unlabeled datasets. It also tests early detection of cyberbullying using fraction of comments. 
- - LR_RF.ipynb : This notebook contains the implementation of the logisitic regression and random forest models. It contains the basis for generating evaluations on all three datasets.
- - Inst_hp_ed.ipynb :
- - Inst_lstm.ipynb :
- - Vine_hp_ed.ipynb :
- - Vine_lstm.ipynb :

### Data dowload instructions

- Instagram dataset: contains image description and user comments.
- Vine dataset: a mobile application website that allows users to record and edit a few seconds looping videos. Each vine session also contains video description and user comments.
- Unlabeled Vine: This is set of raw Vine sessions and posts. Unlike the preceding two datasets, these were manually processed and labeled

Dataset available at https://sites.google.com/site/cucybersafety/home/cyberbullying-detection-project/dataset

Once acquired, the datset can be preprocessed using the files in the preprocessing folder. We are unable to upload processed data due to signed End User Agreements with the source institution. We had to modify the column labels in the vine dataset for it to work with the preprocessing code provided in the HENIN codebase. Please feel free to email us for processed code if you are running into trouble. 

### Dependencies
To run the HENIN model code, the following are required
- python>=3.5
- keras == 2.24
- tensorflow == 1.13
- gensim, network, nltk

Higher versions of tensor flow and keras are incompatible with the current HENIN codebase. Our experiments and comparison models can be run on google colab.

### Commands
To run the HENIN codebase, the datasets have to be placed into the same directory as the code. Ensure the filepath in preprocess.py matches your directory structure, and use the following command to preprocess the data.  

`python3 preprocess.py`

This step needs to be repeated for each dataset after modifying the filepath. 

The HENIN codebase uses 5-fold stratified cross-validation. Once the preprocessed files have been generated, use the following command to train and evaluate the HENIN model

`python3 train.py`

The provided notebooks can be uploaded to Google Colaboratory to preprocess and run the baseline and experimental models. The datasets have to be uploaded onto your google drive (file paths may have to be modified to match your directory). The cells can then be run in the notebook.

### Table of results

We used 5-fold stratified crossvalidation to evaluate the HENIN model with other baselines. The results we gained can be seen below. 

|Dataset   | Model | Accuracy  | Precision  | Recall  | F1 Score | 
|----------|-------|------|-------|------|------|
|Instagram | HENIN |0.893 | 0.847 | 0.789| 0.816|  
||  LR | 0.820 | 0.722 | 0.736 | 0.710 |
||RF | 0.804 | 0.880 | 0.423 | 0.558 |
||RNN | 0.772 | 0.743 | 0.468 | 0.531 |
||GRU | 0.805 | 0.764 | 0.539 | 0.625 |
|----------|-------|------|-------|------|------|
 |Vine | HENIN | 0.805 | 0.739 | 0.586 | 0.651 |  
 ||LR  | 0.759 | 0.681 | 0.542 | 0.619 |
 ||RF | 0.773 | 0.804 | 0.462 | 0.539 |
 ||RNN | 0.721 | 0.759 | 0.156 | 0.242 |
 ||GRU | 0.715 | 0.852 | 0.102 | 0.180 |
 
