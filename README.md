# my-prompts

README file created with generative AI for exceptional documentation depth.  
See: https://github.com/ealvaradomena/my-prompts/tree/main/prompts/readme-builder

Canonical repository for persistent ChatGPT Project settings and reusable task-specific prompts.

The repository separates **project-level behavior** from **task-specific prompts**. Files in `projects/` define persistent instructions for individual ChatGPT Projects, while files in `prompts/` define reusable instructions for bounded editing, documentation, review, and coding tasks.

## Repository structure

```text
my-prompts/
├── projects/
│   ├── bootstrap.md
│   ├── codex-prompt-editor.md
│   ├── patchmymess.md
│   ├── project-settings-editor.md
│   ├── prompt-editor.md
│   └── writing-modes.md
├── prompts/
│   ├── pretty-python-scripts.md
│   ├── pretty-r-scripts.md
│   ├── readme-builder.md
│   └── review-technical-manuscript.md
├── .gitignore
└── README.md
```

The working directory may also contain local IDE metadata, archived copies, and generated ZipMyMess snapshots. Those are not part of the prompt inventory and are excluded by `.gitignore` where applicable.

## `projects/`: persistent ChatGPT Project settings

Canonical project-settings files define persistent behavior for a ChatGPT Project.

| Project | Purpose |
| --- | --- |
| [`codex-prompt-editor`](projects/codex-prompt-editor.md) | Converts rough implementation requests into precise, implementation-ready prompts for Codex. |
| [`patchmymess`](projects/patchmymess.md) | Produces minimal PatchMyMess-compatible ZIPs containing only added or replaced project files at their exact project-relative paths. |
| [`project-settings-editor`](projects/project-settings-editor.md) | Turns rough project-settings drafts into lean, precise instructions built to guide ChatGPT across every chat in a project. |
| [`prompt-editor`](projects/prompt-editor.md) | Refines draft prompts into precise, practical instructions for LLMs. |
| [`writing-modes`](projects/writing-modes.md) | Provides mode-based editing for academic prose, emails, prompts, slides, websites, and blogs. |

[`projects/bootstrap.md`](projects/bootstrap.md) is the minimal loader intended for ChatGPT's native Project Settings field. It points the Project to a canonical settings file hosted elsewhere, such as a raw GitHub URL.

### Project-settings contract

The canonical project-settings files use a common top-level structure:

1. `# Role`
2. `# Purpose`
3. `# Core Behavior`
4. `# Rules`
5. `# Interaction`
6. `# Output`
7. `# Commands`

Individual projects may add task-specific subsections, modes, selectors, or workflows within that structure.

The `# Commands` section uses three shared command names:

| Command | Function |
| --- | --- |
| `MENU!` | Gives a concise orientation to the project's purpose and principal capabilities. |
| `COCOWASH!` | Performs the project's identity check, retrieves the current canonical settings, prints them, and re-anchors the chat to them. |
| `MACUMBA!` | Performs the project-specific finalization or action defined by that project's settings. |

### Configuring a ChatGPT Project

No software installation or dependency environment is required. The primary artifacts are Markdown instruction files.

1. Choose the canonical settings file under `projects/`.
2. Obtain the raw GitHub URL for that file on the intended branch.
3. Copy the contents of [`projects/bootstrap.md`](projects/bootstrap.md) into the ChatGPT Project's native Project Settings field.
4. Replace `[PROJECT_SETTINGS_URL]` with the raw URL of the chosen canonical settings file.
5. Start a new chat in that Project and send `COCOWASH!` to test retrieval and re-anchor the chat to the canonical settings.

The bootstrap is intentionally minimal:

```text
Retrieve and follow the current project settings from:

[PROJECT_SETTINGS_URL]
```

### `COCOWASH!` and canonical settings

`COCOWASH!` is designed to reduce drift between the version-controlled settings in this repository and an active ChatGPT Project. In the current project-settings files, the command instructs the model to:

1. return the identity defined under `# Role`, changing only the opening `You are ...` to `I am ...`;
2. verify the latest commit SHA affecting the specified canonical settings file on the specified branch;
3. retrieve that file at the exact commit SHA instead of relying on a cached, indexed, remembered, or previously retrieved copy;
4. treat the commit-specific file as authoritative;
5. print the complete settings while preserving their Markdown structure; and
6. silently re-anchor subsequent behavior to those settings.

This repository-level convention does not override higher-priority system or product instructions.

## `prompts/`: reusable task prompts

Files under `prompts/` provide instructions for bounded tasks rather than persistent project behavior.

| Prompt | Purpose |
| --- | --- |
| [`Pretty Python Scripts`](prompts/pretty-python-scripts.md) | Improves Python script documentation, formatting, organization, and readability while preserving computational behavior. |
| [`pretty-r-scripts`](prompts/pretty-r-scripts.md) | Improves the documentation, formatting, organization, and readability of R scripts while strictly preserving substantive behavior and computational logic. |
| [`readme-builder`](prompts/readme-builder.md) | Inspects a GitHub repository and creates or revises its README with accurate setup, usage, repository structure, inputs, outputs, reproducibility documentation, and GitHub-native Markdown formatting. |
| [`review-technical-manuscript`](prompts/review-technical-manuscript.md) | Audits technical manuscripts in seven passes covering organization, repetition, clarity, factual accuracy, internal consistency, dismissive language, and first-person voice, with a response-ready issue table after each pass. |

### Using a reusable prompt

Open the desired file under `prompts/` and provide its instructions to the language model together with the material to be processed. Each prompt defines its own scope, workflow, safeguards, and output requirements; those instructions should be read directly rather than inferred from the filename alone.

Examples of the current safeguards and workflows include:

- `pretty-python-scripts` and `pretty-r-scripts` emphasize documentation and readability while protecting computational behavior;
- `readme-builder` requires repository inspection before README creation or revision, prohibits invented repository facts, and requires GitHub-native Markdown tables;
- `review-technical-manuscript` performs seven distinct review passes rather than collapsing the audit into a single undifferentiated review.

## Editing and extending the repository

When adding or revising a project configuration:

- preserve the common project-settings structure;
- keep the project identifier consistent across the filename, YAML `title`, role, and command text;
- keep project commands ending in `!`;
- distinguish commands from modes, labels, categories, and selectors;
- keep canonical settings in `projects/` and use `bootstrap.md` only as the loader.

When adding or revising a reusable prompt:

- place it under `prompts/`;
- provide clear front matter describing its purpose;
- define its scope, constraints, workflow, and expected output explicitly;
- update this README so the prompt inventory remains synchronized with the repository.

## Reproducibility and versioning

These instructions are version-controlled Markdown files. When a workflow depends on a particular prompt or project configuration, record the Git commit SHA or otherwise preserve the exact file version used.

This is especially important for `COCOWASH!`-enabled projects: the command intentionally resolves the current canonical settings, so behavior may change when the corresponding project file changes on the selected branch.

For task-specific prompts, the same principle applies when exact procedural reproducibility matters. Referencing a commit-specific prompt version avoids ambiguity about which instructions governed a particular run, review, or editing pass.

## License

No license file is present in the supplied repository snapshot. Do not assume reuse rights solely because the repository is public.
