# MCEC De-Identification Source Code (RAD-ID and AnonyM)

- [MCEC De-Identification Source Code (RAD-ID and AnonyM)](#mcec-de-identification-source-code-rad-id-and-anonym)
  - [Overview](#overview)
  - [Project Organization](#project-organization)
  - [Getting Started](#getting-started)
    - [Requirements](#requirements)
    - [Installation Instructions](#installation-instructions)
  - [Changelog](#changelog)
  - [Contribute](#contribute)

-------------------------

## Overview

- MCEC RAD-ID - Rule Algorithm for De-identification (TBA)
- MCEC AnonyM - Anonymization with Machine Learning tool (TBA)

This repository hosts the code used to automatically aid the de-identification and anonymization of MCEC data and its documentation. There are two main modules:

1. RAD-ID: A rule-based algorithm designed to be the first-pass for data de-identification. It deals mostly with [direct identifiers](docs/Terms-and-definitions.md#direct-identifiers).
2. AnonyM: A machine-learning algorithm used to ensure that manual de-identification was successful. This is meant to be the first check after data has been anonymized. The second check is a manual check.

For more information about the [de-identification](docs/Terms-and-definitions.md##de-identified-data) and [anonymization](docs/Terms-and-definitions.md#anonymized-data) process as well as data collection, please refer to [section (C)](#c-data-stewardship-mcec-approach-to-data-management) below.

The code in this repository is used to processes email text files and makes a first as well as a last pass at de-identification using Safe-Harbor and FERPA-defined categories.

For all of our processes, email format changes are kept to a minimum except in the case of email footers which often contain more personal information than the entire body of their email (Su, Romero Diaz & Jia, Forthcoming).

Note that all of our software is written in Python (3.9+) and we are currently not accepting any external contributions.

## Project Organization

```
..
├── config             <- Configuration files
├── data
│   ├── external       <- Data from third party sources [ENRON corpus, etc]
│   ├── interim        <- Data examples made of fictitious emails
│   ├── processed      <- (not tracked by git) The final de-identified and anonymized data
│   └── raw            <- (not tracked by git) Original data to be de-identified
.
└── src                <- Source code for this project
    ├── data           <- Scripts and programs to process data
    ├── external       <- Any external source code, e.g., pull other git projects, or external libraries
    ├── models         <- Source code for your own model e.g, word-vectors
    ├── tools          <- Any helper scripts go here
    └── visualization  <- Scripts for visualizing results
```

## Getting Started

Follow this instructions to install and run the RAD-ID and AnonyM modules on your computer.

### Requirements

1. Python (3.9) and up

### Installation Instructions

#### If you don't have a [`conda` environment](https://realpython.com/effective-python-environment/)

```bash
# On Windows
> cd \path\to\email_de-identifier\folder
> python setup.py develop

# On MacOS
$ cd /path/to/email_de-identifier/folder
$ (sudo) python setup.py develop
```

- You may need to run as administrator (`sudo` in MacOS, `runas` in Windows)
- Now you can run the program

```bash
# If your Python command is just `python` do:
python run.py

# If your Python command is `python3` do:
python3 run.py
```

#### If you have a [`conda` environment](https://realpython.com/effective-python-environment/)

- Create a new conda environment named `deid` with python=3.9

```bash
# Create a new conda environment named mcec with python=3.9
conda create -n deid python=3.9
```

- Activate your new environment

```bash
conda activate deid
```

- Make sure that the `email_de-identifier` software folder is not compressed (unzip it if necessary)
- Open the command prompt or terminal in your computer
- [Change directories](https://www.howtogeek.com/659411/how-to-change-directories-in-command-prompt-on-windows-10/#:~:text=If%20the%20folder%20you%20want,window%2C%20and%20then%20press%20Enter.&text=The%20directory%20you%20switched%20to%20will%20be%20reflected%20in%20the%20command%20line.) to the `email_de-identifier` software folder
- Type `python setup.py develop` and enter on your console

```bash
# On Windows
(deid) > cd \path\to\email_de-identifier\folder
(deid) > python setup.py develop

# On MacOS
(deid) $ cd /path/to/email_de-identifier/folder
(deid) $ (sudo) python setup.py develop
```

- You can check your installation by running `conda list deid`

## Changelog

v0.0.1:

 * Start MCEC DeID Repository

## Contribute

If you wish to contribute please contact Damian Romero directly and make sure you are familiar with `git flow`, `git` and `GitHub` software development.

For learning `git flow` you can consult Damian's notes here: https://github.com/damian-romero/gitflow_toy/
