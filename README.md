<div align="center">

# AI tutors

Reusable Codex skills for learning technical topics through clear, structured guidance.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
![Skills](https://img.shields.io/badge/skills-1-blue.svg)

</div>

## Overview

This repository is a small, curated collection of skills that help Codex teach technical subjects instead of only supplying answers. Each skill is self-contained, documented for people, and designed to be easy to install in either a user-wide or project-specific location.

The collection follows a few simple principles:

- Teach reasoning, not just the final result.
- Keep each skill focused on one learning outcome.
- Make installation and customization clear to first-time users.
- Use plain, accessible Markdown with no required dependencies or installer scripts.

> [!NOTE]
> This repository currently includes one published skill: LeetCode Tutor. Future skill ideas are not available until they have their own completed folder and documentation.

## Skills catalog

| Skill | Status | Purpose |
| --- | --- | --- |
| [LeetCode Tutor](skills/leetcode-tutor/README.md) | Available | Guides learners through LeetCode and data-structure problems with reasoning, examples, code review, and clear Python. |

## Quick start

1. Open the [LeetCode Tutor guide](skills/leetcode-tutor/README.md).
2. Install the complete `skills/leetcode-tutor` folder in the scope that fits your needs.
3. Ask Codex about a problem, share an attempt, or ask a focused programming question.

For example: “Help me understand Two Sum. Start with questions and do not show code until after the explanation.”

## Installation scopes

Copy the complete `leetcode-tutor` directory, including `SKILL.md`, `AGENTS.md`, and `README.md`, to one of these locations.

| Scope | Destination | Use it when |
| --- | --- | --- |
| User-scoped | `~/.codex/skills/leetcode-tutor` | You want the tutoring style available in every project. |
| Repository-scoped | `.codex/skills/leetcode-tutor` | You want the skill to apply only within one repository. |

> [!TIP]
> Read the [LeetCode Tutor guide](skills/leetcode-tutor/README.md) before installing. It includes examples, customization guidance, and the same manual installation details.

## Ask Codex to install it

Copy one of these prompts into Codex. Codex needs the appropriate network and file permissions to complete the installation.

### User-scoped prompt

```text
Install the LeetCode Tutor skill from https://github.com/prishitakadam/learning_skills/tree/main/skills/leetcode-tutor into ~/.codex/skills/leetcode-tutor. Inspect the source and my destination before copying. Copy the complete directory, including SKILL.md, AGENTS.md, and README.md. Validate that ~/.codex/skills/leetcode-tutor/SKILL.md exists after copying, then report every installed file. If an installation already exists at the destination, ask for my confirmation before replacing it.
```

### Repository-scoped prompt

```text
Install the LeetCode Tutor skill from https://github.com/prishitakadam/learning_skills/tree/main/skills/leetcode-tutor into .codex/skills/leetcode-tutor. Inspect the source and my destination before copying. Copy the complete directory, including SKILL.md, AGENTS.md, and README.md. Validate that .codex/skills/leetcode-tutor/SKILL.md exists after copying, then report every installed file. If an installation already exists at the destination, ask for my confirmation before replacing it.
```

## Repository structure

```text
learning_skills/
├── README.md
├── LICENSE
├── docs/
│   └── superpowers/
│       ├── plans/
│       │   └── 2026-09-30-learning-skills-repository.md
│       └── specs/
│           └── 2026-09-30-learning-skills-repository-design.md
└── skills/
    └── leetcode-tutor/
        ├── SKILL.md
        ├── AGENTS.md
        └── README.md
```

## Add a future skill

When adding a new learning skill, create a self-contained folder at `skills/<skill-name>/` with:

1. `SKILL.md` — discovery metadata and concise instructions for Codex.
2. `AGENTS.md` — complete behavior and teaching guidance.
3. `README.md` — a human-facing guide for purpose, installation, use, and customization.

Then add one row to the catalog only when the new skill is complete and ready to use. Do not add speculative folders, unfinished catalog entries, or installation tooling unless a real need emerges.

## Documentation standard

Every skill should explain who it helps, what it does, how to install it in both scopes, and how to use it. Installation prompts must name the GitHub source and exact destination, inspect before copying, preserve the complete directory, validate `SKILL.md`, report installed files, and ask before overwriting an existing installation. Keep documentation concise, professional, accessible, and readable as plain Markdown.

<details>
<summary>FAQ</summary>

### Does installing a skill add a plugin or dependency?

No. Skills are copied directories. This repository does not include a package manager, installer script, plugin manifest, or marketplace configuration.

### Which installation scope should I choose?

Choose `~/.codex/skills/leetcode-tutor` for a skill you want available across your work. Choose `.codex/skills/leetcode-tutor` when it should stay with one repository.

### Can I customize a skill after installing it?

Yes. Read the skill's README first. For LeetCode Tutor, you can adjust `AGENTS.md` to change teaching preferences while keeping `SKILL.md` pointed to it.

</details>

<details>
<summary>Troubleshooting</summary>

### Codex cannot install the skill

Confirm that Codex has permission to read the GitHub source and write to the chosen destination. You can also copy the complete folder manually.

### The skill is not being used

Confirm that the destination contains `SKILL.md` at `~/.codex/skills/leetcode-tutor/SKILL.md` or `.codex/skills/leetcode-tutor/SKILL.md`, depending on the scope you selected.

### I already have a folder at the destination

Review its contents and keep a backup if needed. The installation prompts instruct Codex to ask for confirmation before replacing an existing installation.

</details>

## Contributing

Contributions are welcome when they add a focused, complete learning skill and follow the documentation standard above. Keep changes small, avoid unrelated dependencies or tooling, and ensure every documented local path exists.

## License

This repository is available under the [MIT License](LICENSE).

## Repository name

The repository remains `learning_skills` for now. If it is renamed later, `codex-learning-skills` is the recommended name; `learning-agent-skills` and `learncraft-skills` are alternatives.
