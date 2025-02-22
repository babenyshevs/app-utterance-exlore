utterances-exploration
==============================

# Data:

<img src="./reports/figures/solution_rate.png" width="900">

exploration of customer utterances (clustering)

Project Organization
------------

    ├── LICENSE
    ├── README.md          <- The top-level README for developers using this project.
    ├── data
    │   ├── external       <- Data from third party sources.
    │   ├── interim        <- Intermediate data that has been transformed.
    │   ├── processed      <- The final, canonical data sets for modeling.
    │   └── raw            <- The original, immutable data dump.
    │
    ├── docs               <- A default Sphinx project; see sphinx-doc.org for details
    │
    ├── models             <- Trained and serialized models, model predictions, or model summaries
    │
    ├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
    │                         the creator's initials, and a short `-` delimited description, e.g.
    │                         `1.0-jqp-initial-data-exploration`.
    │
    ├── references         <- Data dictionaries, manuals, and all other explanatory materials.
    │
    ├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
    │   └── figures        <- Generated graphics and figures to be used in reporting
    │
    ├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
    │                         generated with `pip freeze > requirements.txt`
    │
    ├── setup.py           <- makes project pip installable (pip install -e .) so src can be imported
    ├── src                <- Source code for use in this project.
    │   ├── __init__.py    <- Makes src a Python module
    │   │
    │   ├── data           <- Scripts to download or generate data
    │   │   └── make_dataset.py
    │   │
    │   ├── features       <- Scripts to turn raw data into features for modeling
    │   │   └── build_features.py
    │   │
    │   ├── models         <- Scripts to train models and then use trained models to make
    │   │   │                 predictions
    │   │   ├── predict_model.py
    │   │   └── train_model.py
    │   │
    │   └── visualization  <- Scripts to create exploratory and results oriented visualizations
    │       └── visualize.py
    │
    └── tox.ini            <- tox file with settings for running tox; see tox.readthedocs.io


--------

# Steps to follow after creating/cloning a project
## create and activate virtual environment

    python -m venv .venv
    .venv/Scripts/activate

## create GIT repo (optional)
alternative way is to create a remote repository, clone it locally and copy create ccds project into it.

    git init

## initial commit to the new repo

    git add .
    git commit -m "default initial commit"

## checkout develop branch (optional)
for small project everything might be stored in master

    git checkout -b develop

## install requirements

    python -m pip install -U pip setuptools wheel
    python -m pip install -r requirements.txt

## install spacy model

the most straight forward way is

    python -m spacy download de_core_news_lg

This can be although tedious because of the proxy settings. 

Alternative approach is to download respective wheel of a  <a target="_blank" href="https://spacy.io/models/">trained language pipeline</a> and place into models folder, if model is large, add it to gitignore section. Finally, install the package.

    pip install models/<model_name>

This approach is sometimes preferable, because one can control which version of model (s)he would have and keep this artifact, say, in Azure Blob,  AWS S3 bucket, etc.

To see, which spacy models are downloaded and installed use:

    python -m spacy info

To uninstall use $pip$:

    pip uninstall en-core-web-sm

<p><small>Project based on the <a target="_blank" href="https://drivendata.github.io/cookiecutter-data-science/">cookiecutter data science project template</a>. #cookiecutterdatascience</small></p>
