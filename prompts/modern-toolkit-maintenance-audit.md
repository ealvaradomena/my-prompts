---
description: Audits the Modern Toolkit for bibliographic, pedagogical,
  structural, sequencing, and maintainability issues, pauses for
  explicit decisions, then applies only the approved changes using the
  smallest safe PatchMyMess patch.
title: modern-toolkit-maintenance-audit
---

# A Modern Toolkit for Social, Political, and Economic Research --- Maintenance Audit

I will provide a **current snapshot of *A Modern Toolkit for Social,
Political, and Economic Research* following the ZipMyMess protocol**.

Use this prompt as a single controlled maintenance workflow with two
mandatory stages:

1.  **Diagnose and consult:** audit the project, present only decisions
    that genuinely warrant my attention, and stop.
2.  **Implement:** only after I respond with decisions for the edit IDs,
    implement exactly those approved decisions using the PatchMyMess
    protocol.

Do not collapse these stages. **Never implement changes during Stage
1.** My response to the decision table is the authorization to proceed
to Stage 2.

The project should remain technically sound, bibliographically reliable,
pedagogically coherent, stylistically consistent, and maintainable over
time.

# Governing principles

Apply a **high threshold for intervention**. The default recommendation
is **KEEP**.

Do not propose changes merely because another implementation, reading,
reference, wording, or organizational scheme is also defensible.
Recommend a change only when there is a concrete reason that the current
implementation is weaker, inconsistent, incorrect, misleading,
unnecessarily complicated, or materially less effective.

Do not manufacture issues to produce a comprehensive-looking audit. At
the same time, be exacting about factual errors, hallucinated
references, broken internal logic, inconsistent conventions, and
technical debt likely to cause future problems.

Throughout both stages:

-   treat the current project snapshot as authoritative;
-   preserve the existing typography, spacing system, colors, visual
    language, page structure, course content, citation style, and Quarto
    architecture except where an approved edit explicitly requires a
    change;
-   prefer the **smallest effective intervention**;
-   reuse existing variables, CSS/SCSS tokens, includes, shortcodes,
    templates, bibliography infrastructure, and shared components rather
    than creating redundant mechanisms;
-   never invent references, authors, titles, publication details,
    chapters, episodes, DOIs, URLs, or other bibliographic information.

------------------------------------------------------------------------

# Stage 1 --- Diagnose and consult

## First inspect the project

Before making recommendations, inspect the current snapshot carefully
and determine from the actual files:

-   how the Quarto project is structured;
-   where the syllabi live;
-   how the home and References pages are generated;
-   how bibliographic data are stored and rendered;
-   what CSS, SCSS, variables, includes, templates, shortcodes, or
    shared components already exist;
-   whether the project already contains mechanisms that should be
    reused rather than duplicated.

Do not assume that any concern described below is present. Verify the
current implementation first.

If a previously raised issue has already been solved satisfactorily,
mark it as such and do not reopen it without a substantive reason.

If `references.bib`, or another file necessary for a reliable audit, is
genuinely absent from the ZipMyMess snapshot, identify that limitation
explicitly.

## Pass 1 --- Syllabus structure

Audit every syllabus systematically.

### Module descriptions

Each ordinary instructional module must use:

-   exactly one paragraph containing exactly two sentences;
-   sentence 1 beginning with **"This module..."**;
-   sentence 2 beginning with **"Students..."**;
-   no em dashes.

Evaluate every existing description for compliance.

Do not rewrite descriptions merely to introduce stylistic variation.
Preserve their substantive meaning and existing voice wherever possible.

Flag descriptions that are unclear, inaccurate, repetitive, poorly
aligned with the module title or readings, or otherwise require
substantive correction.

### Final session

Verify that each course concludes with an appropriate **wrap-up,
synthesis, or integration session**, rather than a standalone capstone
project.

Do not redesign a final session merely because another formulation is
possible. Intervene only when the existing session no longer coheres
with the course as it has evolved.

## Pass 2 --- Bibliographic verification

Conduct rigorous bibliographic verification of **every assigned
reference across all syllabi**.

Use external verification rather than model memory whenever a reference
can be checked. Prefer authoritative sources in this order when
applicable:

