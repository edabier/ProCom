# ProCom 2025: Detect communicative intents in online influence campaigns
By Ahmed Laaroussi, Amine Rahim, Anna Charles, Edgard Dabier & Elouan Marsot

## Project overview

Our project started from the observation that more and more **influence campaigns** (such as the [RNN campaign](https://www.sgdsn.gouv.fr/publications/maj-19062023-rrn-une-campagne-numerique-de-manipulation-de-linformation-complexe-et)) appear in online contents (social networks, online news...). These campaigns represent a real danger for the public opinion and public critical mind. 
Our project is thus motivated by the will to **create a self-defense tool** for the internet users to be warned when facing such influence intended content.

Our main hypothesis is that we can use the information of what **values** are present in a text to determine whether or not this same text is trying to influence the reader's opinion.
Starting from thishypothesis, our goal was to develop a tool that would automatically detect values inside sentences to then be able to detect influence articles.

This process of value detection was highly motivated and inspired by the [Human Value Detection task](https://touche.webis.de/clef24/touche24-web/human-value-detection.html) at Touché 2024.

## Values detection

*For a detailed explaination of our method, please refer to the `project-report.pdf`.*

### Requirements:

To use this code, one need to have access to an annotated sentences dataset with the following format (preferably, request an access to the [Touché dataset](https://touche.webis.de/clef24/touche24-web/human-value-detection.html)):

  A dataset folder containing **training**, **validation** and **test** subfolders.
  For each subfolder, a `sentences.tsv` file containing the text data, and a `labels.tsv` file containing the annotations (as described in the `project-report.pdf`)

We recommand running the code contained in the `final-deliverable` folder inside an environment containing the following libraries:

'''
transformers
torch
numpy
datasets
matplotlib
seaborn
pandas
scikit-learn
'''

To install all the packages, do pip3 install -r requirements.txt.

### Running the code

Our main detection process is defined in the `final-deliverable` folder and is divided into 3 steps:

- `preprocessing/ipynb`: This notebook preprocesses the dataset into *datasets* objects that will be used in the training phase. The preprocessing method is described in the report. These datasets objects are saved in a `datasets` folder.

- `training.ipynb`: This notebook contains the actual definition of the model, based on [RoBERTa-base](https://huggingface.co/FacebookAI/roberta-base). The training results are saved in a `results` folder.

- `result-visualization.ipynb`: This notebook uses the trained model to perform predictions on the test dataset, and then computes a custom *confusion matrix*. This notebook requires a previously trained model, one can find our training results here: [access drive](https://drive.google.com/drive/folders/15P2hjffdsdZbpM3zdjKV2vtGllEdgIZW?usp=sharing)

