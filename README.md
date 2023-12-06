# Multi-Cancer Image Classification Using Convolutional Neural Networks
By William English and Michael Miller of the University of Central Florida
December 6, 2023

This repo contains the scaffolding for training a Convolutional Neural Network on Kaggle's Multi-Cancer dataset, available [here](https://www.kaggle.com/datasets/obulisainaren/multi-cancer/data). This research was performed as an end-of-course project for the Fall 2023 CAP5415 Computer Vision course at UCF, taught by Dr. Yogesh Rawat. Our research summary and dissertation can be found in [the PDF in this repository](CAP5415_course_project_2023_Will_and_Michael.pdf). 

## Setup

Create a python virtual environment and install the requirements. This can either be done using `venv`:

```bash
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

or using `conda`, which we recommend because it has Jupyter Notebook installed right off the bat:
```bash
conda env create -f environment.yml
conda activate cancer-env
```
If this does not work, this is a valid alternative:
```bash
conda create -n cancer-env pip
conda activate cancer-env
pip install -r requirements.txt
```

To install the database, use Kaggle's API to install the Multi-Cancer dataset. 
```bash
kaggle datasets download -d obulisainaren/multi-cancer
```

Depending on how you choose to `unzip` the folder, you will want to change the `base_dir` and `path_prefix` variables found in `TrainClassifiers.ipynb` and `val.ipynb`. 

## Running our model

Depending on the HPC architecture you are using for this, you may be able to use VS Code to log in and run our `.ipynb` files remotely. In instances like UCF's Newton architecture, we recommend referring to [this article](https://alexanderlabwhoi.github.io/post/2019-03-08_jpn_slurm/), which describes the techniques used by Mr. Miller for model validation.

`TrainClassifiers.ipynb` is used to train the classifiers, and `val.ipynb` is used to produce the figures we show in our final document. For your convenience, we have already provided pre-trained models in the `TrainedModels` folder.