1.  DOI registration record;
2.  journal or publisher;
3.  book publisher;
4.  author's institutional or official page;
5.  official project or software documentation;
6.  organization responsible for the resource.

For each reference, verify as applicable:

-   author or institutional author;
-   title;
-   publication year or date;
-   journal, book, publisher, or other venue;
-   volume;
-   issue;
-   page range;
-   edition;
-   chapter or section title;
-   DOI;
-   URL;
-   named episode, chapter, or section assigned in the syllabus.

Flag any reference that:

-   does not appear to exist;
-   cannot be reliably verified;
-   appears to have been hallucinated;
-   conflates multiple works;
-   contains materially incorrect bibliographic information;
-   names a nonexistent chapter, episode, or section;
-   contains an incorrect DOI;
-   links to the wrong resource;
-   otherwise cannot be supported by authoritative evidence.

Never invent missing bibliographic information. When something cannot be
verified confidently, report it as **UNVERIFIED** rather than guessing.

### DOI policy

Do **not** assume every reference should have a DOI.

For journal articles and other works for which a DOI normally exists,
determine whether one actually exists and verify it. If a work has a
DOI, ensure that the stored DOI is correct.

Do not manufacture DOIs for books, websites, software documentation,
organizational pages, Carpentries materials, or other resources that
legitimately lack one.

Where a DOI is the preferred persistent identifier, flag reliance on an
ordinary URL when appropriate.

## Pass 3 --- Books, chapters, episodes, and web resources

Verify every subordinate reading designation, including book chapters,
sections, Carpentries episodes, documentation sections, and comparable
units.

For book readings:

-   verify that the cited chapter exists;
-   verify that its number and/or title is correct;
-   verify that the syllabus points students to the intended material;
-   ensure that the project's established book/chapter emoji convention
    is applied consistently.

For **The Carpentries**, retain its terminology of **Episode**.

For ordinary websites, documentation, tutorials, organizational
resources, and similar materials, do **not** introduce the label
**Chapter** unless the source itself genuinely organizes the material as
chapters and that terminology is useful.

Review resources from organizations or websites such as The Carpentries,
OpenAI, IBM, AlvaradoCSS.com, Quarto, software documentation, and
institutional or organizational websites, and determine whether the
established citation convention is followed consistently.

## Pass 4 --- Dates and "Accessed" conventions

Audit publication dates and access dates across web-based references.

Distinguish carefully among:

-   resources with a genuine publication date;
-   resources with a genuine last-updated date;
-   continuously maintained or undated resources;
-   resources for which an access date is useful.

Do not mechanically add `Accessed ...` to every URL.

Apply the project's established convention consistently. If no coherent
convention can be inferred, propose one as an edit rather than silently
imposing it.

For example, distinguish appropriately between:

> The Carpentries. n.d. "The Unix Shell." Accessed September 2, 2026.
> ...

and

> Alvarado-Mena, Edwin. 2026. "How to Organize Your Computer for Data
> Work." July 28, 2026. ...

Determine whether different treatment is substantively justified rather
than merely visually inconsistent.

## Pass 5 --- Pedagogical alignment of readings

After bibliographic verification, evaluate the readings **module by
module**.

For each module, consider together:

-   title;
-   description;
-   learning objectives, if present;
-   assigned readings;
-   sequence within the course;
-   difficulty level;
-   relationship among the readings.

Ask:

**Is there a strong substantive reason to change the assigned
materials?**

The default recommendation is **KEEP**.

Do not recommend alternatives merely because another good, newer, more
famous, or personally preferred reading exists.

Recommend a change only for a meaningful deficiency, such as:

-   an important conceptual or substantive gap;
-   a clear mismatch between a reading and the module;
-   unnecessary redundancy;
-   substantively obsolete material;
-   a substantially better canonical or pedagogical treatment;
-   inappropriate difficulty or scope;
-   a missing foundational treatment;
-   a reading substantially more useful in another module.

When the existing selection is strong and appropriate, recommend
**KEEP** and move on.

When recommending a change, specify:

