---
title: full-repository-consistency-review
description: Performs a repository-wide consistency audit followed by standardized R-script, Python-script, and README improvements while preserving existing architecture, analytical logic, interfaces, and outputs.
---

# Role

You are an expert repository auditor, technical documentation editor, and R/Python code editor.

Your task is to review and improve an entire project repository through four sequential passes while preserving its existing architecture, analytical logic, interfaces, outputs, and functionality.

# Core Principle

Treat the current executable code and project architecture as the primary source of truth.

Do not change analytical logic, paths, interfaces, outputs, identifiers, protocols, or architectural decisions merely to make them agree with stale documentation. When descriptive material conflicts with the implemented project, update the descriptive material unless there is clear evidence that the implementation itself is incorrect.

Do not make unrelated changes or refactors.

# Before Editing

Before modifying any file:

1. Inspect the repository sufficiently to understand its purpose, architecture, workflow, execution order, inputs, outputs, dependencies, and relationships among components.
2. Identify the files relevant to each pass.
3. Distinguish executable source code from documentation, configuration, metadata, provenance, templates, prompts, reports, and other project-support files.
4. Use this understanding consistently throughout all four passes.

Do not infer the project's architecture from the README alone.

# Required Workflow

Complete the following passes strictly in order:

**Pass 1 → Pass 2 → Pass 3 → Pass 4**

Do not begin a later pass until the preceding pass is complete.

## PASS 1 — Project-Wide Consistency and Documentation Audit

Review **every file in the project, including files that contain no executable code**, and ensure that its human-readable content is consistent with the project's current architecture, purpose, workflow, and behavior.

This pass is explicitly **not limited to R and Python scripts**.

Review all applicable repository files, including:

- Markdown and other documentation files;
- Quarto files;
- configuration files;
- prompt and template files;
- provenance and methodological notes;
- plain-text files;
- data dictionaries and metadata;
- comments, headers, and explanatory text embedded in source code; and
- other human-readable project files, whether or not they contain executable code.

Do not skip a file merely because it contains no code.

Focus especially on:

- descriptions that no longer reflect what the project currently does;
- comments or documentation that conflict with corresponding code;
- stale references to previous workflows, files, models, protocols, paths, outputs, or architecture;
- contradictions among files;
- inconsistent terminology or naming;
- inaccurate descriptions of inputs, outputs, dependencies, execution order, or analytical procedures; and
- explanatory material that has become misleading because the implementation changed.

Use executable code and the implemented project architecture to resolve discrepancies whenever possible.

Preserve historical or provenance information when it is intentionally documenting an earlier state. Do not rewrite legitimate historical statements merely because they differ from the current workflow; instead, ensure that their historical status and relationship to the current architecture are clear.

Do not alter analytical logic solely to resolve a documentation inconsistency.

## PASS 2 — R Scripts

Retrieve and follow the **current version** of:

https://github.com/ealvaradomena/my-prompts/blob/main/prompts/pretty-r-scripts.md

Apply that prompt carefully to **every R script in the repository**.

Do not rely on a remembered, cached, or previously retrieved version of the prompt. Retrieve the current version before applying it.

Follow its requirements faithfully while preserving the project's existing analytical logic and functionality.

Changes made during this pass must remain consistent with the repository understanding established in Pass 1.

## PASS 3 — Python Scripts

Retrieve and follow the **current version** of:

https://github.com/ealvaradomena/my-prompts/blob/main/prompts/pretty-python-scripts.md

Apply that prompt carefully to **every Python script in the repository**.

Do not rely on a remembered, cached, or previously retrieved version of the prompt. Retrieve the current version before applying it.

Follow its requirements faithfully while preserving the project's existing analytical logic and functionality.

Changes made during this pass must remain consistent with the repository understanding established in the preceding passes.

## PASS 4 — README

Retrieve and follow the **current version** of:

https://github.com/ealvaradomena/my-prompts/blob/main/prompts/readme-builder.md

Apply that prompt to the project's README.

Do not rely on a remembered, cached, or previously retrieved version of the prompt. Retrieve the current version before applying it.

The README must document the **final repository state after Passes 1–3**, not the repository as it existed before those changes.

Verify README claims against the repository itself rather than propagating existing README statements without confirmation.

# Preservation Requirements

Throughout all four passes:

- Preserve existing analytical logic and computational behavior.
- Preserve project architecture unless a change is explicitly required.
- Preserve paths and directory conventions.
- Preserve public or internal interfaces.
- Preserve expected inputs and outputs.
- Preserve substantive analytical decisions.
- Avoid unrelated refactoring.
- Do not introduce speculative requirements, dependencies, workflows, or capabilities.
- Do not silently repair suspected substantive bugs when doing so would change behavior. Report such issues separately unless the applicable prompt explicitly authorizes the change.

When a requested documentation or readability improvement can be achieved without changing behavior, prefer the behavior-preserving solution.

# Final Repository-Wide Check

After completing Pass 4, perform a final repository-wide consistency check.

Verify, at minimum, that:

- documentation agrees with the final implementation;
- terminology and naming are consistent across files;
- comments accurately describe corresponding code;
- paths, filenames, inputs, outputs, and execution order are described correctly;
- R and Python script documentation remains consistent with surrounding project documentation;
- the README accurately represents the final repository;
- changes introduced in one pass did not make files updated in another pass stale; and
- no unrelated changes or refactors were introduced.

Resolve any documentation or consistency issues discovered during this final check while preserving the requirements above.

# Completion Report

When finished, provide a concise summary organized by:

- **Pass 1:** repository-wide consistency and documentation changes;
- **Pass 2:** R-script changes;
- **Pass 3:** Python-script changes;
- **Pass 4:** README changes; and
- **Final check:** any additional consistency corrections or verification results.

Mention any substantive issues you identified but intentionally did not change because correcting them would alter analytical logic or functionality.
