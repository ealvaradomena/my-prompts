# my-prompts

README file created with generative AI for exceptional documentation
depth. See:
https://github.com/ealvaradomena/my-prompts/tree/main/prompts/readme-builder

Canonical repository for persistent ChatGPT Project settings and
reusable task-specific prompts.

The repository separates **project-level behavior** from **task-specific
prompts**. Files in `projects/` define persistent instructions for
individual ChatGPT Projects, while files in `prompts/` define reusable
instructions that can be invoked for a particular editing,
documentation, review, or coding task.

## Repository structure

``` text
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

### `projects/`

Canonical settings for persistent ChatGPT Projects. These files define a
project's role, purpose, behavior, rules, interaction model, outputs,
and commands.

  ------------------------------------------------------------------------------------------------------
  Project                                                            Purpose
  ------------------------------------------------------------------ -----------------------------------
  [`codex-prompt-editor`](projects/codex-prompt-editor.md)           Converts rough implementation
                                                                     requests into precise,
                                                                     implementation-ready prompts for
                                                                     Codex.

  [`patchmymess`](projects/patchmymess.md)                           Produces minimal
                                                                     PatchMyMess-compatible ZIPs
                                                                     containing only added or replaced
                                                                     project files at their exact
                                                                     project-relative paths.

  [`project-settings-editor`](projects/project-settings-editor.md)   Turns rough project-settings drafts
                                                                     into lean, precise instructions
                                                                     built to guide ChatGPT across every
                                                                     chat in a project.

  [`prompt-editor`](projects/prompt-editor.md)                       Refines draft prompts into precise,
                                                                     practical instructions for language
                                                                     models.

  [`writing-modes`](projects/writing-modes.md)                       Provides mode-based editing for
                                                                     academic prose, emails, prompts,
                                                                     slides, websites, and blogs.
  ------------------------------------------------------------------------------------------------------

[`projects/bootstrap.md`](projects/bootstrap.md) is the minimal loader
intended for ChatGPT's native Project Settings field. It directs ChatGPT
to retrieve and follow a canonical project-settings file from a supplied
URL.

### `prompts/`

Reusable prompts for bounded tasks. Unlike project settings, these files
are designed to guide a particular operation rather than persistently
define an entire ChatGPT Project.

  -------------------------------------------------------------------------------------------------------------
  Prompt                                                                    Purpose
  ------------------------------------------------------------------------- -----------------------------------
  [`Pretty Python Scripts`](prompts/pretty-python-scripts.md)               Improves Python script
                                                                            documentation, formatting,
                                                                            organization, and readability while
                                                                            preserving computational behavior.

  [`pretty-r-scripts`](prompts/pretty-r-scripts.md)                         Improves R script documentation,
                                                                            formatting, organization, and
                                                                            readability while strictly
                                                                            preserving substantive behavior and
                                                                            computational logic.

  [`readme-builder`](prompts/readme-builder.md)                             Inspects a GitHub repository and
                                                                            creates or revises its README with
                                                                            accurate setup, usage, repository
                                                                            structure, inputs, outputs, and
                                                                            reproducibility documentation.

  [`review-technical-manuscript`](prompts/review-technical-manuscript.md)   Audits technical manuscripts in
                                                                            seven passes covering organization,
                                                                            repetition, clarity, factual
                                                                            accuracy, internal consistency,
                                                                            dismissive language, and
                                                                            first-person voice.
  -------------------------------------------------------------------------------------------------------------

## Using a ChatGPT Project configuration

The repository does not require a software installation or dependency
environment. Its primary artifacts are Markdown instruction files.

To configure a ChatGPT Project:

1.  Choose the canonical settings file under `projects/`.
2.  Obtain the raw GitHub URL for that file on the intended branch.
3.  Copy the contents of
    [`projects/bootstrap.md`](projects/bootstrap.md) into the ChatGPT
    Project's native Project Settings field.
4.  Replace `[PROJECT_SETTINGS_URL]` with the raw URL of the chosen
    canonical settings file.
5.  Start a new chat in that Project and send `COCOWASH!` to test
    retrieval and re-anchor the chat to the canonical settings.

For example, the bootstrap has this form:

``` text
Retrieve and follow the current project settings from:

