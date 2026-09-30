# Learning Skills Repository Design

## Purpose

Turn this repository into a professional collection of reusable Codex skills that help people learn technical subjects through clear, structured guidance.

The first skill is **LeetCode Tutor**. Future skills may cover programming languages, frameworks, developer tools, algorithms, data structures, and other technical topics.

## Audience

- Learners who want guided explanations instead of answer-only responses
- Developers studying algorithms, data structures, or unfamiliar technologies
- Codex users who want reusable teaching behavior
- Contributors who want to add focused learning skills with consistent documentation

## Repository name

The current repository remains `learning_skills` until the owner chooses to rename it.

Recommended name: **`codex-learning-skills`**

Alternatives:

- `learning-agent-skills`
- `learncraft-skills`

Renaming the repository is outside this change.

## Structure

```text
learning_skills/
├── README.md
├── LICENSE
├── docs/
│   └── superpowers/
│       └── specs/
│           └── 2026-09-30-learning-skills-repository-design.md
└── skills/
    └── leetcode-tutor/
        ├── SKILL.md
        ├── AGENTS.md
        └── README.md
```

## File responsibilities

### Root `README.md`

Present the repository as a curated learning-skill collection. It must include:

- A polished header and short value proposition
- Lightweight status and license badges
- A catalog of available skills
- A quick-start section
- User-scoped and repository-scoped installation instructions
- Guidance for using and adding skills
- GitHub alerts for important notes and tips
- Collapsible FAQ and troubleshooting sections
- Contribution and license information

The design should use standard GitHub Markdown and small amounts of safe HTML for alignment or collapsible sections. It must remain readable in plain text.

### `skills/leetcode-tutor/SKILL.md`

Provide the Codex discovery entry point.

It must:

- Use valid YAML frontmatter with the name `leetcode-tutor`
- Describe when the skill should activate
- Tell Codex to read and follow the adjacent `AGENTS.md`
- Preserve explicit user instructions when they conflict with optional teaching preferences
- Avoid duplicating the full tutor instructions

### `skills/leetcode-tutor/AGENTS.md`

Contain the complete LeetCode tutor behavior supplied by the repository owner.

It must preserve these principles:

- Teach the idea before showing code
- Guide with problem-specific questions
- Explain naive and optimal approaches
- Use examples and dry runs where useful
- Review the learner's code before replacing it
- Prefer small corrections when possible
- Provide Python 3 solutions in LeetCode format when a full solution is requested
- Explain complexity, mistakes, and relevant follow-ups
- Use shorter direct explanations for small syntax or concept questions

### `skills/leetcode-tutor/README.md`

Explain the skill to a human reader. It must include:

- Purpose and intended audience
- Features and teaching workflow
- Installation instructions
- Quick-start prompts
- Example use cases
- File layout
- Customization guidance
- Collapsible FAQ or implementation details

## Installation model

Document two installation methods:

1. **User-scoped:** copy the `leetcode-tutor` directory to `~/.codex/skills/leetcode-tutor`.
2. **Repository-scoped:** copy it to `.codex/skills/leetcode-tutor` in a project.

The repository will not add an installer script, package manager, plugin manifest, or marketplace configuration in this initial version. Those should be added only if repeated manual installation becomes a real problem.

## Documentation style

Documentation should be:

- Professional and welcoming
- Easy to scan
- Clear to first-time users
- Modern without decorative clutter
- Consistent across the root and skill READMEs
- Accessible without relying on images or color alone

Use headings, tables, GitHub alerts, concise code blocks, and `<details>` sections where they improve comprehension.

## Validation

Before completion:

- Confirm every referenced path exists
- Confirm `SKILL.md` contains valid frontmatter
- Confirm both installation methods use the correct directory structure
- Confirm the tutor instructions match the owner's existing LeetCode tutor behavior
- Confirm Markdown links and relative paths resolve correctly
- Confirm the repository contains no unfinished placeholders

## Non-goals

This change will not:

- Rename the GitHub repository
- Add multiple speculative skills
- Add executable installation scripts
- Package the collection as a plugin
- Add external dependencies
- Change the existing license

## Acceptance criteria

The design is complete when:

1. A visitor can understand the repository's purpose from the root README.
2. A visitor can find and install the LeetCode Tutor skill without outside guidance.
3. Codex can discover the tutor through `SKILL.md`.
4. The full teaching behavior is available in `AGENTS.md`.
5. Each skill has its own human-facing README.
6. The layout provides a clear pattern for adding future learning skills.
