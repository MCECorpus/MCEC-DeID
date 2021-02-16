# MCEC Data Stewardship Documentation

**Table of contents**

- [MCEC Data Stewardship Documentation](#mcec-data-stewardship-documentation)
  - [Overview](#overview)
  - [Data security and privacy](#data-security-and-privacy)
  - [In what cases does FERPA allow for information disclosure?](#in-what-cases-does-ferpa-allow-for-information-disclosure)
  - [The data collection process](#the-data-collection-process)
  - [The de-identification - anonymization process](#the-de-identification---anonymization-process)
  - [Resources](#resources)
    - [Family Educational Rights and Privacy Act (FERPA)](#family-educational-rights-and-privacy-act-ferpa)
    - [Human Subjects Protection Program (HSPP)](#human-subjects-protection-program-hspp)
    - [Health Insurance Portability and Accountability Act (HIPAA)](#health-insurance-portability-and-accountability-act-hipaa)
    - [Human Subjects Protection Program (HSPP), University of Arizona](#human-subjects-protection-program-hspp-university-of-arizona)
    - [Other resources](#other-resources)

## Overview

This document defines the steps that the MCEC Team has taken to ensure the quality, integrity, accessibility, and security of the MCEC data from collection to publication. That includes the general MCEC workflow for handling data contained in the [`The de-identification - anonymization process`](#the-de-identification---anonymization-process) section below.

For information about the specifics of each process, please consult:

- The [Terms and Definitions document](Terms-and-definitions.md) for a definition of [data stewardship](Terms-and-definitions.md#data-stewardship).
- The Terms and Definitions document for specific information about our [data collection](Terms-and-definitions.md#data-collection)) and what we do to avoid [undue influence or coercion](Terms-and-definitions.md##undue-influence-or-coercion) during this process.
- The [De-identification Team Workflows document](De-identification-team-workflows.md) for the workflows specific to the de-identification process.
- The [Anonymization Team Workflows document](Anonymization-team-workflows.md) for the workflows specific to the anonymization process.
- The [Tags](Tags.md) document to learn more about the role that the MCEC Tags play in the de-identification and anonymization of MCEC data.
- The [MCEC Keys (Codes) document](MCEC-keys-codes.md) for more information about the types of de-identification and anonymization keys (codes) we use to name our files and redact our participants' names, as well as how we assign and safeguard them.

## Data security and privacy

To the best of our knowledge there are no publicly-available corpora of emails except for those released by public entities, such as the [ENRON corpus](https://en.wikipedia.org/wiki/Enron_Corpus), the [Avocado corpus](http://dla.library.upenn.edu/dla/olac/record.html?q=archive_facet:%22The%20LDC%20Corpus%20Catalog%22&id=www_ldc_upenn_edu_LDC2015T03), the [Hillary Clinton Email Corpus](https://link-springer-com.ezproxy4.library.arizona.edu/article/10.1007/s41701-018-0034-2) and the like. Given the fact that email is a form of personal communication containing unstructured data which may contain sensitive and identifiable information, it is reasonable to ask why and in what way does the MCEC Project disclose participant emails?

1. We have obtained [IRB permission](Terms-and-definitions.md#data-collection) from our institution to conduct research in the manner that is outlined in this documentation. Our current IRB status is classified as a [minimal risk research project](Terms-and-definitions.md#minimal-risk-research).
2. We have received electronically informed consent from our participants as outlined on FERPA, [Section 99.30](https://studentprivacy.ed.gov/node/548/#0.1_se34.1.99_130), paragraphs (a-d).
3. We de-identify and later anonymize records and other information/data as outlined on FERPA, [Section 99.31](https://studentprivacy.ed.gov/node/548/#0.1_se34.1.99_131), paragraph 16 b(1).
4. We have in place [data-protection workflows](#the-de-identification---anonymization-process) to redact  [`personally identifiable information`](https://studentprivacy.ed.gov/glossary#glossary-node-236) as well as  [`education records`](https://studentprivacy.ed.gov/glossary#glossary-node-218) from participants' data.
5. Finally, although email communications is a type of personal communication, the objective of our research is not to collect personal emails, but rather institutional emails. The MCEC Project aims to understand *academic* communication. From our professional teaching experience, we understand the possibility of personal topics coming up in teacher-student interactions, however we do not expect this to happen in the majority of the data to fall into the realm of "institutional (written) talk" [(Prabhakaran et al. 2018, p. 467)](https://www.mitpressjournals.org/doi/abs/10.1162/tacl_a_00031).

## In what cases does FERPA allow for information disclosure?

FERPA allows educational agencies or institutions to disclose student information on certain cases. The most relevant to the MCEC project being §99.30 (prior consent), and §99.31 (de-identified records and information).

In the MCEC Project, we have decided to take no chances regarding our participant's data confidentiality, which is why we have:

- Adopted the Safe-Harbor method as our identification process.
- Extended the list of identifiers protected by [HIPAA](HIPAA-tags.md) with those protected by [FERPA](MCEC-specific-tags.md), and excluded educational records within the email and survey data.
- Created an automatic detection algorithm of direct identifiers information to ensure consistency, and a manual-check after the automatic process to ensure accuracy.
- Created workflows manually to de-identify the data from any indirect identifiers.
- Created workflows to anonymize the data after its de-identification, including using a Machine Learning algorithm, and a last manual-check before its publication.
- Extended this process to cover all our [participants](Terms-and-definitions.md#participants)' and [referents](Terms-and-definitions.md#identifier-referents)' data and not only student data.

Additionally, the MCEC Team reserves the right to exclude any data from publication, for example if it is the case that the relevant referents cannot be satisfactorily anonymized.

You may find the relevant FERPA sections copied below:

```
# FERPA

## [Subpart D—May an Educational Agency or Institution Disclose Personally Identifiable Information From Education Records?](https://studentprivacy.ed.gov/node/548/#0.1_sp34.1.99.d)

### §99.30 Under what conditions is prior consent required to disclose information?

(a) The parent or eligible student shall provide a signed and dated written consent before an educational agency or institution discloses personally identifiable information from the student's education records, except as provided in §99.31.

(b) The written consent must:

(1) Specify the records that may be disclosed;

(2) State the purpose of the disclosure; and

(3) Identify the party or class of parties to whom the disclosure may be made.

(c) When a disclosure is made under paragraph (a) of this section:

(1) If a parent or eligible student so requests, the educational agency or institution shall provide him or her with a copy of the records disclosed; and

(2) If the parent of a student who is not an eligible student so requests, the agency or institution shall provide the student with a copy of the records disclosed.

(d) “Signed and dated written consent” under this part may include a record and signature in electronic form that—

(1) Identifies and authenticates a particular person as the source of the electronic consent; and

(2) Indicates such person's approval of the information contained in the electronic consent.

(Authority: 20 U.S.C. 1232g (b)(1) and (b)(2)(A))

[53 FR 11943, Apr. 11, 1988, as amended at 58 FR 3189, Jan. 7, 1993; 69 FR 21671, Apr. 21, 2004]

### §99.31 Under what conditions is prior consent not required to disclose information?

(b)(1) De-identified records and information. An educational agency or institution, or a party that has received education records or information from education records under this part, may release the records or information without the consent required by §99.30 after the removal of all personally identifiable information provided that the educational agency or institution or other party has made a reasonable determination that a student's identity is not personally identifiable, whether through single or multiple releases, and taking into account other reasonably available information.
```

## The data collection process

The MCEC data collection process is the following:

1. The [MCEC Team](Terms-and-definitions.md#mcec-team) scouts for potential [instructor participants](Terms-and-definitions.md#instructors) from the [approved departments](MCEC-team-roles.md#participating-uarizona-departments) using the University of Arizona's UAccess system.
2. Using the information collected by the MCEC Team, the [Principal Investigators](Terms-and-definitions.md#principal-investigators) email instructors with an invitation to participate in the project. This invitation contains a link to the Online [Informed Consent]([informed consent](https://rgw.arizona.edu/compliance/human-subjects-protection-program/HSPP-forms/consent-templates)) form as well as our sociolinguistic, language background, and sociodemographic information survey.
3. Instructors who consent in being part of the study contact their students with an invitation email. This email is provided by the Principal Investigators and  contains an Online Informed Consent form as well as the student version of the survey mentioned above.
4. Students who consent then forward the MCEC Project emails between themselves and their instructors.
5. Instructors and students are notified of the reception of the email conversations and are provided with a [MCEC contact key](MCEC-keys-codes.md#mcec-contact-key). The [participants](Terms-and-definitions.md#participants) can then use this contact key to email the PIs with requests to exclude any of their data from unpublished materials.

## The de-identification - anonymization process

The University of Arizona considers academic emails as educational records, which means that these are protected by [FERPA](Terms-and-definitions.md#family-educational-rights-and-privacy-act-ferpa). Additionally, email data, even if it is work/school related (i.e. not personal in nature), may contain direct or indirect personal identifiable information, which is not only confidential, but also protected by law. For these reasons, the MCEC Project has put in place a five-step process to unlink this information (identifiers) from the people they identify ([referents](Terms-and-definitions.md#identifier-referents)).

The de-identification - anonymization process outlined by the MCEC is the following:

1. The two [co-directors]([MCEC Team Roles document](MCEC-team-roles.md)) Damian Romero and Hanyu Jia collect the emails and run the automated script contained in this repository. The automated script redacts (removes) [HIPAA](HIPAA-tags.md) and [FERPA](MCEC-specific-tags.md) identifiers and replace them with generic [tags](#tags). This is a first-pass towards de-identification.
2. The two [co-directors]([MCEC Team Roles document](MCEC-team-roles.md)) manually de-identify the output of the automated script to redact (remove) any direct identifiers and replace them with generic [tags](Tags.md). The files are re-named using [codes/keys](MCEC-keys-codes.md) to which only the co-directors have access. At this point, the data is considered de-identified for internal use since the non-PI team members will not have any direct knowledge about the identity of the interlocutors. This version of the dataset will then be uploaded to a secure box folder.
3. The MCEC team members will then engage in the anonymization of the data contained in the secure box folder. The objective is to further redact (remove) direct and indirect identifiers from the data. Once the data has been completely de-identified, this data is considered usable for academic research internal to the MCEC team members. The data is kept in a secure box folder and the previous version of the data is destroyed.
4. Once the data is completely de-identified, Damian Romero or Hanyu Jia renames the files using [anonymization keys](MCEC-keys-codes.md#anonymization-keys). At this point the data is considered anonymized and ready for making it openly available. However, the MCEC directors have put an extra filter in place to ensure that the quality of the anonymization is as high as possible before making it public.
5. Before making the data publicly available, the anonymized version of data must sit for at least 3 months in a secure box folder to which only the project directors have access. The data then is run through a second script that uses machine learning algorithms to catch any anonymization issues. Finally, the output of that program is manually checked and any necessary changes are made by members of the MCEC team. At this point the data is considered safe and ready to be published  as part of the Multilingual College Email Corpus through the [University of Arizona Research Data Repository (ReDATA)](https://data.library.arizona.edu/redata).

## Resources

### Family Educational Rights and Privacy Act (FERPA)

- [The University of Arizona FERPA page](https://www.registrar.arizona.edu/personal-information/family-educational-rights-and-privacy-act-1974-ferpa?topic=ferpa)
- [What is FERPA?](https://studentprivacy.ed.gov/faq/what-ferpa)
- [Guidance documents](https://studentprivacy.ed.gov/guidance)
- [Data Security Checklist](https://studentprivacy.ed.gov/resources/data-security-checklist)
- [Written Agreement Checklist](https://studentprivacy.ed.gov/resources/written-agreement-checklist)
- [Checklist: Data Sharing Agreement](https://studentprivacy.ed.gov/node/418/)
- [Data Security and Management Training: Best Practice Considerations](https://studentprivacy.ed.gov/resources/data-security-and-management-training-best-practice-considerations)
- [Student Privacy 101](https://studentprivacy.ed.gov/training/student-privacy-101)
- [Data De-identification: An Overview of Basic Terms](https://studentprivacy.ed.gov/resources/data-de-identification-overview-basic-terms)
- [FERPA 101: For Colleges & Universities](https://studentprivacy.ed.gov/training/ferpa-101-colleges-universities)
- [Email and Student Privacy](https://studentprivacy.ed.gov/training/email-and-student-privacy)
- [Issue Brief: Data Governance and Stewardship](https://studentprivacy.ed.gov/node/168/)
- [Basic Concepts and Definitions for Privacy and Confidentiality in Student Education Records](https://nces.ed.gov/pubs2011/2011601.pdf)
- [Issue Brief: Data Governance and Stewardship](https://studentprivacy.ed.gov/resources/issue-brief-data-governance-and-stewardship)

### Human Subjects Protection Program (HSPP)

- [The University of Arizona Human Subjects Protection Program](https://rgw.arizona.edu/compliance/human-subjects-protection-program)
- [UArizona's HSPP Guidance for Researchers](https://rgw.arizona.edu/compliance/human-subjects-protection-program/guidance-researchers)
- [UArizona's HSPP Regulations](https://rgw.arizona.edu/compliance/human-subjects-protection-program/regulations)
- [UArizona's information for research participants](https://rgw.arizona.edu/compliance/human-subjects-protection-program/research-participants)
- [Minimal Risk Research](https://rgw.arizona.edu/sites/default/files/minimal_risk_research_v2020-08.pdf)

### Health Insurance Portability and Accountability Act (HIPAA)

- [HIPAA home page](https://www.hhs.gov/hipaa/index.html)
- [About the Health Insurance Portability and Accountability Act](https://www.cdc.gov/phlp/publications/topic/hipaa.html)
- [Safe Harbor Guidance](https://www.hhs.gov/hipaa/for-professionals/privacy/special-topics/de-identification/index.html#safeharborguidance)
- [Modes of De-identification, Mehmet Kayaalp, MD, PhD](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5977668/)

### Human Subjects Protection Program (HSPP), University of Arizona

- [Guidance for Researchers](https://rgw.arizona.edu/compliance/human-subjects-protection-program/guidance-researchers)
- [Data Security and Records Retention](https://rgw.arizona.edu/sites/default/files/data_security_and_records_retention_v2020-04.pdf)
- [Amazon MTurk](https://rgw.arizona.edu/sites/default/files/amazon_mturk_v2020-06.pdf)
- [Access to Records](https://rgw.arizona.edu/sites/default/files/access_to_records_v2020-03.pdf)
- [Informed Consent](https://rgw.arizona.edu/compliance/human-subjects-protection-program/HSPP-forms/consent-templates)
- [HSPP Getting Started](https://rgw.arizona.edu/compliance/human-subjects-protection-program/getting-started)
- [Principal Investigator Eligibility](https://rgw.arizona.edu/sites/default/files/pi_eligibility_v2020-06.pdf)
- [Principal Investigator (PI) Responsibilities](https://rgw.arizona.edu/sites/default/files/investigators_responsibility_after_irb_approval_v2020-06.pdf)
- [Principal Investigator, Project Director, Co-Principal Investigator (PI, PD, Co-PI) Eligibility](https://rgw.arizona.edu/administration/getting-started/principal-investigator-project-director-co-principal)

### Other resources

- [UArizona Research Data Repository (ReDATA)](http://arizona.figshare.com/)
- [UArizona Research Data Repository (ReDATA) About page](https://data.library.arizona.edu/redata)
- [Learner corpora around the world, UCLouvain](https://uclouvain.be/en/research-institutes/ilc/cecl/learner-corpora-around-the-world.html)
- [International Computer Archive of Modern and Medieval English (ICAME)](http://icame.uib.no/)
- [ICAME Corpus manuals](http://korpus.uib.no/icame/manuals/)
- [ENRON corpus](https://www.cs.cmu.edu/~enron/)
- [Avocado corpus](https://catalog.ldc.upenn.edu/LDC2015T03)
- [Hillary Clinton Email Corpus](https://www.kaggle.com/kaggle/hillary-clinton-emails)