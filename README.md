# AdvancingNLPwithFC

This repository reference all code used in the experiments described in the following paper: 
Nora Hollenstein, Maria Barrett, Marius Troendle, Francesco Bigiolli, Nicolas Langer & Ce Zhang. _Advancing NLP with Cognitive Language Processing Data_. 2019.
https://arxiv.org/abs/1904.02682


# Data
The original Zurich Cognitive Language Processing Corpus (ZuCo) corpus can be found here: https://osf.io/q3zws/
! BE AWARE ! you need to download task1- SR/Matlab files, task2 - NR/Matlab files in 2018 version, not 2019.

# Relation Classification
## Preprocessing
### Word embeddings
Download the pre-trained "Glove embeddings" or train your own and put in 'embeddings/'

### Part-of-speech tags (PoS tag)
 1. Download the Stanford CoreNLP. and run server
 2. Use the script 'annotate_pos_tags.py' to generate the PoS tags.
 3. Move the new pos_tags.txt file into 'preprocessing/'
 
### Relative positions
Use the script 'calculate_relative_positions.py' to generate the relative position files.

## Training 
### Configuration
Set your configurations in the 'config.yml' file

### Prerequisites
Python3, tensorflow, numpy, etc.

### Training a model
CUDA_VISIBLE_DEVICES=1 python train_relext.py config.yml


# Sentiment Analysis



