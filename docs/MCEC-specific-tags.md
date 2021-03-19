# MCEC-specific tags

The tags below have been created to protect identifiers not contemplated in the Safe Harbor method, but which directly or indirectly identify participant information or that of their "relatives, employers, or household members" (also called identifier ["referents"](Terms-and-definitions.md#identifier-referents) throughout this documentation). There are two types of tags: educational record tags and personally identifiable information tags.

## Educational record tags

The U.S. Department of Education' protects students privacy via the Family Educational Rights and Privacy Act, also known as [FERPA](https://studentprivacy.ed.gov/). According to FERPA, a [record](https://studentprivacy.ed.gov/node/548/#0.1_se34.1.99_13) is: "any information recorded in any way, including, but not limited to, handwriting, print, computer media, video or audio tape, film, microfilm, and microfiche."

Educational records are defined by FERPA as:

"[...] those records that are:
(1) Directly related to a student; and
(2) Maintained by an educational agency or institution or by a party acting for the agency or institution.
[...]" ([34 CFR § 99.3.](https://studentprivacy.ed.gov/node/548/#0.1_se34.1.99_13))

Some examples of educational records can be found in the FERPA website [here](https://studentprivacy.ed.gov/faq/what-education-record) and in the University of Arizona Office of the Registrar website [here](https://www.registrar.arizona.edu/personal-information/family-educational-rights-and-privacy-act-1974-ferpa?topic=ferpa),

There are a few exceptions to what a protected educational record is. These exceptions include "[r]ecords that are kept in the sole possession of the maker", "[g]rades on peer-graded papers before they are collected and recorded by a teacher", among others. For more information, please consult the online documentation [here](https://studentprivacy.ed.gov/node/548/#0.1_se34.1.99_13).

Taking into account these definitions, the MCEC has defined the following tags:

### MCEC ID "A"

Scores/grades

|Automated y/n|Item|Tag|Notes|
|---------------|----|---|-----|
|Automated y/n|Scores (test, assignments, course, etc.)|[[academic-score]]|Notes|
|Automated y/n|Transcript information|[[transcript-info]]|Notes|

### MCEC ID "B"

Groups and affiliations

Automated y/n|Item|Tag|Notes|
|--------------|----|---|-----|
Automated y/n|Department|[[department]]|Notes|
Automated y/n|Laboratory|[[laboratory]]|Notes|
Automated y/n|Groups or associations|[[group-name]]|E.g. student clubs, associations|
Automated y/n|Academic unit|[[academic-unit]]|any units below the college/school level|

### MCEC ID "C"

Course identifiers

Automated y/n|Item|Tag|Notes|
|--------------|----|---|-----|
Automated y/n|Subject name|[[subject-name]]|Notes|
Automated y/n|Course prefix|[[course-prefix]]|INFO/SPAN/MATH, etc.|
Automated y/n|Course name|[[course-name]]|Notes|
Automated y/n|Course number|[[course-no]]|Notes|
Automated y/n|Course section|[[section-no]]|Notes|

### MCEC ID "D"

University and academic activities

Automated y/n|Item|Tag|Notes|
|--------------|----|---|-----|
Automated y/n|Test name|[[test]]|GRE, Bar exam, etc|
Automated y/n|Assignment/homework|[[assignment]]|Notes|
Automated y/n|Classwork activity|[[classwork]]|Notes|
Automated y/n|Research activity|[[research]]|Notes|
Automated y/n|University-related sports|[[sport]]|Other sports mentioned in the data would not count as academic records|
Automated y/n|University-related volunteer work|[[volunteer-work]]|Notes|

### MCEC ID "E"

Academic materials/methods

Automated y/n|Item|Tag|Notes|
|--------------|----|---|-----|
Automated y/n|Book|[[book]]|Even if abbreviated|
Automated y/n|Academic article|[[article]]|Notes|
Automated y/n|Other course materials|[[course-material]]|Syllabi, artifacts, and other non-book, non-article materials|
Automated y/n|Teaching software|[[teaching-software]]|Piazza, Canvas, BrightSpace, Blackboard, etc.|
Automated y/n|Laboratory equipment|[[laboratory-equip]]|Notes|
Automated y/n|Computer software|[[computer-software]]|Only specific software that can be used by a small number of people. Matlab or Python would not count as identifier computer-software.|
Automated y/n|Research method|[[research-method]]|Notes|

### MCEC ID "F"

Other records

|Automated y/n|Class list information|[[classlist-info]]|Notes|
|Automated y/n|Course (or any) schedule information|[[schedule-info]]|Notes|
|Automated y/n|Financial information|[[financial-info]]|Notes|
|Automated y/n|Student discipline files|[[discipline-file]]|Notes|
|Automated y/n|Work positions|[[position-name]]|Grader, assistant, director, etc.|

## Examples of an Education Record include:

- Biographical information including date and place of birth, gender, nationality, information about race and ethnicity, and identification photographs
- Grades, test scores, evaluations, courses taken, academic specialization and activities, and official communications regarding a student's status
- Course work including papers and exams, class schedules, as well as written, email or recorded communications that are part of the academic process
- Disciplinary records
- Students' financial and financial aid records
- Internship program records
- SID:  Student Identification number

## Personally identifiable information

FERPA defines certain personally identifiable information [(34 CFR § 99.3.)](https://studentprivacy.ed.gov/ferpa#0.1_se34.1.99_13), some of which overlaps with HIPAA privacy items. The table below compares HIPAA vs FERPA-defined identifiers:

|HIPAA|FERPA|Notes|
|-----|-----|-----|
|(A) Names|(a) The student's name and (b) The name of the student's parent or other family members, (e) Other indirect identifiers, such as the student's date of birth, place of birth, and mother's maiden name||
|(B) Geographic sub-divisions smaller than state|(c) The address of the student or student's family, (e) Other indirect identifiers, such as the student's date of birth, place of birth, and mother's maiden name||
|(C) All elements of dates (except year)|(e) Other indirect identifiers, such as the student's date of birth, place of birth, and mother's maiden name||
|(C)(1) All ages over 89 and all elements of dates (including year) indicative of such age|(e) Other indirect identifiers, such as the student's date of birth, place of birth, and mother's maiden name||
|(D) Telephone numbers|NaN||
|(E) Fax numbers|NaN||
|(F) Email addresses|(d) A personal identifier, such as the student's social security number, student number, or biometric record|UArizona email addresses contain student NetIDs|
|(G) Social security numbers|(d) A personal identifier, such as the student's social security number, student number, or biometric record||
|(H) Medical record numbers|(d) A personal identifier, such as the student's social security number, student number, or biometric record||
|(I) Health plan beneficiary numbers|(d) A personal identifier, such as the student's social security number, student number, or biometric record||
|(J) Account numbers|(d) A personal identifier, such as the student's social security number, student number, or biometric record||
|(K) Certificate/license numbers|(d) A personal identifier, such as the student's social security number, student number, or biometric record||
|(L) Vehicle identifiers and serial numbers, including license plate numbers|NaN||
|(M) Device identifiers and serial numbers|NaN||
|(N) Locators (URLs)|NaN||
|(O) Internet Protocol (IP) addresses|NaN||
|(P) Biometric identifiers, including finger and voice prints|(d) A personal identifier, such as the student's social security number, student number, or biometric record||
|(Q) Full-face photographs and any comparable images|NaN||
|(R) Any other unique identifying number, characteristic, or code, except as permitted by paragraph (c) of this section|(f) Other information that, alone or in combination, is linked or linkable to a specific student that would allow a reasonable person in the school community, who does not have personal knowledge of the relevant circumstances, to identify the student with reasonable certainty|see tags|
|NaN|(g) Information requested by a person who the educational agency or institution reasonably believes knows the identity of the student to whom the education record relates.|see tags|
