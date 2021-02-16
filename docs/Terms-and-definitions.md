# Terms and definitions

**Table of contents**

- [Terms and definitions](#terms-and-definitions)
  - [Data](#data)
    - [Anonymized data](#anonymized-data)
    - [Data collection](#data-collection)
    - [Data governance](#data-governance)
    - [Data stewardship](#data-stewardship)
    - [De-identified data](#de-identified-data)
    - [Methods of data de-identification](#methods-of-data-de-identification)
    - [Modes of data de-identification](#modes-of-data-de-identification)
  - [Human Subjects Protection Program (HSPP) and Institutional Review Boards (IRBs)](#human-subjects-protection-program-hspp-and-institutional-review-boards-irbs)
    - [Minimal risk research](#minimal-risk-research)
  - [Identifiers](#identifiers)
    - [Direct identifiers](#direct-identifiers)
    - [Indirect identifier](#indirect-identifier)
    - [Personally identifiable information (PII)](#personally-identifiable-information-pii)
    - [Personally identifiable information for education records](#personally-identifiable-information-for-education-records)
    - [Protected health information (PHI)](#protected-health-information-phi)
    - [Identifier referents](#identifier-referents)
  - [Information Privacy Acts (HIPAA vs FERPA)](#information-privacy-acts-hipaa-vs-ferpa)
    - [Family Educational Rights and Privacy Act (FERPA)](#family-educational-rights-and-privacy-act-ferpa)
    - [FERPA protected information](#ferpa-protected-information)
    - [FERPA vs. HIPAA Infographic](#ferpa-vs-hipaa-infographic)
    - [Health Insurance Portability and Accountability Act (HIPAA)](#health-insurance-portability-and-accountability-act-hipaa)
  - [Multilingual College Email Corpus (MCEC)](#multilingual-college-email-corpus-mcec)
    - [MCEC DeID](#mcec-deid)
    - [MCEC Project](#mcec-project)
    - [MCEC Team](#mcec-team)
    - [Principal investigators](#principal-investigators)
  - [Participants](#participants)
    - [Instructors](#instructors)
    - [MCEC participant data](#mcec-participant-data)
    - [Students](#students)
  - [Privacy and confidentiality](#privacy-and-confidentiality)
    - [Confidentiality](#confidentiality)
    - [Privacy](#privacy)
  - [Records](#records)
    - [Education records](#education-records)
    - [IRB records](#irb-records)
    - [Record code](#record-code)
    - [Record retention](#record-retention)
    - [Who grants access to records?](#who-grants-access-to-records)
  - [Research Data Repository (ReDATA)](#research-data-repository-redata)
- [Tags](#tags)

-------------------------

## Data

Also referred in this documentation as MCEC research data or MCEC data. Any participant records held by the MCEC ranging from email responses to survey responses.

### Anonymized data

"Anonymization takes the data one step beyond de-identification. That is, anonymized data are data that have been de-identified, and they do not include a re-identification code. In an anonymized data file, the student case numbers in the data records cannot be linked back to the original student record system. Returning to the examples discussed above, anonymized data would not be useful to staff using data to monitor the progress and performance of individual students. However, if a professor at a university reads the research report from the analysis of academic gains of students in the afterschool enrichment program and decides that he or she would like to have a class of graduate students apply different analytic procedures to see if the results can be replicated, an anonymized file could be produced from the de-identified file used by the researchers to serve this purpose. To do this, the re-identification code must be removed and the file should be reviewed to ensure that additional statistical disclosure techniques do not need to be applied. The documentation for the anonymized data file should identify any disclosure limitation techniques that were applied and their implications for the analysis." ([Seastrom, 2010, p. 6](https://nces.ed.gov/pubsearch/pubsinfo.asp?pubid=2011601))

### Data collection

The MCEC Team collects data under the following IRB protocol information:

```
Date: April 28, 2020
Principal Investigator: Damian Yukio Romero Diaz
Protocol Number: 2004533142
Protocol Title: Collection and Analysis of Authentic College Emails
```

Because academic [emails are considered as educational records](https://www.registrar.arizona.edu/personal-information/family-educational-rights-and-privacy-act-1974-ferpa?topic=ferpa):

"Written permission from the student is required to access non-directory information. In limited circumstances, the IRB may waive the requirement to obtain written permission from the student found here. To obtain a waiver to access FERPA information, the investigator must include protocol-specific justification for why access to the FERPA information is needed without written approval from the student. This request must be submitted to the IRB for review and approval."[Access to Records, HSPP, 2021/01/07](https://rgw.arizona.edu/sites/default/files/access_to_records_v2020-03.pdf)

The MCEC requests participants for their [informed consent](https://rgw.arizona.edu/compliance/human-subjects-protection-program/HSPP-forms/consent-templates) before collecting any student or instructors data.

For more information about what is required from researchers to collect human data, please refer to the Human Subjects Protection Program site at https://rgw.arizona.edu/compliance/human-subjects-protection-program/getting-started.

#### Undue influence or coercion

Some of our PIs currently attend, or have worked as Graduate Teaching Assistants in some of the departments where data is being collected. This means that there are some ethical concerns regarding the influence that a MCEC Team member may have during the recruitment process. This is true for courses where the recruiting research members are a part of (such has a graduate class where recruitment may happen) or when the recruiting researcher is the instructor of a class (TA, grader, or main instructor).

For these cases, the MCEC assigns the recruitment task to a PI that is not part of the class in question. The Human Subjects Protection Guidelines guidance on this matter is reproduced below:

"Student artifacts and other educational records cannot be accessed until after final grades are posted if any project personnel also has access to student grades. In addition, these project personnel cannot be involved in recruitment, consenting, or identifiable data collection or analysis of his/her students as to avoid the potential for undue influence or coercion. In this instance, a third party not affiliated with the study would need to be responsible for recruiting and consenting students as well as collecting identifiable data, including educational records, and hold those items until final grades are posted. This person will need to be the point of contact for the student to request withdraw from the study, if they wish to do so prior to posting of final grades. However, if the project personnel/instructor wishes to analyze data in real time, the third party can de-identify the data and share it with the project personnel/instructor."[Access to Records, HSPP, 2021/01/07](https://rgw.arizona.edu/sites/default/files/access_to_records_v2020-03.pdf)

### Data governance

"Data governance can be defined as an organizational approach to data and information management that is formalized as a set of policies and procedures that encompass the full life cycle of data, from acquisition to use to disposal. The key steps to creating a robust data governance program include

- specifying organizational decision making authority;
- specifying data standards and policies and procedures for guiding various data management processes,
including data security and privacy protection, data quality control, and data dissemination activities;
- implementing these policies and procedures; and
- monitoring for compliance with the established standards and policies and procedures.

A data governance program includes
- protection of sensitive data;
- vulnerability assessment and risk management;
- enforcement of legal, regulatory, contractual, and architectural compliance requirements;
- identification of stakeholders, such as parents and administrators, their roles and responsibilities; and
- access management." ([Data	Governance and Stewardship, Privacy Technical Assistance Center, 2021-02-09](https://studentprivacy.ed.gov/sites/default/files/resource_document/file/Data_Governance_and_Stewardship_0.pdf))

### Data stewardship

"Data stewardship can be defined as a comprehensive approach to data management to ensure quality,
integrity, accessibility, and security of the data.

"Data stewards are managers and administrators within an organization who are responsible for implementing
data governance policies and standards and maintaining data quality and security." ([Data	Governance and Stewardship, Privacy Technical Assistance Center, 2021-02-09](https://studentprivacy.ed.gov/sites/default/files/resource_document/file/Data_Governance_and_Stewardship_0.pdf))

### De-identified data

The U.S. Department of Education defines [de-identified data](https://studentprivacy.ed.gov/glossary#de-identified-data) as:

```
[...] records that have a re-identification code and have enough personally identifiable information removed or obscured so that the remaining information does not identify an individual and there is no reasonable basis to believe that the information can be used to identify an individual. The re-identification code may allow the recipient to match information received from the same source.

For more information, see the [SLDS Technical Brief: Basic Concepts and Definitions for Privacy and Confidentiality in Student Education Records](https://nces.ed.gov/pubs2011/2011601.pdf).
```

#### Re-identification code

"A re-identification code enables an authorized researcher to return to the source of de-identified data and match the de-identified data to the source records.

For more information, see the SLDS Technical Brief: Basic Concepts and Definitions for Privacy and Confidentiality in Student Education Records." [Glossary, Protecting Student Privacy, 2021/02/07](https://studentprivacy.ed.gov/glossary#glossary-node-239)

To learn more about the codes (keys) used by re-data, please refer to the [MCEC Keys (codes) document](MCEC-keys-codes.md).

### Methods of data de-identification

"It is important to note that [PII](#personally-identifiable-information-pii) may include not only direct identifiers, such as names, student IDs or social security numbers, but also any other sensitive and non-sensitive information that, alone or combined with other information that is linked or linkable to a specific individual, would allow identification. Therefore, simple removal of direct identifiers from the data to be released DOES NOT constitute adequate de-identification. Properly performed de-identification involves removing or obscuring all identifiable information until all data that can lead to individual identification have been expunged or masked." [Data De-identification: An Overview of Basic Terms, Privacy Technical Assistance Center, 20210-02-09](https://studentprivacy.ed.gov/sites/default/files/resource_document/file/data_deidentification_terms_0.pdf)

The MCEC Project uses two methods of de-identification: redaction and suppression. In our project, protected information is redacted by taking any direct or indirect identifier defined in [HIPAA](docs/HIPAA-tags.md) or [FERPA](docs/MCEC-specific-tags.md) and replacing them with a tag. On the other hand, suppression is the entire removal of a section, phrase or paragraph in which only a single tag [[suppressed-info]] is used to replace that content. For more formal definitions of these two methods, we refer the reader to the official FERPA documentation: [Data De-identification: An Overview of Basic Terms](https://studentprivacy.ed.gov/sites/default/files/resource_document/file/data_deidentification_terms_0.pdf).

#### Redaction of data

"Redaction is a general term describing the process of expunging sensitive data from the records prior to disclosure in a way that meets established disclosure requirements applicable to the specific data disclosure occurrence (e.g., removing or obscuring PII from published reports to meet federal, state, and local privacy laws as well as organizational data disclosure policies). (See disclosure limitation method for more information about specific techniques that can be used for data redaction.)" ([Data De-identification: An Overview of Basic Terms, p. 5](https://studentprivacy.ed.gov/sites/default/files/resource_document/file/data_deidentification_terms_0.pdf))

#### Suppression of data

"Suppression is a disclosure limitation method which involves removing data (e.g., from a cell or a row in a table) to prevent the identification of individuals in small groups or those with unique characteristics." (https://studentprivacy.ed.gov/sites/default/files/resource_document/file/data_deidentification_terms_0.pdf))

#### Safe Harbor Method

"According to the Privacy Rule of the Health Insurance Portability and Accountability Act (HIPAA), the de-identification process can be accomplished using two separate pathways: Safe Harbor method and Expert Determination approach [...] The Safe Harbor method requires all 18 personal identifiers to be eliminated." [Modes of De-identification](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5977668/)

The Safe Harbor method outlines a set of identifiers to be stripped (redacted or suppressed) from any publicly available information. These identifiers are linked with "the individual or of relatives, employers, or household members of the individual" ([U.S. Department of Health & Human Services](https://www.hhs.gov/hipaa/for-professionals/privacy/special-topics/de-identification/index.html#safeharborguidance), 2021/01/31). We have expanded these identifiers to include data specific to our needs. For instance, the Safe Harbor "A" identifier category (Names) has been expanded [here](docs/HIPAA-tags.md) to include hypocorisms, which are relatively frequent in academic emails.

### Modes of data de-identification

According to [(Kayaalp, 2017)](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5977668/), there are eight different modes of medical data de-identification:

```
A.	Repository-wide batch de-identification
B.	On-demand cohort-specific de-identification
C.	On-demand de-identification of query results
D.	De-identification with patient and provider identifiers
E.	Scientist involved de-identification
F.	Patient involved de-identification
G.	Physician involved de-identification
H.	Online de-identification by honest brokers
```

Although the MCEC Project does not collect medical records, we use this categorization to our own research. Thus, the mode of de-identification used by the MCEC is the Repository-wide batch de-identification mode, which is defined as follows:

"When institutions obtain a de-identification system, some may immediately create a de-identified version of their entire repository, so that researchers with proper credentials can quickly access what they need in a de-identified format." [(Kayaalp, 2017)](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5977668/)

## Human Subjects Protection Program (HSPP) and Institutional Review Boards (IRBs)

"The Human Subjects Protection Program (HSPP), as the administrative and regulatory support program to the Institutional Review Boards (IRBs), works in collaboration with the research community to maintain an ethical and compliant research program. The IRBs are the independent review committee charged with the protection of human research subjects. An IRB must review all research and related activities involving human subjects conducted at the University of Arizona or by in which the University is a responsible participant. The University of Arizona HSPP has been accredited by the Association for Accreditation of Human Research Protection Programs (AAHRPP) since 2005, strong evidence of our commitment to the protection of human research subjects."[Human Subjects Protection Program, HSPP, 2021/02/07](https://rgw.arizona.edu/compliance/human-subjects-protection-program)

### Minimal risk research

"Projects approved under this guidance are reviewed according to the University’s Flexible Guidance for review of projects that are not federally funded or supported, or FDA regulated. Human research that is not federally funded or supported, or FDA regulated, and does not significantly affect the health and welfare of participants can be deemed minimal risk. Determination of a project’s review level requires a determination by a designated IRB member. Investigators cannot make determinations whether Human Research projects meet the regulatory criteria" [Minimal Risk Research](https://rgw.arizona.edu/sites/default/files/minimal_risk_research_v2020-08.pdf).

To learn more about minimal risk research, please consult the link inside UArizona's [Guidance for Researchers page](https://rgw.arizona.edu/compliance/human-subjects-protection-program/guidance-researchers) where you will find the most up-to-date information.

## Identifiers

Identifiers are any type of information that links participant data to other participants and, following the HIPAA [Safe Harbor method](#safe-harbor-method), "relatives, employers, or household members of the individual" ([U.S. Department of Health & Human Services](https://www.hhs.gov/hipaa/for-professionals/privacy/special-topics/de-identification/index.html#safeharborguidance), 2021-01-31) as well as FERPA "parent or other family members". For the lack of a better term, the MCEC Project uses '[referents](#referents)' to talk about any of the people that an identifier can be linked to.

### Direct identifiers

"Direct identifiers include information that relates specifically to an individual such as the individual’s residence, including for example, name, address, Social Security Number or other identifying number or code, telephone number, e-mail address, or biometric record. See also Indirect Identifier.

For more information, see the [SLDS Technical Brief: Basic Concepts and Definitions for Privacy and Confidentiality in Student Education Records](http://nces.ed.gov/pubsearch/pubsinfo.asp?pubid=2011601)."[Glossary, Protecting Student Privacy, 2021/02/07](https://studentprivacy.ed.gov/glossary#header-for-D)

### Indirect identifier

"Indirect identifiers include information that can be combined with other information to identify specific individuals, including, for example, a combination of gender, birth date, geographic indicator and other descriptors. Other examples of indirect identifiers include place of birth, race, religion, weight, activities, employment information, medical information, education information, and financial information. See also Direct Identifier.

For more information, see the [SLDS Technical Brief: Basic Concepts and Definitions for Privacy and Confidentiality in Student Education Records](http://nces.ed.gov/pubsearch/pubsinfo.asp?pubid=2011601)."[Glossary, Protecting Student Privacy, 2021/02/07](https://studentprivacy.ed.gov/glossary#header-for-I)

### Personally identifiable information (PII)

"Personally identifiable information (PII) includes information that can be used to distinguish or trace an individual’s identity either directly or indirectly through linkages with other information.

Additional information on PII is available in the [Family Educational Rights and Privacy Act Regulations, 34 CFR §99.3](http://www2.ed.gov/policy/gen/guid/fpco/pdf/ferparegs.pdf), and in the PTAC publication [Checklist: Data Governance](https://studentprivacy.ed.gov/node/167/)" [Glossary, Protecting Student Privacy, 2021/02/07](https://studentprivacy.ed.gov/glossary#header-for-I)

### Personally identifiable information for education records

"Personally identifiable information for education records is a FERPA term referring to identifiable information that is maintained in education records and includes direct identifiers, such as a student’s name or identification number, indirect identifiers, such as a student’s date of birth, or other information which can be used to distinguish or trace an individual’s identity either directly or indirectly through linkages with other information.

See [Family Educational Rights and Privacy Act Regulations, 34 CFR §99.3](http://www2.ed.gov/policy/gen/guid/fpco/pdf/ferparegs.pdf), for a complete definition of PII specific to education records and for examples of other data elements that are defined to constitute PII. Additional information is available in the PTAC publication [Protecting Student Privacy While Using Online Educational Services](https://studentprivacy.ed.gov/node/161/)." [Glossary, Protecting Student Privacy, 2021/02/07](https://studentprivacy.ed.gov/glossary#header-for-I)

### Protected health information (PHI)

Although the MCEC Project does not deal with information on patients or health plan members (PHI, see below), the HIPAA safe harbor method of de-identification is a clear guidance on how to protect participant data and it is the model that the Directors of the MCEC Project has decided to use and augment for protecting participant data.

"Under HIPAA, protected health information is considered to be individually identifiable information relating to the past, present, or future health status of an individual that is created, collected, or transmitted, or maintained by a HIPAA-covered entity in relation to the provision of healthcare, payment for healthcare services, or use in healthcare operations (PHI healthcare business uses).

Health information such as diagnoses, treatment information, medical test results, and prescription information are considered protected health information under HIPAA, as are national identification numbers and demographic information such as birth dates, gender, ethnicity, and contact and emergency contact information. PHI relates to physical records, while ePHI is any PHI that is created, stored, transmitted, or received electronically.

PHI only relates to information on patients or health plan members. It does not include information contained in educational and employment records, that includes health information maintained by a HIPAA covered entity in its capacity as an employer.

PHI is only considered PHI when an individual could be identified from the information. If all identifiers are stripped from health data, it ceases to be protected health information and the HIPAA Privacy Rule’s restrictions on uses and disclosures no longer apply.

What is PHI?
PHI is any health information that can be tied to an individual, which under HIPAA means protected health information includes one or more of the following 18 identifiers. If these identifiers are removed the information is considered de-identified protected health information, which is not subject to the restrictions of the HIPAA Privacy Rule.

1. Names (Full or last name and initial)
2. All geographical identifiers smaller than a state, except for the initial three digits of a zip code if, according to the current publicly available data from the U.S. Bureau of the Census: the geographic unit formed by combining all zip codes with the same three initial digits contains more than 20,000 people; and the initial three digits of a zip code for all such geographic units containing 20,000 or fewer people is changed to 000
3. Dates (other than year) directly related to an individual
4. Phone Numbers
5. Fax numbers
6. Email addresses
7. Social Security numbers
8. Medical record numbers
9. Health insurance beneficiary numbers
10. Account numbers
11. Certificate/license numbers
12. Vehicle identifiers (including serial numbers and license plate numbers)
13. Device identifiers and serial numbers;
14. Web Uniform Resource Locators (URLs)
15. Internet Protocol (IP) address numbers
16. Biometric identifiers, including finger, retinal and voice prints
17. Full face photographic images and any comparable images
18. Any other unique identifying number, characteristic, or code except the unique code assigned by the investigator to code the data" [What is Considered Protected Health Information Under HIPAA?, HIPAA Journal, 2021-02-14](https://www.hipaajournal.com/what-is-considered-protected-health-information-under-hipaa/#:~:text=Under%20HIPAA%2C%20protected%20health%20information,provision%20of%20healthcare%2C%20payment%20for)

### Identifier referents

The MCEC Project uses the term "identifier referents", or the shorter "referents" as any of the people that an identifier ([as defined in this document](#identifiers)) can link to. The term "referents" includes participants, but also participants' relatives, employees, or household members. On email exchanges, "referents" not only include interlocutors (the people that are part of an email exchange), but also people who are *mentioned* in that email exchange.

## Information Privacy Acts (HIPAA vs FERPA)

The MCEC Project collects two types of data (also known as MCEC participant data):

- Email conversations in simple text format (.txt UTF8-encoded files) between instructors and students, and
- Survey data containing sociolinguistic, language background, and sociodemographic information.

While the MCEC Project does not deal with health information directly, the University of Arizona considers academic emails as educational records, which means that these are protected by [FERPA](Terms-and-definitions.md#family-educational-rights-and-privacy-act-ferpa):

"Examples of an Education Record include:
[...]
Course work including papers and exams, class schedules, as well as written, email or recorded communications that are part of the academic process
"[Family Educational Rights and Privacy Act of 1974 (FERPA), Office of the Registrar, 2021/02/07](https://www.registrar.arizona.edu/personal-information/family-educational-rights-and-privacy-act-1974-ferpa?topic=ferpa)

Additionally, email data, even if it is work/school related (i.e. not personal in nature), may contain direct or indirect personal identifiers (name, email, student/employee ID, etc.), medical data (emails messages such as "Dear Professor, I have a disability and I will need accommodation"), and student records (emails messages such as "...I am not sure why I got a C in the midterm exam.") both in structured or unstructured format. In order to protect our participant's privacy and confidentiality, we follow the guidance provided in both the Family Educational Rights and Privacy Act (FERPA) as well as the Health Insurance Portability and Accountability Act (HIPAA). We do so by:

A) Incorporating HIPAA's [Safe Harbor method](Terms-and-definitions.md#safe-harbor-method) for data de-identification. See our [HIPAA Tags](HIPAA-tags.md) document for more information.

B) Expanding the identifiers used in the Safe Harbor method to include FERPA and MCEC-specific categories.

[](https://www.hhs.gov/hipaa/for-professionals/privacy/special-topics/de-identification/index.html#standard)

### Family Educational Rights and Privacy Act (FERPA)

"The Family Educational Rights and Privacy Act (FERPA) is a federal law that affords parents the right to have access to their children’s education records, the right to seek to have the records amended, and the right to have some control over the disclosure of personally identifiable information from the education records. When a student turns 18 years old, or enters a postsecondary institution at any age, the rights under FERPA transfer from the parents to the student (“eligible student”). The FERPA statute is found at 20 U.S.C. § 1232g and the FERPA regulations are found at 34 CFR Part 99."([What is FERPA?](https://studentprivacy.ed.gov/faq/what-ferpa))

"The HIPAA Security Rule requires covered entities to protect against reasonably anticipated threats to the security of [PHI](#protected-health-information-phi).  Covered entities must implement safeguards to ensure the confidentiality, integrity, and availability of PHI, although HIPAA is not technology specific and the exact safeguards that should be implemented are left to the discretion of the covered entity.

HIPAA requires physical, technical, and administrative safeguards to be implemented. Technologies such as encryption software and firewalls are covered under technical safeguards. Physical safeguards for PHI data include keeping physical records and electronic devices containing PHI under lock and key. Administrative safeguards include access controls to limit who can view PHI information and security awareness training." [What is Considered Protected Health Information Under HIPAA?, HIPAA Journal, 2021-02-14](https://www.hipaajournal.com/what-is-considered-protected-health-information-under-hipaa/#:~:text=Under%20HIPAA%2C%20protected%20health%20information,provision%20of%20healthcare%2C%20payment%20for)

### FERPA protected information

Like HIPAA, FERPA protects two types of information: education records, and personally identifiable information.

"Education records are those records that are directly related to a student and are maintained by an educational agency or institution or by a party acting for the agency or institution. For more information, see the Family Educational Rights and Privacy Act regulations, 34 CFR §99.3." ([U.S. Department of Education. (2021, February 2). *Glossary*. Student Privacy.](https://studentprivacy.ed.gov/glossary#educational-records))

"Personally identifiable information (PII) includes information that can be used to distinguish or trace an individual’s identity either directly or indirectly through linkages with other information" [U.S. Department of Education. (2021, February 2). *Glossary*. Personally Identifiable Information (PII)](https://studentprivacy.ed.gov/glossary#header-for-P)

###  FERPA vs. HIPAA Infographic

"Health information is regulated by different federal and state laws, depending on the source of the information and the entity entrusted with the information. The Family Educational Rights and Privacy Act (FERPA) and the Health Insurance Portability and Accountability Act of 1996 (HIPAA) are two examples of federal laws that regulate privacy and the exchange of specific types of information. The work of healthcare providers, school personnel, and others interacts with FERPA and HIPAA frequently, which is why it is important to understand these laws and know when they apply."[FERPA vs. HIPAA infographic](https://www.cdc.gov/phlp/publications/topic/healthinformationprivacy.html)

### Health Insurance Portability and Accountability Act (HIPAA)

"The Health Insurance Portability and Accountability Act of 1996 (HIPAA) is a federal law that required the creation of national standards to protect sensitive patient health information from being disclosed without the patient’s consent or knowledge. The US Department of Health and Human Services (HHS) issued the HIPAA Privacy Rule to implement the requirements of HIPAA. The HIPAA Security Rule protects a subset of information covered by the Privacy Rule.

Compare HIPAA with FERPA

HIPAA Privacy Rule
The Privacy Rule standards address the use and disclosure of individuals’ health information (known as “protected health information”) by entities subject to the Privacy Rule. These individuals and organizations are called “covered entities.” The Privacy Rule also contains standards for individuals’ rights to understand and control how their health information is used. A major goal of the Privacy Rule is to ensure that individuals’ health information is properly protected while allowing the flow of health information needed to provide and promote high quality health care and to protect the public’s health and well-being. The Privacy Rule strikes a balance that permits important uses of information while protecting the privacy of people who seek care and healing."[About the Health Insurance Portability and Accountability Act](https://www.cdc.gov/phlp/publications/topic/hipaa.html)

## Multilingual College Email Corpus (MCEC)

The Multilingual College Email Corpus Project (MCEC) is an ongoing collection of student and instructor emails across several departments from the University of Arizona. It is a first-of-its-kind project given its wide scope (several disciplines and academic levels) and the sociolinguistic and language backgound information collected (L1, L2, linguistic experiences, heritage languages, and more).

### MCEC DeID

The Multilingual College Email Corpus De-Identification Tool. This term refers to the GitHub repository containing source code, guidelines, manuals, workflows, and definitions related to data governance and stewardship of the MCEC Project.

### MCEC Project

This term is used to distinguish the activities surrounding the MCEC from the corpus itself (MCEC). The MCEC Project was founded in 2019 by Damian Romero as part of his Ph.D. dissertation project. After devising the MCEC Project, Damian joined efforts with Hanyu Jia and Mohammed AlShakhori to form the [Board of Directors](MCEC-team-roles.md#dirctors) of the MCEC Project. Since then, the project has grown to host numerous graduate students from different departments.

### MCEC Team

Also called the MCEC Research Team, includes all people who have shown interest in the MCEC Project and have been approved by the directors. Members of the MCEC team include the Principal Investigators (PI, co-PIs) and non-Principal Investigators (non-PIs.). For a full list, please consult our [MCEC Team Roles document](MCEC-team-roles.md).

### Principal investigators

Principal Investigators (PI and co-PIs) are researchers who have passed the relevant [Collaborative Institutional Training Initiative (CITI) training](https://rgw.arizona.edu/compliance/human-subjects-protection-program/getting-started) for ethical research and who have been approved by the [IRB](#human-subjects-protection-program-hspp-and-institutional-review-boards-irbs) to recruit participants. Not all MCEC Team members are principal investigators.

Only Principal investigators can recruit participants for the project. 

For an updated list of PIs, please refer to our [MCEC Team Roles document](MCEC-team-roles.md#current-pis).

For more information about PIs and co-PIs eligibility and responsibilities, consult the following UArizona HSPP documentation:

- [Principal Investigator Eligibility](https://rgw.arizona.edu/sites/default/files/pi_eligibility_v2020-06.pdf)
- [Principal Investigator (PI) Responsibilities](https://rgw.arizona.edu/sites/default/files/investigators_responsibility_after_irb_approval_v2020-06.pdf)

## Participants

### Instructors

Instructors is an umbrella term for anyone in charge or partly in charge of the academic process in a class. This includes professors, adjuncts, teaching assistants, graders, etc.)

### MCEC participant data

Any data related to MCEC participants such as email exchanges and survey responses.

### Students

The MCEC project collects data from a variety of students including undergraduate, graduate, on-campus, off-campus (online), and professional students, among others.

## Privacy and confidentiality

"The terms privacy and confidentiality are often invoked in discussions about rights and responsibilities when it comes to student records; in fact, they are often used interchangeably even though they have distinct meanings. So exactly what does each of these terms mean?" [Basic Concepts and Definitions for Privacy and Confidentiality in Student Education Records, p. 3](https://nces.ed.gov/pubs2011/2011601.pdf)

### Confidentiality

"Confidentiality relates to the management of another individual’s personally identifiable information. In a 2009 National Academy of Sciences, Institute of Medicine report, confidentiality is defined as referring to the obligations of those who receive personal information about an individual to respect the individual’s privacy by safeguarding the information (Committee on Health Research and the Privacy of Health Information: The HIPAA Privacy Rule, 2009, Beyond the HIPAA Privacy Rule: Enhancing Privacy, Improving Health Through Research, pp. 17–18). " [Basic Concepts and Definitions for Privacy and Confidentiality in Student Education Records, p. 4](https://nces.ed.gov/pubs2011/2011601.pdf)

### Privacy

"The concept of privacy relates to individual autonomy and each person’s control over their own information (Report of the National Academy of Science 1993 Panel Report Private Lives and Public Policies, p. 3). This includes each person’s right to decide when and whether to share personal information, how much information to share, and the circumstances under which that information can be shared (Report of the National Academy of Science 1993 Panel Report Private Lives and Public Policies, p. 22)." [Basic Concepts and Definitions for Privacy and Confidentiality in Student Education Records, p. 3](https://nces.ed.gov/pubs2011/2011601.pdf)

## Records

### Education records

The University of Arizona considers [academic emails as educational records](https://www.registrar.arizona.edu/personal-information/family-educational-rights-and-privacy-act-1974-ferpa?topic=ferpa). This means that all student email data is protected by FERPA. FERPA's definition of educational records is the following:

"Education records are those records that are directly related to a student and are maintained by an educational agency or institution or by a party acting for the agency or institution.

For more information, see 20 U.S.C. §1232g(a)(4)(A) and the [Family Educational Rights and Privacy Act regulations, 34 CFR §99.3](Family Educational Rights and Privacy Act regulations, 34 CFR §99.3).

Additional information is available in the PTAC publication [Checklist: Data Sharing Agreement](https://studentprivacy.ed.gov/node/418/)." [Glossary, Protecting Student Privacy, 2021/02/07](https://studentprivacy.ed.gov/glossary#header-for-E)

### IRB records

"IRB records are retained for six (6) years following completion of the research, which is longer than required by the human subject rules but is consistent with requirements for HIPAA retention.

This applies to all research studies, whether or not participants were enrolled. Sponsored grants and contracts may require additional periods for record retention." 
[Data Security and Records Retention, HSPP, 2021/02/07](https://rgw.arizona.edu/sites/default/files/data_security_and_records_retention_v2020-04.pdf)

### Record code

"Record code refers to the unique descriptor that can be used to match individual-level records across de-identified data files from the same source (e.g., for the purposes of comparing performance of individual students over time).

Additional information is available in the PTAC publication Data De-identification: An Overview of Basic Terms." [Data De-identification: An Overview of Basic Terms, Privacy Technical Assistance Center, 2021-02-09](https://studentprivacy.ed.gov/sites/default/files/resource_document/file/data_deidentification_terms_0.pdf)

The MCEC Team prefers the term `record keys` to refer to `record codes`. The MCEC Project uses three different types of record keys to protect participant information. To learn more, please refer to the [MCEC Keys (codes) documentation](MCEC-keys-codes.md).


### Record retention

"Research records should be maintained for whichever of the following time periods is the longest:
a) Six (6) years after the completion of the research; or
b) If the research involves children, 6 years after the youngest child in the research reaches the agesof majority (In Arizona the age of majority is 18 years old);
c) The length of time required by law (see below for FDA regulated research); or
d) As long as the sponsor requires (for sponsored research).
If desired, the investigator may archive these records with U"
[Data Security and Records Retention, HSPP, 2021/02/07](https://rgw.arizona.edu/sites/default/files/data_security_and_records_retention_v2020-04.pdf)

### Who grants access to records?

"Access to department specific records may be granted by the individual department. Permission for use of large-scale University of Arizona student records (undergraduate, graduate, and professional) is granted by the Registrar’s Office. The request for release of information and a copy of the protocol must be submitted to the Registrar for a determination of whether the release of information is appropriate under FERPA."[Access to Records, HSPP, 2021/01/07](https://rgw.arizona.edu/sites/default/files/access_to_records_v2020-03.pdf)

## Research Data Repository (ReDATA)

"The University of Arizona Research Data Repository (ReDATA) serves as the institutional repository for non-traditional scholarly outputs resulting from research activities by University of Arizona researchers. Depositing research materials (datasets, code, images, videos, etc.) associated with published articles and/or completed grants and research projects into ReDATA helps UA researchers ensure compliance with funder and journal data sharing policies as well as University data retention policies. ReDATA is designed for materials intended for public availability. All published materials will receive a Digital Object Identifier (DOI) for citation purposes" (ReDATA About Page, Data Cooperative, 2021/02/07)[https://data.library.arizona.edu/data-management/services/research-data-repository-redata]

# Tags

In the context of the [MCEC DeID](Terms-and-definitions.md#mcec-deid) `tags` are labels used to replace direct or indirect identifiers with generic information that is both human-readable and easily indexable by a computer.