1.  the weakness in the current selection;
2.  the alternative material;
3.  why it is materially better **for this module**;
4.  whether it should **REPLACE**, **ADD**, **REMOVE**, or **RELOCATE**
    a reading.

Do not inflate reading lists unnecessarily.

### Description-reading consistency

Check that each module description accurately represents what the
assigned materials actually teach.

When a description and its readings do not align, determine which side
should change rather than automatically changing the readings. Sometimes
the correct intervention is to narrow or revise the description;
sometimes the reading set genuinely needs correction. Explain which is
preferable and why.

## Pass 6 --- Reading sequence and arrangement

Within each module, evaluate whether the readings are arranged in a
sensible pedagogical order. Recommend rearrangement when a different
order would produce a **clearer pedagogical progression**, such as:

-   foundational → applied;
-   conceptual → technical;
-   introductory → advanced;
-   general → specialized;
-   explanation → implementation.

Do not reorder readings arbitrarily or for cosmetic consistency. When
the existing order is already sensible, recommend **KEEP**.

When reordering is warranted, preserve all references unless another
proposed edit separately calls for adding, removing, replacing, or
relocating one.

Materials marked **Advanced** or **Very advanced** must remain at the
bottom of the module's reading list. Within that bottom section, place
**Advanced** materials before **Very advanced** materials unless there
is a compelling pedagogical reason otherwise.

Preserve the project's existing advanced-material conventions and
markers.

## Pass 7 --- Duplication

Check for duplicated readings.

Within a single syllabus, a work should not normally be assigned
repeatedly without a substantive reason.

Legitimate repetition includes cases in which different modules use:

-   different chapters;
-   different sections;
-   different episodes;
-   materially different portions of the same work.

Do not flag cross-syllabus repetition merely because the same good
resource is useful in more than one course.

If a duplicate within a syllabus appears unnecessary, identify it and
recommend the best location.

## Pass 8 --- References page and `references.bib`

Audit the relationship among:

-   syllabus citations;
-   `references.bib`;
-   the rendered **References** page.

The desired relationship is:

**Every reference actually assigned in a syllabus should appear in the
bibliography/References page, and every entry presented on the
References page should correspond to a reference actually used in at
least one syllabus.**

Identify:

-   syllabus references missing from `references.bib`;
-   bibliography entries unused by any syllabus;
-   duplicate bibliography entries;
-   inconsistent citation keys;
-   cases where two keys represent the same work;
-   malformed metadata affecting rendering;
-   discrepancies between displayed references and their BibTeX source.

Do not delete apparently unused bibliography entries automatically when
there is evidence that they serve another intentional function. Flag
them and explain the situation.

## Pass 9 --- Project-wide quality and maintainability

Finally, identify project-wide issues that materially affect quality or
future maintenance, including:

-   duplicated content that should use a shared variable, shortcode,
    include, or template;
-   inconsistent terminology;
-   hard-coded values that should clearly be dynamic;
-   repeated styling that should use an existing token or shared rule;
-   broken or fragile internal links;
-   unnecessary duplication across syllabus files;
-   inconsistent treatment of common components;
-   obsolete comments or configuration that create genuine confusion;
-   accessibility or semantic HTML problems with meaningful user impact;
-   obvious rendering defects.

This is **not permission for a redesign or broad architectural
reconsideration**.

Preserve the existing typography, spacing system, colors, content
architecture, and overall visual language unless a specific problem
provides a strong reason to change them.

Prefer the smallest effective intervention.

## Stage 1 output --- Decision table

Do **not** modify any files.

Return a **decision table containing only issues or decisions that
genuinely warrant my attention**, with these columns:

  Edit ID   Area   Finding   Choices   Recommendation   Why
  --------- ------ --------- --------- ---------------- -----

Assign sequential IDs: `E01`, `E02`, `E03`, ...

For every genuine decision, present concrete alternatives as:

**A)** ...\
**B)** ...\
**C)** ...

when applicable.

Clearly mark the preferred choice, for example:

**Recommended: B**

Do not create artificial A/B choices when there is only one sensible
correction, such as fixing an objectively incorrect DOI. In those cases,
state the correction directly and mark it as recommended.

Group related problems into one edit when they should logically be
solved together. Do not create dozens of microscopic edit IDs for
instances of the same underlying convention.

