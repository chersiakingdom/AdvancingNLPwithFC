# AdvancingNLPwithFC

This repository reference all code used in the experiments described in the following paper: 
Nora Hollenstein, Maria Barrett, Marius Troendle, Francesco Bigiolli, Nicolas Langer & Ce Zhang. _Advancing NLP with Cognitive Language Processing Data_. 2019.
https://arxiv.org/abs/1904.02682


# Overall Data
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
## Data
In addition to this code, you will need the following data:
- The Google 300 dimensional embeddings from https://github.com/mmihaltz/word2vec-GoogleNews-vectors. The embedding file must be placed in the folder embeddings/.
- The ZuCo data in 2018 format. Those data must be placed in the Data_to_preprocess/ folder.

## Code
1. You will then need an environment with the following packages:

h5py 2.7.1
matplotlib 2.2.3
mxnet 1.0.0.post2 
nltk 3.3
numpy 1.14.2
pandas 0.20.3
pip 18.0
scikit-learn 0.19.0
scipy 0.19.1
seaborn 0.9.0
setuptools 39.0.1
statsmodels 0.9.0
tensorboard 1.7.0
tensorflow 1.7.0
tflearn 0.3.2
wheel 0.30.0

2. After setting up the environment and all the data, you will need to preprocess them to create the training data. To do that run python3 create_modeling_data.py from this directory.


3. Now you can run all experiments via these three scripts:

- run_features_model.py for the experiment on ZuCo data only.
  e.g. python3 run_features_model.py -we -et -eeg -b -s -opt
- run_stts_embedding_experiment.py for the experiment on SST data with Cross-Validation.
  e.g. python3 run_stts_embedding_experiment.py -we -et -eeg -b -s -opt
- run_stts_embedding_experiment2.py for the experiment on SST data with the official train, dev and test division.
  e.g. python3 run_stts_embedding_experiment2.py -we -et -eeg -b -s -opt

The parameters for those runs are:
-v if you want a verbose output
-b if you want the binary experiment
-we if you want word embeddings to be used
-et if you want eye-tracking to be used
-eeg if you want eeg signal to be used
-s if the data should be saved
-opt if optimized parameters should be added \


