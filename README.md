# MCEC De-Identification Tool (MCEC DeID)

Automatic de-identifier of email data that follows the [HIPAA Safe-Harbor method](https://www.hhs.gov/hipaa/for-professionals/privacy/special-topics/de-identification/index.html)


- [MCEC De-Identification Tool (MCEC DeID)](#mcec-de-identification-tool-mcec-deid)
  - [Overview](#overview)
  - [Tags](#tags)
    - [Types of tags](#types-of-tags)
    - [Type formatting:](#type-formatting)
  - [Project Organization](#project-organization)
  - [Getting Started](#getting-started)
    - [Requirements](#requirements)
    - [Installation Instructions](#installation-instructions)
  - [Contribute](#contribute)
  - [Changelog](#changelog)
  - [License](#license)
  - [Final Notes](#final-notes)

-------------------------

## Overview

Processes email text files and makes a first pass at de-identification using the Safe-Harbor method categories:

Whenever possible, email format changes are kept to a minimum for archival purposes, except in the case of email footers which often contain more personal information than the entire body of their email (Su & Romero Diaz, Forthcoming).

## Tags

The Safe Harbor method outlines a set of identifiers to be stripped from any publicly available information. These identifiers are linked with "the individual or of relatives, employers, or household members of the individual" ([U.S. Department of Health & Human Services](https://www.hhs.gov/hipaa/for-professionals/privacy/special-topics/de-identification/index.html#safeharborguidance), 2021/01/31). We have expanded these identifiers to include data specific to our needs. For instance, the Safe Harbor "A" identifier category (Names) has been expanded [here](insert-link) to include hypocorisms, which are relatively frequent in academic emails. See coding manual [examples](insert-link).

Unless otherwise noted with an asterisk (*), these items are pooled from the Safe-Harbor method:

The following lists maps Safe Harbor identifiers to the MCEC-defined de-identification items and tags.

Safe Harbor tags

MCEC-specific tags

Sub-tags (both for safe-harbor and MCEC-specific)

### Types of tags

Appart from the "Tag classification" mentioned above (Safe Harbor tags, MCEC-Specific tags), tags are divided into two types: main tags and sub-tags (aka. 'embedded tags').

Main tags are always used to replace identifiable information. These are signaled by the [[double square-brackets]] surrounding them.

Subtags are used to distinguish between more than one identifier item of the same kind, for instance if there are two names, these tags will allow the reader to differenciate between both referents ([instructor] vs [student] or [student][1] vs [student][2]). These tags are embedded within other tags. There can be up to two tags embedded within a main tag.

Sub-tags contain only one set of square brackets, as opposed to main tags, which have two.

Examples:

Main tag:
- [[main-tag]]

Main tag with one sub-tag:
- [[main-tag[sub-tag1][sub-tag2]]]

Main tag with one sub-tag:
- [[main-tag[sub-tag1][sub-tag2]]]

### Type formatting:

Tags are always small-cased:

Incorrect use of casing:
- [[Main-tag]]
- [[Main-Tag]]
- [[main-Tag]]

Sub-tags cannot be embedded within other sub tags. In other words, there is only one level of embedding (embedding is not recurrent). 

Incorrect use of sub-tags (main tag > sub-tag > sub-tag):
- [[main-tag[sub-tag1[sub-tag2]]]]

Notice that there is no spacing between square brackets when using sub-tags.

Incorrect spacing (any spacing inside a main tag is considered incorrect):
- [[main-tag [sub-tag1]   [sub-tag2]]]

## Project Organization

    .
    ├── AUTHORS.md
    ├── LICENSE
    ├── README.md
    ├── bin
    ├── config
    ├── data
    │   ├── external
    │   ├── interim
    │   ├── processed
    │   └── raw
    ├── docs
    ├── notebooks
    ├── reports
    │   └── figures
    └── src
        ├── data
        ├── external
        ├── models
        ├── tools
        └── visualization

## Getting Started

Follow this instructions to install and run the email_de-identifier module on your computer.

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

- You can check your installation by running `conda list mcecdeid`

## Contribute

If you wish to contribute please contact Damian Romero directly and make sure you are familiar with `git flow`, `git` and `GitHub` software development.

For learning `git flow` you can consult Damian's notes here: https://github.com/damian-romero/gitflow_toy/

## Changelog

v0.0.1:
 * Tag documentation (in progress)
 * Project organization
 * README.md #2, #4, #6
 * `images/` including `EmG-Logo.png`

## License

This project is licensed under the [MIT License](https://opensource.org/licenses/MIT) - see the [LICENSE](LICENSE) file for details.

## Final Notes

__*Progress is saved to a file called `pickled_instructors_<TERMyy>`. Please do not delete this file nor the folder where it is stored until we have aggregated this information to our safe archives.__

The project structure for this repository was generated using the [Reproducible Science cookiecutter boilerplate by Mario Krapp (2016)](https://github.com/mkrapp/cookiecutter-reproducible-science)

------------
