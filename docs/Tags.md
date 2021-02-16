# Tags

In the context of the [MCEC DeID](Terms-and-definitions.md#mcec-deid) `tags` are labels used to replace direct or indirect identifiers with generic information that is both human-readable and easily indexable by a computer.

The following documents list map MCEC identifiers to their corresponding tags:

- [HIPAA Safe Harbor tags](docs/HIPAA-tags.md)

- [MCEC-specific tags (incorporates the FERPA-specific tags)](docs/MCEC-specific-tags.md)

- [Sub-tags (both for HIPAA and MCEC-specific)](docs/Sub-tags.md)

## Types of tags

Apart from the "Tag classification" mentioned above (Safe Harbor tags, MCEC-Specific tags), tags are divided into two types: main tags and sub-tags (aka. 'embedded tags').

Main tags are always used to replace identifiable information. These are signaled by the [[double square-brackets]] surrounding them.

Subtags are used to distinguish between more than one identifier item of the same kind, for instance if there are two names, these tags will allow the reader to differentiate between both [identifier referents](Terms-and-definitions.md#identifier-referents) ([[instructor](docs/Terms-and-definitions.md#instructors)] vs [[student](docs/Terms-and-definitions.md#students)] or [student][1] vs [student][2]). These tags are embedded within other tags. There can be up to two tags embedded within a main tag, but sub-tags cannot be embedded within other sub-tags.

Sub-tags contain only one set of square brackets, as opposed to main tags, which have two.

Examples:

- Main tag:

  - `[[main-tag]]`

- Main tag with one sub-tag:

  - `[[main-tag[sub-tag1][sub-tag2]]]`

- Main tag with one sub-tag:

  - `[[main-tag[sub-tag1][sub-tag2]]]`

## Tagging style-guide:

Tags are always small-cased:

- Incorrect use of casing:
  - `[[Main-tag]]`
  - `[[Main-Tag]]`
  - `[[main-Tag]]`

Sub-tags cannot be embedded within other sub tags. In other words, there is only one level of embedding (embedding is not recurrent). 

- Incorrect use of sub-tags (main tag > sub-tag > sub-tag):
  - `[[main-tag[sub-tag1[sub-tag2]]]]`

Notice that there is no spacing between square brackets when using sub-tags.

- Incorrect spacing (any spacing inside a main tag is considered incorrect):
  - `[[main-tag [sub-tag1]   [sub-tag2]]]`
