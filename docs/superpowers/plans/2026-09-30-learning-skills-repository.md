# Learning Skills Repository Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Publish a professional, installable LeetCode Tutor skill and turn the repository README into a clear catalog for current and future learning skills.

**Architecture:** Keep each skill self-contained under `skills/<skill-name>/`. Use `SKILL.md` as the Codex discovery entry point, `AGENTS.md` as the complete teaching policy, and `README.md` as human-facing installation and usage documentation. The root README catalogs the collection and links to each skill.

**Tech Stack:** GitHub-flavored Markdown, YAML frontmatter, Codex user-scoped and repository-scoped skill directories

**Spec:** `docs/superpowers/specs/2026-09-30-learning-skills-repository-design.md`

## Global Constraints

- Keep the repository name `learning_skills`; recommend `codex-learning-skills` without renaming it.
- Add only the LeetCode Tutor skill in this change.
- Add no scripts, dependencies, plugin manifest, package manager, marketplace configuration, or speculative skill folders.
- Preserve the existing `LICENSE`.
- Keep documentation readable as plain Markdown; use GitHub alerts and `<details>` only when they improve scanning.
- Document both `~/.codex/skills/leetcode-tutor` and `.codex/skills/leetcode-tutor`.
- Every installation prompt must inspect first, copy the full directory, validate `SKILL.md`, report installed files, and ask before overwriting.

## Review Focus

- **Discovery metadata:** malformed or vague YAML frontmatter must not prevent Codex from finding `leetcode-tutor`; Task 1 validates exact required keys and values.
- **Instruction completeness:** the tutor policy must retain the owner's problem workflow, own-code review flow, and short concept-answer exception; Task 1 checks all three.
- **Installation scope:** user-scoped and repository-scoped destinations must not be mixed up; Task 2 checks both paths and prompt wording.
- **Existing installations:** the copy-ready prompts must not authorize silent replacement; Task 2 checks for an explicit confirmation-before-overwrite instruction.
- **Navigation:** every root catalog link and skill-relative link must resolve to a created file; Tasks 2 and 3 check their link targets.

---

### Task 1: Create the LeetCode Tutor runtime instructions

**Files:**
- Create: `skills/leetcode-tutor/SKILL.md`
- Create: `skills/leetcode-tutor/AGENTS.md`

**Interfaces:**
- Consumes: The approved tutor behavior in the repository owner's current `AGENTS.md` instructions and the design spec.
- Produces: A discoverable `leetcode-tutor` skill whose entry point delegates detailed teaching behavior to the adjacent `AGENTS.md`.

- [ ] **Step 1: Create `skills/leetcode-tutor/AGENTS.md`**

Preserve the owner's LeetCode Tutor Instructions, including the 13-part problem response order, the separate own-code review order, the short-concept-question exception, and the final understanding-first rule. Keep the language clear and do not add unrelated teaching policies.

- [ ] **Step 2: Create `skills/leetcode-tutor/SKILL.md`**

Start with valid YAML frontmatter:

```yaml
---
name: leetcode-tutor
description: Teach LeetCode and data-structure problems through guided reasoning, examples, code review, and clear Python solutions. Use when a learner asks for help understanding, solving, debugging, or reviewing a LeetCode-style problem.
---
```

The body must tell Codex to read the adjacent `AGENTS.md` completely, follow it for tutoring requests, honor explicit user requests for a complete answer, and avoid forcing the full problem template onto small syntax questions.

- [ ] **Step 3: Validate the runtime files**

Fetch both files from `main` and confirm:

- `SKILL.md` begins with delimiters and contains exactly one `name` and one `description` field.
- The skill name is `leetcode-tutor`.
- `SKILL.md` links to `AGENTS.md`.
- `AGENTS.md` contains `Response structure for each problem`, `When I share my own code`, and `When I ask a small concept question`.
- Neither file contains `TBD`, `TODO`, or unfinished scaffold text.

Expected: all checks pass and both GitHub paths render successfully.

- [ ] **Step 4: Commit the runtime instructions**

Commit message: `feat: add LeetCode Tutor skill instructions`

### Task 2: Add the skill's human-facing README

**Files:**
- Create: `skills/leetcode-tutor/README.md`

**Interfaces:**
- Consumes: The runtime behavior produced by Task 1 and both installation scopes from the design spec.
- Produces: A standalone guide that lets a visitor understand, install, invoke, and customize the skill.