[PROJECT_SETTINGS_URL]
```

The canonical settings remain in this repository; the native ChatGPT
Project Settings field only needs the loader.

## Project-settings contract

Canonical project-settings files follow a common top-level structure:

1.  `# Role`
2.  `# Purpose`
3.  `# Core Behavior`
4.  `# Rules`
5.  `# Interaction`
6.  `# Output`
7.  `# Commands`

The `# Commands` section begins with three universal commands:

  -----------------------------------------------------------------------
  Command                             Function
  ----------------------------------- -----------------------------------
  `MENU!`                             Provides a concise orientation to
                                      the project's purpose, accepted
                                      inputs, and principal capabilities.

  `COCOWASH!`                         Performs an identity check,
                                      retrieves the current canonical
                                      settings from GitHub, prints them,
                                      and re-anchors the chat to them.

  `MACUMBA!`                          Performs the project's principal
                                      finalization action using decisions
                                      or work already established in the
                                      chat.
  -----------------------------------------------------------------------

Project-specific settings may define additional behavior, modes, or
selectors.

## `COCOWASH!` and canonical settings

`COCOWASH!` is designed to reduce drift between the settings stored in
this repository and the behavior of an active ChatGPT Project.

When invoked, the project:

1.  returns the identity defined under `# Role`, converting only the
    opening `You are ...` to `I am ...`;
2.  identifies the latest commit affecting the specified canonical
    settings file on the specified branch;
3.  retrieves that file at the exact commit SHA rather than relying on a
    cached, indexed, remembered, or previously retrieved copy;
4.  treats that commit-specific file as authoritative;
5.  prints the complete settings while preserving their Markdown
    structure; and
6.  silently re-anchors subsequent behavior to those settings.

This mechanism does not override higher-priority ChatGPT or system
instructions.

## Naming convention

Each canonical project uses one lowercase kebab-case identifier
consistently across:

-   the filename stem;
-   the YAML `title`;
-   the project name in `# Role`;
-   references to the project in `MENU!`; and
-   the first-person identity returned by `COCOWASH!`.

For example,
[`projects/project-settings-editor.md`](projects/project-settings-editor.md)
uses `project-settings-editor` as its filename stem and YAML title, and
its role begins with `You are project-settings-editor, ...`.

Reusable prompts may use their own title conventions; their front matter
is authoritative.

## Using a reusable prompt

Open the desired file under `prompts/` and provide its instructions to
the language model together with the material to be processed.

Each prompt defines its own scope and safeguards. For example:

-   `pretty-python-scripts` and `pretty-r-scripts` emphasize readability
    and documentation while protecting computational behavior;
-   `readme-builder` requires repository inspection before README
    creation or revision and prohibits invented repository facts;
-   `review-technical-manuscript` uses seven separate review passes
    rather than a single undifferentiated review.

Read the selected prompt before use because its task-specific rules take
precedence over assumptions suggested by its filename alone.

## Editing and extending the repository

When adding or revising a project configuration:

-   preserve the common project-settings contract;
-   keep the project identifier consistent throughout the file;
-   keep project commands ending in `!`;
-   distinguish commands from modes, labels, categories, or selectors;
-   keep the canonical settings in `projects/` and use `bootstrap.md`
    only as the loader.

When adding or revising a reusable prompt:

-   place it under `prompts/`;
-   give it clear front matter describing its purpose;
-   define its scope, constraints, and expected output explicitly;
-   update this README so the prompt inventory remains consistent with
    the repository.

## Reproducibility and versioning

These instructions are version-controlled Markdown files. For workflows
that depend on a particular prompt or project configuration, record the
Git commit SHA or otherwise preserve the exact file version used.

This is especially important for `COCOWASH!`-enabled projects: the
command intentionally resolves the current canonical settings, so
behavior can change when the corresponding project file changes on the
selected branch.

## License

No license file is included in the current repository. Public
availability on GitHub should not be interpreted as granting a
particular reuse license.
