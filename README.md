# MCEC De-Identification Tool (MCEC DeID)

Documentation, manual, and code for de-identification and anonymization of MCEC email data that guided by the [HIPAA Safe-Harbor method](https://www.hhs.gov/hipaa/for-professionals/privacy/special-topics/de-identification/index.html) and [FERPA regulations](https://studentprivacy.ed.gov/node/548/). 

- [MCEC De-Identification Tool (MCEC DeID)](#mcec-de-identification-tool-mcec-deid)
  - [Overview](#overview)
  - [Why are de-identification and anonymization necessary?](#why-are-de-identification-and-anonymization-necessary)
  - [Is all this documentation necessary?](#is-all-this-documentation-necessary)
  - [Protecting participant data](#protecting-participant-data)
    - [MCEC's standpoint on data privacy and confidentiality](#mcecs-standpoint-on-data-privacy-and-confidentiality)
  - [Identifiers](#identifiers)
  - [De-identification and anonymization](#de-identification-and-anonymization)
    - [Tags](#tags)
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

This repository:

A) Hosts the code used to automatically aid the de-identification of [MCEC](docs/Terms-and-definitions.md#multilingual-college-email-corpus-mcec) data and its documentation.

B) Contains documentation for the de-identification and anonymization manual for the MCEC Project. For the documentation, please refer to our Publishing Email Data document [here](docs/Publishing-email-data.md).

C) Contains the documentation for the workflows that integrate the MCEC-DeID source code with the manual checks for data de-identification and anonymization.

The code in this repository is used to processes email text files and makes a first as well as a last pass at de-identification using Safe-Harbor and FERPA-defined categories.

For all of our processes, email format changes are kept to a minimum except in the case of email footers which often contain more personal information than the entire body of their email (Su, Romero Diaz & Jia, Forthcoming).

## Why are de-identification and anonymization necessary?

A language corpus is an organized collection of text, usually about a specific topic. The goal of the [Multilingual College Email Corpus (MCEC)](docs/Terms-and-definitions.md#multilingual-college-email-corpus-mcec) is one of many example of publicly available language corpora that is used by researchers around the world to understand human communication. As such, protecting participant's [privacy and confidentiality](docs/Terms-and-definitions.md#privacy-and-confidentiality) is of outmost important. Both the [MCEC Research Team](docs/Terms-and-definitions.md#mcec-team) as well as the [University of Arizona](https://www.arizona.edu) are committed to protecting participant's privacy and confidentiality.

For this reason, data must be [de-identified](docs/Terms-and-definitions.md#de-identified-data) for internal use of the [MCEC Research team](docs/Terms-and-definitions.md#mcec-team), who will follow the [MCEC-defined processes](docs/Publishing-email-data.md) to [anonymize](docs/Terms-and-definitions.md#anonymized-data) the data and prepare it for making it publicly available.
 
Entities releasing data should apply a consistent de-identification strategy to all of their data releases of a similar type (e.g., tabular and individual level data) and similar sensitivity level. It is advised that organizations document their data reporting rules in the documents describing their data reporting policies and privacy protection practices, such as a Data Governance Manual. (See PTAC’s Data Governance and Stewardship brief at https://studentprivacy.ed.gov/resources/issue-brief-data-governance-and-stewardship for more information on best practices in data governance.)

https://studentprivacy.ed.gov/sites/default/files/resource_document/file/data_deidentification_terms_0.pdf

## Is all this documentation necessary?

Yes. Not only does the University of Arizona [Human Subjects Protection Program](https://rgw.arizona.edu/compliance/human-subjects-protection-program/guidance-researchers) require researchers to keep a record of how participant data is processed and protected, but there are also [U.S. regulations](https://rgw.arizona.edu/compliance/human-subjects-protection-program/regulations) that require this documentation. For researchers:

"The importance of documentation for which values in health data correspond to PHI, as well as the systems that manage PHI, for the de-identification process cannot be overstated.  Esoteric notation, such as acronyms whose meaning are known to only a select few employees of a covered entity, and incomplete description may lead those overseeing a de-identification procedure to unnecessarily redact information or to fail to redact when necessary.  When sufficient documentation is provided, it is straightforward to redact the appropriate fields." [Preparation for De-identification, HIPAA, 2021/02/07](https://www.hhs.gov/hipaa/for-professionals/privacy/special-topics/de-identification/index.html#preparation)

## Protecting participant data

### MCEC's standpoint on data privacy and confidentiality

The MCEC Team is committed to protecting all personal data and FERPA-protected school records, even if this means lowering the usability of the public version of the MCEC corpus. Our participants' privacy comes first.

As with most academic language corpora, the MCEC keeps two versions of the relevant language data: (A) an internal version that is only available to the research team. This version is [de-identified](#de-identification-vs-anonymization)) and only the MCEC co-directors Damian Romero and Hanyu Jia have access to the de-identification table ([see below](#re-identification-keys)). The second version of our data will be public and anonymized. This anonymized data will be published via the [Research Data Repository](https://arizona.figshare.com) of the University of Arizona (also known as ReDATA).

There are a few reasons why the MCEC project does not anonymize participant data immediately upon collection. The first one is that we wish to provide our participants with the opportunity for retracting their data from any unpublished materials. Secondly, the University of Arizona Human Subjects Protection Program requires researchers to retain participant records for a number of years (see the [Data Security and Records Retention document](https://rgw.arizona.edu/sites/default/files/data_security_and_records_retention_v2020-04.pdf)).

Finally, in special cases, certain U.S. government officials may require us to disclose relevant records, for example if they are needed for law enforcement purposes. For more information, please visit the UArizona [HSPP page](https://rgw.arizona.edu/compliance/human-subjects-protection-program) as well as the Office of the Registrar's [FERPA page](https://www.registrar.arizona.edu/personal-information/family-educational-rights-and-privacy-act-1974-ferpa?topic=ferpa)

If you have any questions about the MCEC Project's data collection, de-identification and anonymization process, or making email text publicly available, the best way to get started is to consult our [`Publishing Email Data`](docs/Publishing-email-data.md) document.

## Identifiers

The Multilingual College Email Corpus is a [Repository-wide batch de-identified](docs/Terms-and-definitions.md#modes-of-data-de-identification) project, which means that the whole dataset is de-identified soon after new data is obtained (usually each academic term).

We base our de-identification methodology on two main resources: the Health Insurance Portability and Accountability Act (HIPAA), and the Family Educational Rights and Privacy Act (FERPA). We use these two resources because they are well-known academic standards on data privacy.

While both HIIPAA and FERPA define what data counts as [personally identifiable information (PII)](docs/Terms-and-definitions.md#personally-identifiable-information-pii), HIPAA provides a clear de-identification method known as the [Safe Harbor method](docs/Terms-and-definitions.md#safe-harbor-method). Additionally, FERPA regulates students' [education records](docs/Terms-and-definitions.md#education-records), which are a big part of the MCEC project's records. Additionally, [academic emails are considered educational records by the University of Arizona](https://www.registrar.arizona.edu/personal-information/family-educational-rights-and-privacy-act-1974-ferpa?topic=ferpa).

To learn more about identifiers, please refer to our [Terms and Definitions](docs/Terms-and-definitions.md#identifiers) document.

## De-identification and anonymization

As mentioned above, the MCEC Project uses the Safe Harbor method to de-identify the data. This is done by substituting direct and indirect identifiers with [tags](#tags). See the fictional example below:

```
<<Susan to Kirke.txt>>

Dear Professor Kirke,

My classmate Peter and I have finished our English homework. Where can we turn it in?

Sincerely,

Susan
```

After applying the Safe Harbor method using a algorithm followed by manual human de-identification, the example above is transformed into:

```
<<de-identified-file-name.txt>>

Dear [[last-name[instructor]]],

My classmate [[first-name[student][2]]] and I have finished our [[subject-name]] homework. Where can we turn it in?

Sincerely,

[[first-name[student][1]]]
```

While the data in the second example is certainly more secure, it is still not ready to be made publically available as part of the MCEC. For that, there is a last computer (Machine Learning) and manual human check. Then, the `de-identified-file-name` is [anonymized](docs/Terms-and-definitions.md#anonymized-data) so that the email cannot be linked back to the original student record system nor to other emails produced by the same student:

```
<<anonymized-file-name.txt>>

Dear [[last-name[instructor]]],

My classmate [[first-name[student][2]]] and I have finished our [[subject-name]] homework. Where can we turn it in?

Sincerely,

[[first-name[student][1]]]
```

In the example above notice that the file name has changed from `<<de-identified-file-name.txt>>` to `<<anonymized-file-name.txt>>`. 

The whole process/workflow from data collection to anonymization is described in our [Publishing Email Data documentation](docs/Publishing-email-data.md).

### Tags

Unless otherwise noted with an asterisk (*), these items are pooled from the Safe-Harbor method:

The following lists maps Safe Harbor identifiers to the MCEC-defined de-identification items and tags.

[HIPAA Safe Harbor tags](docs/HIPAA-tags.md)

[MCEC-specific tags (incorporates the FERPA-specific tags)](docs/MCEC-specific-tags.md)

[Sub-tags (both for HIPAA and MCEC-specific)](docs/Sub-tags.md)

#### Types of tags

Apart from the "Tag classification" mentioned above (Safe Harbor tags, MCEC-Specific tags), tags are divided into two types: main tags and sub-tags (aka. 'embedded tags').

Main tags are always used to replace identifiable information. These are signaled by the [[double square-brackets]] surrounding them.

Subtags are used to distinguish between more than one identifier item of the same kind, for instance if there are two names, these tags will allow the reader to differentiate between both referents ([instructor] vs [student] or [student][1] vs [student][2]). These tags are embedded within other tags. There can be up to two tags embedded within a main tag.

Sub-tags contain only one set of square brackets, as opposed to main tags, which have two.

Examples:

Main tag:
- [[main-tag]]

Main tag with one sub-tag:
- [[main-tag[sub-tag1][sub-tag2]]]

Main tag with one sub-tag:
- [[main-tag[sub-tag1][sub-tag2]]]

#### Tag formatting:

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

```
.
├── AUTHORS.md
├── LICENSE
├── README.md
├── bin                <- Binary code (not tracked by git)
├── config             <- Configuration files
├── data
│   ├── external       <- Data from third party sources [ENRON corpus, etc]
│   ├── interim        <- Data examples made of fictitious emails
│   ├── processed      <- (not tracked by git) The final de-identified and anonymized data
│   └── raw            <- (not tracked by git) Original data to be de-identified
├── docs               <- Documentation
├── notebooks          <- Ipython or R notebooks
├── reports            <- For a manuscript source, e.g., LaTeX, Markdown, etc., or any project reports
│   └── figures        <- Figures for manuscripts or reports
└── src                <- Source code for this project
    ├── data           <- Scripts and programs to process data
    ├── external       <- Any external source code, e.g., pull other git projects, or external libraries
    ├── models         <- Source code for your own model e.g, word-vectors
    ├── tools          <- Any helper scripts go here
    └── visualization  <- Scripts for visualizing results
```

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