Conversely, do not combine unrelated decisions merely to shorten the
table.

After the table, provide three short sections:

### Verified and healthy

Summarize areas inspected and found sound enough to leave unchanged.

### Unverified or blocked

Identify anything that could not be established confidently and explain
why.

### Proposed maintenance conventions

Record any project-wide convention that should become a durable rule for
future maintenance, particularly for:

-   bibliography;
-   DOI handling;
-   access dates;
-   book chapters and Carpentries episodes;
-   module descriptions;
-   final wrap-up sessions;
-   reading sequence and arrangement;
-   advanced and very advanced readings;
-   References-page synchronization.

Then **stop and wait for my decisions**.

I will respond with choices such as:

`E01 B, E02 A, E03 KEEP, E04 C ...`

Do not implement, patch, or modify files until I have supplied those
decisions.

------------------------------------------------------------------------

# Stage 2 --- Implement approved decisions

Begin Stage 2 only after I have responded to the Stage 1 decision table.

My decisions are authoritative. Implement **only the approved
decisions**, following the **PatchMyMess protocol**.

Do not reopen settled design, bibliographic, pedagogical, or
organizational decisions unless implementation would be technically
impossible or would demonstrably break the project.

A response of **KEEP** means make no change for that edit ID.

## Reinspect before editing

Before applying each approved edit, inspect its actual implementation in
the current project snapshot.

Do not blindly apply the Stage 1 recommendation if the project state has
changed since the audit.

If an approved issue has already been resolved in the current snapshot,
leave it alone and report that fact.

If the snapshot used for implementation is not demonstrably the same
current state that was audited, or if I provide a newer snapshot, treat
the newest supplied snapshot as authoritative and verify every approved
edit against it before patching.

Reuse existing:

-   variables;
-   CSS/SCSS tokens;
-   includes;
-   shortcodes;
-   templates;
-   bibliography infrastructure;
-   shared components;

whenever possible rather than creating redundant mechanisms.

## Scope control

Implement only the decisions I approved.

Do not rebuild, redesign, modernize, simplify, refactor, or otherwise
modify unrelated parts of the project.

Preserve the existing:

-   typography;
-   spacing system;
-   colors;
-   visual language;
-   page structure;
-   course content;
-   citation style;
-   Quarto architecture;

except where an approved edit explicitly requires a change.

Use the **smallest effective patch**.

## Bibliographic safety

Never invent:

-   references;
-   authors;
-   titles;
-   publication details;
-   chapters;
-   episodes;
-   DOIs;
-   URLs.

For factual corrections established during Stage 1, use the verified
information from the audit rather than improvising new metadata.

If implementation exposes a bibliographic uncertainty that Stage 1 did
not resolve, preserve the current entry and flag the issue rather than
guessing.

## Validation

After patching, verify as applicable that:

-   the Quarto project structure remains intact;
-   changed pages render logically;
-   internal links remain valid;
-   bibliography keys resolve;
-   syllabus citations and `references.bib` remain synchronized;
-   the References page reflects the intended bibliography;
-   module descriptions consist of exactly one paragraph containing
    exactly two sentences, with sentence 1 beginning **"This
    module..."** and sentence 2 beginning **"Students..."**;
-   final wrap-up sessions remain coherent;
-   module references follow the approved sensible pedagogical order;
-   no accidental duplicate references were introduced;
-   **Advanced** and **Very advanced** materials remain at the bottom of
    each module's reading list, with their established markers
    preserved;
-   shared styling or components were not unnecessarily duplicated;
-   no unrelated content changed.

## Stage 2 output --- PatchMyMess

Follow the **PatchMyMess protocol exactly**.

The resulting patch must contain only files that genuinely need to
change.

Include a concise change log mapping implemented changes to their edit
IDs:

  Edit ID   Files changed        Implementation
  --------- -------------------- ----------------
  E01       `_quarto.yml`, ...   ...
  E04       `courses/...qmd`     ...

Also report:

-   approved edits that were already resolved and therefore required no
    change;
-   approved edits that could not safely be implemented, with the
    reason.

Do not make additional unsolicited changes.
