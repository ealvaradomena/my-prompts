# my-prompts

Canonical repository for ChatGPT Project settings and reusable prompts.

## Structure

-   `projects/` contains persistent settings for individual ChatGPT Projects.
-   `prompts/` contains reusable task-specific prompts.
-   `projects/bootstrap.md` contains the minimal loader copied into ChatGPT's native Project Settings field.

## Prompts

| Prompt title | Description |
|----|----|
| `pretty-r-scripts` | Improves the documentation, formatting, organization, and readability of R scripts while strictly preserving their substantive behavior and computational logic. |

## Projects

| Project title | Description |
|----|----|
| `patchmymess` | Produces minimal PatchMyMess-compatible ZIPs containing only added or replaced project files at their exact project-relative paths. |
| `project-settings-editor` | Turns rough project-settings drafts into lean, precise instructions built to guide ChatGPT across every chat in a project. |
| `prompt-editor` | Refines draft prompts into precise, practical instructions for LLMs. |
| `writing-modes` | Provides mode-based editing for academic prose, emails, prompts, slides, websites, and blogs. |

## COCOWASH! behavior

`COCOWASH!` is both an identity check and a re-anchoring command. When invoked, the project must:

1.  Respond with the project's `# Role` converted from `You are ...` to `I am ...`.
2.  Print the complete current project settings retrieved from the canonical GitHub file, preserving their Markdown structure.
3.  Silently re-anchor behavior to those settings before continuing.

Printing the settings is intentional. In testing, explicitly bringing the retrieved settings into the conversation improved adherence to the remote project configuration.

## Project naming convention

Every project uses one lowercase kebab-case identifier consistently across its canonical file:

-   the filename stem;
-   the YAML `title`;
-   the project name in `# Role`;
-   references to the project in `MENU!`; and
-   the first-person identity returned by `COCOWASH!`.

For example, `projects/project-settings-editor.md` uses `title: project-settings-editor`, its Role begins `You are project-settings-editor, ...`, and `COCOWASH!` begins `I am project-settings-editor, ...`.

## Project-settings contract

Every canonical project-settings file uses the same top-level structure:

1.  `# Role`
2.  `# Purpose`
3.  `# Core Behavior`
4.  `# Rules`
5.  `# Interaction`
6.  `# Output`
7.  `# Commands`

Every `# Commands` section begins with:

1.  `## MENU!`
2.  `## COCOWASH!`
3.  `## MACUMBA!`

Project commands end with `!`. Modes, labels, categories, and other selectors are not project commands and need not end with `!`. For example, writing-modes uses `POL`, `PRO`, and `Q` as mode identifiers.

## Universal project commands

### MENU!

`MENU!` is the orientation command. It should briefly explain what the current project does, what kinds of inputs it accepts, and the most important ways to use it. Project-specific modes or capabilities may be summarized here.

Use `MENU!` when you need a concise reminder of what a project can do.

### COCOWASH!

`COCOWASH!` is the identity and orientation check. It is defined only in the canonical project-settings file, not in the bootstrap.

Every project keeps its canonical identity under `# Role` as a second-person instruction beginning with `You are ...`. When `COCOWASH!` is invoked, the model converts only that opening into first person and returns the identity beginning with `I am ...`.

For example, writing-modes contains:

> You are writing-modes, a mode-based editor for academic prose and related professional writing.

Its `COCOWASH!` response is therefore:

> I am writing-modes, a mode-based editor for academic prose and related professional writing.

The response should contain only that first-person identity unless another format is explicitly requested. After responding, the model silently re-anchors itself to the complete current project settings for the remainder of the chat.

This serves two purposes. First, it provides a simple identity check tied to the canonical settings. Second, it reduces project drift by restoring the project's intended interpretation rules. For example, in writing-modes, `PRO Top 10 soccer-focused YouTubers` should be interpreted as a request to enter `PRO` prompt-editing mode, not as a request to list YouTubers directly.

`COCOWASH!` does not override higher-priority ChatGPT or system instructions. It re-establishes the behavior defined by the current project settings within those constraints.

### MACUMBA!

`MACUMBA!` is the project-finalization command. Its exact behavior is project-specific, but it should perform the principal completion action using decisions and work already established in the current chat.

Examples include producing final project settings, returning the final preferred prompt, or returning the final preferred writing revision without alternatives or commentary.

## Bootstrap workflow

Copy `projects/bootstrap.md` into a ChatGPT Project's native Project Settings field and replace `[PROJECT_SETTINGS_URL]` with the raw GitHub URL for the corresponding canonical settings file.

Then start a new chat in that Project and send `COCOWASH!` to test whether the canonical settings were retrieved and to re-anchor the chat to them.
