# LeetCode Tutor

LeetCode Tutor turns Codex into a patient study partner for LeetCode and data-structure problems. It emphasizes reasoning, examples, code review, and clear Python before the final answer.

## Who this skill is for

Use this skill if you are learning problem-solving patterns, practicing for interviews, or want help understanding and debugging LeetCode-style solutions instead of only receiving code.

## Highlights

- Starts with the problem, constraints, and questions worth asking.
- Covers edge cases, a dry run, and the simple approach before the optimized one.
- Explains why an algorithm works and how to recognize its pattern.
- Reviews your code with a small correction when possible.
- Uses clear Python 3 in the standard LeetCode `class Solution` format.
- Answers small syntax questions directly without forcing a long problem template.

## How the teaching workflow works

For a full problem, the tutor first restates the task and identifies useful constraints. It then asks targeted thinking questions, discusses relevant edge cases, and develops the intuition with an example or dry run. Next, it compares a naive approach with an optimal approach, explains the topics and pattern, and only then shows a Python solution. It closes with a code walkthrough, complexity, common mistakes, and useful follow-up questions.

When you share your own code, the tutor explains your approach first, identifies what is already correct, demonstrates the exact issue on an input, and aims for the smallest helpful fix.

> [!NOTE]
> This guide helps you install the skill manually or ask Codex to install it. Codex can only copy files when it has the necessary file and network permissions; review its plan and confirm any requested access.

## Installation

Copy the complete `leetcode-tutor` folder, including `SKILL.md`, `AGENTS.md`, and this `README.md`, to one of these locations.

### User-scoped installation

Install the skill for your account:

```text
~/.codex/skills/leetcode-tutor
```

### Repository-scoped installation

Install the skill only for one repository:

```text
.codex/skills/leetcode-tutor
```

> [!TIP]
> Choose the user-scoped location when you want the same tutoring style in every project. Choose the repository-scoped location when you want the skill to travel with one project.

## Ask Codex to install it

### User-scoped prompt

```text
Install the LeetCode Tutor skill from https://github.com/prishitakadam/learning_skills/tree/main/skills/leetcode-tutor into ~/.codex/skills/leetcode-tutor. Inspect the source and my destination before copying. Copy the complete directory, including SKILL.md, AGENTS.md, and README.md. Validate that ~/.codex/skills/leetcode-tutor/SKILL.md exists after copying, then report every installed file. If an installation already exists at the destination, ask for my confirmation before replacing it.
```

### Repository-scoped prompt

```text
Install the LeetCode Tutor skill from https://github.com/prishitakadam/learning_skills/tree/main/skills/leetcode-tutor into .codex/skills/leetcode-tutor. Inspect the source and my destination before copying. Copy the complete directory, including SKILL.md, AGENTS.md, and README.md. Validate that .codex/skills/leetcode-tutor/SKILL.md exists after copying, then report every installed file. If an installation already exists at the destination, ask for my confirmation before replacing it.
```

## Getting started

After installation, ask Codex about a LeetCode problem, paste an attempt, or ask a focused programming question. Include the problem statement, constraints, and your code when you have them.

## Example prompts

- “Help me understand Two Sum. Start with questions and do not show code until after the explanation.”
- “I wrote this binary search. Review my approach and show the smallest correction if there is a bug.”
- “Why does `left <= right` matter in binary search? Use a small example.”
- “Teach me how to solve Number of Islands. Compare the naive and optimal approaches.”

## File structure

```text
leetcode-tutor/
├── SKILL.md   # Skill metadata and entry instructions
├── AGENTS.md  # Detailed tutoring guidance
└── README.md  # This human-facing guide
```

Open [`SKILL.md`](SKILL.md) for the skill entry point and [`AGENTS.md`](AGENTS.md) for the full tutoring behavior.

## Customization

Adjust `AGENTS.md` to fit your learning style. For example, you can request more hints before solutions, favor a language other than Python, or focus on a particular topic such as graphs or dynamic programming. Keep `SKILL.md` pointed at `AGENTS.md` so Codex continues to load the teaching guidance.

<details>
<summary>Implementation details and FAQ</summary>

### Why are there two files besides this README?

`SKILL.md` tells Codex when to use LeetCode Tutor and directs it to the detailed guidance. `AGENTS.md` contains the tutoring workflow: problem understanding, questions, edge cases, intuition, dry runs, naive and optimal approaches, Python code, walkthroughs, complexity, mistakes, and follow-ups.

### Does the tutor always use the complete workflow?

No. It uses the full structure for a LeetCode-style problem. For small concept questions, such as slicing or `1 // 2`, it gives a direct explanation with examples instead.

### Can I ask for a complete solution?

Yes. The tutor still explains the reasoning first, then provides the solution when you explicitly ask for it.

</details>