- [ ] **Step 1: Write the skill README**

Include these sections:

1. Header and concise purpose
2. Who the skill is for
3. Highlights
4. How the teaching workflow works
5. Installation
6. Ask Codex to install it
7. Getting started
8. Example prompts
9. File structure
10. Customization
11. FAQ or implementation details in `<details>`

Use GitHub alerts for the most important note and tip. Keep examples practical and avoid claiming automatic installation without Codex file and network permissions.

- [ ] **Step 2: Add manual installation instructions**

Document:

- User-scoped destination: `~/.codex/skills/leetcode-tutor`
- Repository-scoped destination: `.codex/skills/leetcode-tutor`
- The complete folder—`SKILL.md`, `AGENTS.md`, and `README.md`—must be copied.

- [ ] **Step 3: Add two copy-ready Codex prompts**

Provide one prompt per scope. Each prompt must include:

- Source: `https://github.com/prishitakadam/learning_skills/tree/main/skills/leetcode-tutor`
- Exact destination for that scope
- Inspect-before-copying instruction
- Complete-directory instruction
- `SKILL.md` validation instruction
- Installed-files report
- Confirmation before replacing an existing installation

- [ ] **Step 4: Validate the skill README**

Fetch the file from `main` and confirm both paths, the GitHub source URL, the overwrite guard, `SKILL.md`, `AGENTS.md`, at least one GitHub alert, and at least one closed `<details>` section are present.

Expected: all checks pass, and every relative path named in the README exists.

- [ ] **Step 5: Commit the skill README**

Commit message: `docs: add LeetCode Tutor guide`

### Task 3: Replace the root README with the skill catalog

**Files:**
- Modify: `README.md`

**Interfaces:**
- Consumes: The completed LeetCode Tutor folder from Tasks 1 and 2.
- Produces: The public landing page and extension pattern for future learning skills.

- [ ] **Step 1: Write the repository landing page**

Replace the one-line README with:

1. Centered project title and concise value proposition
2. Lightweight license and skill-count badges
3. Overview and highlighted repository principles
4. Skills catalog table with LeetCode Tutor status, purpose, and relative link
5. Quick start
6. Installation scopes
7. Copy-ready Codex installation prompt
8. Repository structure
9. How to add a future skill
10. Documentation standard for every skill
11. Collapsible FAQ and troubleshooting
12. Contribution and license sections
13. A short repository-name recommendation note

Use professional, accessible wording and avoid decorative clutter.

- [ ] **Step 2: Validate navigation and installation content**

Fetch the root README and confirm:

- The catalog link resolves to `skills/leetcode-tutor/README.md`.
- The documented tree matches the files that exist.
- Both installation destinations are correct.
- The prompt contains the GitHub source, validation, reporting, and overwrite requirements.
- GitHub alerts and `<details>` tags are balanced.
- No placeholder or future skill is presented as already available.

Expected: all checks pass and the rendered README provides a complete path from discovery to first use.

- [ ] **Step 3: Commit the root README**

Commit message: `docs: build learning skills catalog`

### Task 4: Perform the final repository validation

**Files:**
- Verify: `README.md`
- Verify: `skills/leetcode-tutor/SKILL.md`
- Verify: `skills/leetcode-tutor/AGENTS.md`
- Verify: `skills/leetcode-tutor/README.md`
- Preserve: `LICENSE`

**Interfaces:**
- Consumes: All outputs from Tasks 1–3.
- Produces: Evidence that the repository satisfies every acceptance criterion in the approved spec.

- [ ] **Step 1: Fetch the final repository tree**

Confirm all planned files exist on `main` and no speculative skill folders or installer scripts were added.

- [ ] **Step 2: Run the cross-file consistency check**

Confirm:

- The skill name is always `leetcode-tutor`.
- All installation source URLs and destinations match.
- Every referenced local path exists.
- The skill README accurately summarizes `AGENTS.md`.
- The root README catalog accurately summarizes the skill README.
- The existing `LICENSE` remains present and unchanged.
- No file contains `TBD`, `TODO`, or broken placeholder text.

Expected: every check passes.

- [ ] **Step 3: Correct only discovered validation failures**

If a check fails, make the smallest targeted documentation correction and re-run Steps 1–2. Do not expand the approved scope.

- [ ] **Step 4: Record completion**

Report the changed files, validation results, repository-name recommendation, and direct links to the root and skill READMEs.
