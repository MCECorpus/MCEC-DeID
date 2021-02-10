# MCEC De-Identification Tool (MCEC DeID)

Documentation, manual, and code for de-identification and anonymization of MCEC email data that guided by the [HIPAA Safe-Harbor method](https://www.hhs.gov/hipaa/for-professionals/privacy/special-topics/de-identification/index.html) and [FERPA regulations](https://studentprivacy.ed.gov/node/548/). 

- [MCEC De-Identification Tool (MCEC DeID)](#mcec-de-identification-tool-mcec-deid)
  - [Overview](#overview)
    - [A) Source code](#a-source-code)
    - [B) De-identification and anonymization manual for the MCEC Project](#b-de-identification-and-anonymization-manual-for-the-mcec-project)
    - [C) Data stewardship (MCEC approach to data management)](#c-data-stewardship-mcec-approach-to-data-management)
  - [Why are de-identification and anonymization necessary?](#why-are-de-identification-and-anonymization-necessary)
  - [Is all this documentation necessary?](#is-all-this-documentation-necessary)
  - [Protecting participant data](#protecting-participant-data)
    - [MCEC's standpoint on data privacy and confidentiality](#mcecs-standpoint-on-data-privacy-and-confidentiality)
  - [Identifiers](#identifiers)
  - [De-identification and anonymization](#de-identification-and-anonymization)
    - [Tags](#tags)
  - [Project Organization](#project-organization)
  - [Changelog](#changelog)
  - [Contribute](#contribute)
  - [License](#license)
  - [Final Notes](#final-notes)

-------------------------

## Overview

This repository is part of the eco-system of the [Multilingual College Email Corpus Project](docs/Terms-and-definitions.md#multilingual-college-email-corpus-mcec). It contains source code and documentation for the de-identification and anonymization of [MCEC research data](docs/Terms-and-definitions.md#data). Please notice that we are pacing the public release of our source code and documentation, so you may find some sections of this documentation incomplete. If you have any questions please make sure to email the research team at `mcec.team[at]gmail[dot]com`.

You may find the description of the source code and documentation below. Please follow the links in there for the full content.

### A) Source code

- [src/README.md](src/README.md)

The `src` directory inside this repository hosts the code used to automatically aid the de-identification and anonymization of MCEC data and its documentation. There are two main modules:

1. RAD-ID: A rule-based algorithm designed to be the first-pass for data de-identification. It deals mostly with [direct identifiers](docs/Terms-and-definitions.md#direct-identifiers).
2. AnonyM: A machine-learning algorithm used to ensure that manual de-identification was successful. This is meant to be the first check after data has been anonymized. The second check is a manual check.

For more information about the [de-identification](docs/Terms-and-definitions.md##de-identified-data) and [anonymization](docs/Terms-and-definitions.md#anonymized-data) process as well as data collection, please refer to [section (C)](#c-data-stewardship-mcec-approach-to-data-management) below.

The code in this repository is used to processes email text files and makes a first as well as a last pass at de-identification using Safe-Harbor and FERPA-defined categories.

For all of our processes, email format changes are kept to a minimum except in the case of email footers which often contain more personal information than the entire body of their email (Su, Romero Diaz & Jia, Forthcoming).

Note that all of our software is written in Python (3.9+) and we are currently not accepting any external contributions.

### B) De-identification and anonymization manual for the MCEC Project

- [MCEC-DeID Manual (TBA)](docs/MCEC-deid-manual.md)

This is the manual exclusive to the de-identification - anonymization process of the MCEC corpus and should not be confused with the annotation manual, which is currently under development. For examples on corpus annotation manuals, please see the [ICAME Corpus manuals](http://korpus.uib.no/icame/manuals/).

### C) Data stewardship (MCEC approach to data management)

- [MCEC Data Stewardship Documentation](docs/MCEC-data-stewardship-documentation.md)

Documents how the MCEC Team manages data quality, integrity, accessibility, and security from collection to publication. It also outlines the workflows that integrate the MCEC-DeID source code with the manual checks for data de-identification and anonymization. The last section contains a list of resources related to everything contained in this repository.

## Why are de-identification and anonymization necessary?

A language corpus is an organized collection of text, usually around a specific topic. The goal of the [Multilingual College Email Corpus (MCEC)](docs/Terms-and-definitions.md#multilingual-college-email-corpus-mcec) is one of [many examples of publicly available language corpora](https://uclouvain.be/en/research-institutes/ilc/cecl/learner-corpora-around-the-world.html) that are used by researchers around the world to understand different language systems and human communication in general.

The release of written human data is permitted under University and federal regulations with certain restrictions:

"Entities releasing data should apply a consistent de-identification strategy to all of their data releases of a similar type (e.g., tabular and individual level data) and similar sensitivity level. It is advised that organizations document their data reporting rules in the documents describing their data reporting policies and privacy protection practices, such as a Data Governance Manual. (See PTAC’s Data Governance and Stewardship brief at https://studentprivacy.ed.gov/resources/issue-brief-data-governance-and-stewardship for more information on best practices in data governance.)"([Data De-identification: An Overview of Basic Terms, Privacy Technical Assistance Center, 2021-02-09](https://studentprivacy.ed.gov/sites/default/files/resource_document/file/data_deidentification_terms_0.pdf))

The [MCEC Project](docs/Terms-and-definitions.md#mcec-project) is an [IRB - approved research project at the University of Arizona](docs/Terms-and-definitions.md#data-collection). As such, there are measures in place to exclude [Personally identifiable information (PII)](docs/Terms-and-definitions.md#personally-identifiable-information-pii) from any published research data. Two of those measures are [data de-identification](docs/Terms-and-definitions.md#de-identified-data) and [data anonymization](docs/Terms-and-definitions.md#anonymized-data). First, data must be de-identified for the internal use of the [MCEC Research team](docs/Terms-and-definitions.md#mcec-team), who will then follow the [MCEC-defined processes](docs/MCEC-data-stewardship-documentation.md) to [anonymize](docs/Terms-and-definitions.md#anonymized-data) the data and prepare it for making it publicly available.

Both the [MCEC Research Team](docs/Terms-and-definitions.md#mcec-team) as well as the [University of Arizona](https://www.arizona.edu) are committed to protecting participant's privacy and confidentiality. 

## Is all this documentation necessary?

Yes. Not only does the University of Arizona [Human Subjects Protection Program](https://rgw.arizona.edu/compliance/human-subjects-protection-program/guidance-researchers) require researchers to keep a record of how participant data is processed and protected, but there are also [U.S. regulations](https://rgw.arizona.edu/compliance/human-subjects-protection-program/regulations) that require this documentation. For researchers:

"The importance of documentation for which values in health data correspond to PHI, as well as the systems that manage PHI, for the de-identification process cannot be overstated.  Esoteric notation, such as acronyms whose meaning are known to only a select few employees of a covered entity, and incomplete description may lead those overseeing a de-identification procedure to unnecessarily redact information or to fail to redact when necessary.  When sufficient documentation is provided, it is straightforward to redact the appropriate fields." [Preparation for De-identification, HIPAA, 2021/02/07](https://www.hhs.gov/hipaa/for-professionals/privacy/special-topics/de-identification/index.html#preparation)

## Protecting participant data

### MCEC's standpoint on data privacy and confidentiality

The MCEC Team is committed to protecting all personal data and FERPA-protected school records, even if this means lowering the usability of the public version of the MCEC corpus. Our participants' privacy comes first.

As with most academic language corpora, the MCEC keeps two versions of the relevant language data: (A) an internal version that is only available to the research team. This version is [de-identified](docs/Terms-and-definitions.md##de-identified-data)) and only the MCEC co-directors Damian Romero and Hanyu Jia have access to the de-identification table ([see our MCEC Keys (Codes) documentation](#MCEC-keys-codes.md)). The second version of our data will be public and anonymized. This anonymized data will be published via the [Research Data Repository](https://arizona.figshare.com) of the University of Arizona (also known as ReDATA).

There are a few reasons why the MCEC project does not anonymize participant data immediately upon collection. The first one is that we wish to provide our participants with the opportunity for retracting their data from any unpublished materials. Secondly, the University of Arizona Human Subjects Protection Program requires researchers to retain participant records for a number of years (see the [Data Security and Records Retention document](https://rgw.arizona.edu/sites/default/files/data_security_and_records_retention_v2020-04.pdf)).

Finally, in special cases, certain U.S. government officials may require us to disclose relevant records, for example if they are needed for law enforcement purposes. For more information, please visit the UArizona [HSPP page](https://rgw.arizona.edu/compliance/human-subjects-protection-program) as well as the Office of the Registrar's [FERPA page](https://www.registrar.arizona.edu/personal-information/family-educational-rights-and-privacy-act-1974-ferpa?topic=ferpa)

If you have any questions about the MCEC Project's data collection, de-identification and anonymization process, or making email text publicly available, the best way to get started is to consult our [`Publishing Email Data`](docs/MCEC-data-stewardship-documentation.md) document.

## Identifiers

The Multilingual College Email Corpus works under a [*repository-wide batch de-identification modality*](docs/Terms-and-definitions.md#modes-of-data-de-identification), which means that the whole MCEC dataset is de-identified soon after new data is obtained (usually each academic term). The de-identification process consists mainly in [redacting](docs/Terms-and-definitions.md#redaction-of-data) identifiers ([direct and indirect](docs/Terms-and-definitions.md##identifiers)) out of the data and replacing them by [tags](#tags). The redaction process is supplemented by the [suppression](docs/Terms-and-definitions.md#suppression-of-data) of information whenever the Research Team deems it necessary. The MCEC Team reserves the right to exclude any research data from publication, for example if it is the case that the relevant referents cannot be satisfactorily anonymized.

We base our de-identification methodology on two main resources: the [Health Insurance Portability and Accountability Act (HIPAA)](docs/Terms-and-definitions.md#health-insurance-portability-and-accountability-act-hipaa), and the [Family Educational Rights and Privacy Act (FERPA)](docs/Terms-and-definitions.md#family-educational-rights-and-privacy-act-ferpa). We use these two resources because they are well-known academic standards on data privacy.

While both HIIPAA and FERPA define what data counts as [personally identifiable information (PII)](docs/Terms-and-definitions.md#personally-identifiable-information-pii), HIPAA provides a clear de-identification method known as the [Safe Harbor method](docs/Terms-and-definitions.md#safe-harbor-method). Additionally, FERPA regulates students' [education records](docs/Terms-and-definitions.md#education-records), which are a big part of the MCEC project's records since [student academic emails are considered educational records by the University of Arizona](https://www.registrar.arizona.edu/personal-information/family-educational-rights-and-privacy-act-1974-ferpa?topic=ferpa).

To learn more about identifiers, please refer to our [Terms and Definitions](docs/Terms-and-definitions.md#identifiers) document.

## De-identification and anonymization

As mentioned above, the MCEC Project uses the Safe Harbor method to de-identify the data. This is done by substituting direct and indirect identifiers with [tags](#tags). See the fictional example below:

```
<<Document name: "Susan-to-Kirke-1.txt">>

Dear Professor Kirke,

My classmate Peter and I have finished our English homework. Where can we turn it in?

Sincerely,

Susan
```

After applying the Safe Harbor method using a algorithm followed by manual human de-identification, the example above is transformed into:

```
<<Document name: "de-identified-file-name 1.txt">>

Dear [[last-name[instructor]]],

My classmate [[first-name[student][2]]] and I have finished our [[subject-name]] homework. Where can we turn it in?

Sincerely,

[[first-name[student][1]]]
```

While the data in the second example is certainly more secure, it is still not ready to be made publicly available as part of the MCEC. For that, there is a last computer (Machine Learning) and manual human check. Then, the `de-identified-file-name` is [anonymized](docs/Terms-and-definitions.md#anonymized-data) so that the email cannot be linked back to the original student record system nor to other emails produced by the same student:

```
<<Document name: "anonymized-file-name 1.txt">>

Dear [[last-name[instructor]]],

My classmate [[first-name[student][2]]] and I have finished our [[subject-name]] homework. Where can we turn it in?

Sincerely,

[[first-name[student][1]]]
```

In the example above notice that the file name has changed from `<<de-identified-file-name.txt>>` to `<<anonymized-file-name.txt>>`. 

The whole process/workflow from data collection to anonymization is described in our [Publishing Email Data documentation](docs/MCEC-data-stewardship-documentation.md).

### Tags

For a definition of what a tag is in the context of the [MCEC DeID](docs/Terms-and-definitions.md#mcec-deid) as well as the types of tags used by the MCEC Team and the tagging style manual, please read the [Tags document](docs/Tags.md).

The following documents list map MCEC identifiers to their corresponding tags:

[HIPAA Safe Harbor tags](docs/HIPAA-tags.md)

[MCEC-specific tags (incorporates the FERPA-specific tags)](docs/MCEC-specific-tags.md)

[Sub-tags (both for HIPAA and MCEC-specific)](docs/Sub-tags.md)

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
## Changelog

v0.0.1:

 * Start MCEC DeID Repository
 * Project organization
 * Tag documentation
 * LICENCE
 * README.md
 * docs/Anonymization-team-workflows.md
 * docs/De-identification-team-workflows.md
 * docs/Educational-records-tags.md
 * docs/HIPAA-tags.md
 * docs/MCEC-data-stewardship-documentation.md
 * docs/MCEC-deid-manual.md
 * docs/MCEC-keys-codes.md
 * docs/MCEC-specific-tags.md
 * docs/MCEC-team-roles.md
 * docs/Sub-tags.md
 * docs/Tags.md
 * docs/Terms-and-definitions.md

## Contribute

If you or your department is interested in being part of the MCEC project, please contact the MCEC team (mcec.team[at]gmail.com) where someone will put you in contact with our Outreach Coordinator, Miss. Wei Xu, directly.

## License

The code inside this project is licensed under the [MIT License](https://opensource.org/licenses/MIT) - see the [LICENSE](LICENSE) file for details.

## Final Notes

The project structure for this repository was generated using the [Reproducible Science cookiecutter boilerplate by Mario Krapp (2016)](https://github.com/mkrapp/cookiecutter-reproducible-science)

------------
