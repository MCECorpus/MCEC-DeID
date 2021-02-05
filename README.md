# MCEC De-Identification Tool (MCEC DeID)

Automatic de-identifier of email data that follows the [HIPAA Safe-Harbor method](https://www.hhs.gov/hipaa/for-professionals/privacy/special-topics/de-identification/index.html)


- [MCEC De-Identification Tool (MCEC DeID)](#mcec-de-identification-tool-mcec-deid)
  - [Overview](#overview)
  - [Protecting participant data](#protecting-participant-data)
    - [MCEC's standpoint on data privacy and confidentiality](#mcecs-standpoint-on-data-privacy-and-confidentiality)
    - [De-identification vs Anonymization](#de-identification-vs-anonymization)
    - [What is anonymized data?](#what-is-anonymized-data)
  - [Identifiers](#identifiers)
    - [The Safe Harbor method](#the-safe-harbor-method)
    - [FERPA protected information](#ferpa-protected-information)
  - [MCEC Codes/Keys](#mcec-codeskeys)
    - [Re-identification keys](#re-identification-keys)
    - [MCEC contact keys](#mcec-contact-keys)
    - [Anonymization keys](#anonymization-keys)
    - [References](#references)
  - [Methods of de-identification](#methods-of-de-identification)
    - [Redaction](#redaction)
    - [Suppression](#suppression)
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

A) Hosts the code used to automatically aid the de-identification of MCEC data and its documentation.
B) Contains the documentation for the MCEC de-identification manual (manual check).
C) Contains the documentation for the workflows that integrate the MCEC-DeID source code with the manual checks.

The source code in this repository is used to processes email text files and makes a first pass at de-identification using Safe-Harbor and FERPA-defined categories.

Whenever possible, email format changes are kept to a minimum for archival purposes, except in the case of email footers which often contain more personal information than the entire body of their email (Su & Romero Diaz, Forthcoming).

## Protecting participant data

### MCEC's standpoint on data privacy and confidentiality

The MCEC Team is committed to protecting all personal data and FERPA-protected school records, even if this means lowering the usability of the public version of the MCEC corpus. Our participants' privacy comes first.

As with most academic language corpora, the MCEC keeps two versions of the relevant language data: (A) an internal version that is only available to the research team. This version is [de-identified](#de-identification-vs-anonymization)) and only the MCEC co-directors Damian Romero and Hanyu Jia have access to the de-identification table ([see below](#re-identification-keys)). The second version of our data will be public and anonymized. We are currently engaging in data collection version which will be anonymized and published via the [Research Data Repository](https://arizona.figshare.com) of the University of Arizona (also known as ReDATA).

There are a few reasons why the MCEC project does not anonymize participant data immediately upon collection. The first one is that we wish to provide our participants with the opportunity for retracting their data from any unpublished materials. Secondly, academic research projects that collect personal data in special cases, law enforcement and other U.S. agencies may require us to disclose relevant records, for example if they are needed for an investigation. For more information, please visit the UArizona [HSPP page](https://rgw.arizona.edu/compliance/human-subjects-protection-program).

If you have any questions about the MCEC corpus making academic email text publically available, please consult our `Publishing email data.md` document.


### De-identification vs Anonymization

Email data, even if it is work/school related may contain direct or indirect personal identifiable information, which is  is not only confidential, but also protected by law. For this reason we have a four-step process to unlink this information (identifiers) from the people they identify (referents). Referents not only include interlocutors (the people that are part of an email exchange), but also people who are mentioned in an email exchange.

The de-identification -- anonymization process outlined by the MCEC is the following:

1. Only Principal Investigators (PI and co-PIs) can recruit participants for the project. Current PIs are listed in the [MCEC Team Roles document](./docs/MCEC-team-roles.md) document. PIs email instructors (professors, adjuncts, teaching assistants, etc.) with an invitation to participate in the project. In turn, instructors who consent in being part of the study contact their students with an invitation email. Students who consent then forward the MCEC Project emails between themselves and their instructors.
2. The two [co-directors]([MCEC Team Roles document](./docs/MCEC-team-roles.md)) Damian Romero and Hanyu Jia collect the emails and run the automated script contained in this repository. The automated script redacts (removes) [HIPAA](docs/HIPAA-tags.md) and [FERPA](docs/MCEC-specific-tags.md) identifiers and replace them with generic [tags](#tags). This is a first-pass towards de-identification.
3. The two [co-directors]([MCEC Team Roles document](./docs/MCEC-team-roles.md)) manually de-identify the output of the automated script to redact (remove) any direct identifiers and replace them with generic [tags](#tags). The files are re-named using [codes/keys](#mcec-codeskeys) to which only the co-directors have access. At this point, the data is considered de-identified for internal use since the non-PI team members will not have any direct knowledge about the identity of the interlocutors. This version of the dataset will then be uploaded to a secure box folder.
4. The MCEC team members will then engage in the anonymization of the data contained in the secure box folder. The objective is to further redact (remove) direct and indirect identifiers from the data. Once the data has been completely de-identified, this data is considered usable for academic research internal to the MCEC team members. The data is kept in a secure box folder and the previous version of the data is destroyed.
5. Once the data is completely de-identified, Damian Romero or Hanyu Jia renames the files using [anonymization keys](#mcec-codeskeys). At this point the data is considered anonymized and ready for making it openly available. However, the MCEC directors have put an extra filter in place to ensure that the quality of the anonymization is as high as possible before making it public.
6. Before making the data publicly available, the anonymized version of data must sit for at least 3 months in a secure box folder to which only the project directors have access. The data then is run through a second script that uses machine learning algorithms to catch any anonymization issues. Finally, the output of that program is manually checked and any necessary changes are made by members of the MCEC team. At this point the data is considered safe and ready to be published  as part of the Multilingual College Email Corpus through the [University of Arizona Research Data Repository (ReDATA)]([https:](https://data.library.arizona.edu/redata)).

#### What is de-identified data?

The U.S. Department of Education defines [de-identified data](https://studentprivacy.ed.gov/glossary#de-identified-data) as:

```
[...] records that have a re-identification code and have enough personally identifiable information removed or obscured so that the remaining information does not identify an individual and there is no reasonable basis to believe that the information can be used to identify an individual. The re-identification code may allow the recipient to match information received from the same source.

For more information, see the [SLDS Technical Brief: Basic Concepts and Definitions for Privacy and Confidentiality in Student Education Records](https://nces.ed.gov/pubs2011/2011601.pdf).
```

### What is anonymized data?

"Anonymization takes the data one step beyond de-identification. That is, anonymized data are data that have been de-identified, and they do not include a re-identification code. In an anonymized data file, the student case numbers in the data records cannot be linked back to the original student record system. Returning to the examples discussed above, anonymized data would not be useful to staff using data to monitor the progress and performance of individual students. However, if a professor at a university reads the research report from the analysis of academic gains of students in the afterschool enrichment program and decides that he or she would like to have a class of graduate students apply different analytic procedures to see if the results can be replicated, an anonymized file could be produced from the de-identified file used by the researchers to serve this purpose. To do this, the re-identification code must be removed and the file should be reviewed to ensure that additional statistical disclosure techniques do not need to be applied. The documentation for the anonymized data file should identify any disclosure limitation techniques that were applied and their implications for the analysis." ([Seastrom, 2010, p. 6](https://nces.ed.gov/pubsearch/pubsinfo.asp?pubid=2011601))

## Identifiers

We base our de-identification methodology on two main resources: the Health Insurance Portability and Accountability Act (HIPAA), and the Family Educational Rights and Privacy Act (FERPA). We use these two resources because they are well-known academic standards on data privacy. While both HIIPAA and FERPA define what data counts as identifiable information, HIPAA provides a clear de-identification method known as "Safe Harbor". Additionally, FERPA regulates students' data, which is a big part of the MCEC project's records.

### The Safe Harbor method

The Safe Harbor method outlines a set of identifiers to be stripped from any publicly available information. These identifiers are linked with "the individual or of relatives, employers, or household members of the individual" ([U.S. Department of Health & Human Services](https://www.hhs.gov/hipaa/for-professionals/privacy/special-topics/de-identification/index.html#safeharborguidance), 2021/01/31). We have expanded these identifiers to include data specific to our needs. For instance, the Safe Harbor "A" identifier category (Names) has been expanded [here](docs/HIPAA-tags.md) to include hypocorisms, which are relatively frequent in academic emails. See coding manual [examples](insert-link).

### FERPA protected information

Like HIPAA, FERPA protects two types of information: education records, and personally identifiable information.

"Education records are those records that are directly related to a student and are maintained by an educational agency or institution or by a party acting for the agency or institution. For more information, see the Family Educational Rights and Privacy Act regulations, 34 CFR §99.3." ([U.S. Department of Education. (2021, February 2). *Glossary*. Student Privacy.](https://studentprivacy.ed.gov/glossary#educational-records))

"Personally identifiable information (PII) includes information that can be used to distinguish or trace an individual’s identity either directly or indirectly through linkages with other information" [U.S. Department of Education. (2021, February 2). *Glossary*. Personally Identifiable Information (PII)](https://studentprivacy.ed.gov/glossary#header-for-P)

## MCEC Codes/Keys

In the MCEC project we use the word 'keys' rather than 'codes' to refer to any descriptors used to label research data records for file naming, contacting participants, etc. There are three types of keys used by the MCEC team. Ranked by its level of confidentiality (1 being the most confidential), these are:

1. Re-identification keys
2. MCEC contact keys
3. Anonymization keys

### Re-identification keys

"A re-identification code enables an authorized researcher to return to the source of de-identified data and match the de-identified data to the source records.
For more information, see the SLDS Technical Brief: Basic Concepts and Definitions for Privacy and Confidentiality in Student Education Records." https://studentprivacy.ed.gov/glossary#re-identification-code

Re-identification keys are the most important keys for confidentiality purposes. Only the co-directors of the MCEC project, Damian Romero and Hanyu Jia, have access to re-identification table that matches the re-identification keys to participant's data. Limiting access to the re-identification table makes it so that the re-identification keys cannot be used by MCEC Team members or any other person to identify a student or personally identifiable information about a student. Damian Romero is the only researcher with the knowledge of the method used to produce and assign these keys.  ([Seastrom, 2010, p. 6](https://nces.ed.gov/pubsearch/pubsinfo.asp?pubid=2011601))

Following FERPA guidelines ([34 CFR § 99.31(b)(2)](https://studentprivacy.ed.gov/node/548/#0.1_se34.1.99_131)), our re-identification codes are not based on participants' personal information. We do not share how the re-identification codes are generated or assigned. Only MCEC co-directors Damian Romero and Hanyu Jia will use these keys to match de-identified records to the source materials for education research purposes.

Internal MCEC data files (e.g. email files) are named by Damian Romero and Hanyu Jia using these re-identification keys. This allows the other members of the MCEC Team to work on data anonymization (anonymization checks, redaction of indirect identifiers, suppression of personal information, etc.). The use of re-identification keys also offers an extra layer of protection to any inadvertent or unauthorized disclosures of personal information.

TL;DR

   - Re-identification key access: MCEC Team. However, Access to the de-identification table is restricted to MCEC co-directors.
   - Use: Internal academic research and anonymization by the MCEC Team without disclosing direct identifiers.
   - Note: Internal MCEC data files are named using re-identification keys. Using re-identification keys also offers an extra layer of confidentiality.

### MCEC contact keys

TL;DR

   - MCEC contact key access: Participants have access to their own MCEC contact key. MCEC Principal Investigators (P.I. and Co-PIs) authorized by the University of Arizona's Human Subjects Protection Program have access to the MCEC contact keys table in case they need to address participants' questions, concerns or requests such as deleting data from unpublished records.
   - Use: Only used for participants to contact the MCEC Team PIs. This is generated by the MCEC Email Generator Tool (MCEC-EmG).
   - Note: These keys are not linked to any participant data.

### Anonymization keys

TL;DR

   - Anonymization key access: Public. No de-identification table exists.
   - Use: Public version of the corpus with no re-identification (record) keys. 
   - Note: These keys are not linked to any personally identifiable information. Anonymization keys are assigned to individual email conversations irrespectively of whether or not two or more conversations involve the same interlocutors. As a result, researchers cannot use these keys to match individual records across
previously de-identified data files from the same source (e.g., to compare student emails over several years). However, we believe this is the best alternative to respect participant's privacy.

### References

[Seastrom, M. (2010). Basic concepts and definitions for privacy and confidentiality in student education records (NCES 2011–601). Washington, DC: National Center for Education Statistics, Institute of Education Sciences, US Department of Education. Gov/Pubsearch/Pubsinfo. Asp.](https://nces.ed.gov/pubsearch/pubsinfo.asp?pubid=2011601)

## Methods of de-identification

The MCEC Project uses two methods of de-identification: redaction and suppression. In our project, protected information is redacted by taking any direct or indirect identifier defined in [HIPAA](docs/HIPAA-tags.md) or [FERPA](docs/MCEC-specific-tags.md) and replacing them with a tag. On the other hand, suppression is the entire removal of a section, phrase or paragraph in which only a single tag [[suppressed-info]] is used to replace that content. For more formal definitions of these two methods, we refer the rerader to the official FERPA documentation: [Data De-identification: An Overview of Basic Terms](https://studentprivacy.ed.gov/sites/default/files/resource_document/file/data_deidentification_terms_0.pdf). The contents are reproduced below:

### Redaction

"Redaction is a general term describing the process of expunging sensitive data from the records prior
to disclosure in a way that meets established disclosure requirements applicable to the specific data
disclosure occurrence (e.g., removing or obscuring PII from published reports to meet federal, state,
and local privacy laws as well as organizational data disclosure policies). (See disclosure limitation
method for more information about specific techniques that can be used for data redaction.)" ([Data De-identification: An Overview of Basic Terms, p. 5](https://studentprivacy.ed.gov/sites/default/files/resource_document/file/data_deidentification_terms_0.pdf))

### Suppression

"Suppression is a disclosure limitation method which involves removing data (e.g., from a cell or a row
in a table) to prevent the identification of individuals in small groups or those with unique
characteristics. This method may often result in very little data being produced for small populations,
and it usually requires additional suppression of non-sensitive data to ensure adequate protection
of PII (e.g., complementary suppression of one or more non-sensitive cells in a table so that the
values of the suppressed cells may not be calculated by subtracting the reported values from the row
and column totals). Correct application of this technique generally ensures low risk of disclosure;
however, it can be difficult to perform properly because of the necessary calculations (especially for
large multi-dimensional tables). Further, if additional data are available elsewhere (e.g., total student
counts are reported), the suppressed data may be re-calculated." ([Data De-identification: An Overview of Basic Terms, pp. 5-6](https://studentprivacy.ed.gov/sites/default/files/resource_document/file/data_deidentification_terms_0.pdf))

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
