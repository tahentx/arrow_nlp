Topic Modeling the Apache Arrow repository.
==============================

Topic modeling the Apache Arrow repo (commit comments and pull requests) using non-negative matrix factorization.

Project Organization
------------

    ├── LICENSE
    ├── Makefile           <- Makefile with commands like `make data` or `make train`
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

###Technology stack
<p align="center">
  <img src="/images/stack.png" width="550" title="hover text">
</p>
 
 --------

###Model Selection Rationale
<p>Inspired by a software development podcast in which the topic was working effectively with legacy code, I thought it would be interesting to apply natural language processing to an unfamiliar codebase in order to get a sense of what's important (to those actively commenting and committing anyway). Key themes could provide helpful context before actually diggin into the code. With this idea, I knew that in a technical sense, this was a topic modeling problem.</p>
<p>I learned of Non-negative Matrix Factorization (NMF) through a colleague who was pleased with his implementation of the model on a twitter dataset. Commit messages, I would argue, are similar in size and structure to tweets, so I could assume the data would be of similar shape. At a minimum, it would set a good baseline.  </p>
<p>The other widely used algorithm for topic modeling is Latent Semantic Analysis. As I understand it, the strength of LSA is in surfacing the relationships between documents, which I did not consider a primary goal of my project. The relationship between commits, pull requests, and the associated comments are well-defined.</p>

 --------

