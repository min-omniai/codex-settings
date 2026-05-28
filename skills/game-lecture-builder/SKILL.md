---
name: game-lecture-builder
description: "Create practical game development teaching materials for Unity, C#, gameplay systems, UI, optimization, and client architecture. Use when asked for lectures, lesson plans, classroom explanations, practice exercises, assignments, quizzes, rubrics, beginner-friendly explanations, student feedback, or curriculum content for game client development."
---

# Game Lecture Builder

## Workflow

1. Identify the learner level, class duration, target engine/version if known, and the concrete outcome students should produce.
2. Structure the material as concept, demonstration, guided practice, independent exercise, common mistakes, and review.
3. Prefer Unity/C# examples that are small enough to teach in class and realistic enough to transfer to production code.
4. Include checks for student understanding: questions, expected observations, debugging prompts, or rubric items.
5. When the user asks for beginner material, explain in Korean by default with plain terms first, then connect to Unity execution flow and code.

## Output Patterns

For lesson plans, include:
- Topic and target learner
- Learning goals
- Time plan
- Explanation outline
- Demo steps
- Practice task
- Common mistakes
- Assignment
- Answer or grading guide

For exercises, include:
- Starting state
- Requirements
- Constraints
- Hints
- Success criteria
- Extension tasks

For feedback, avoid giving the final answer first. Use:
- What works
- What to improve
- Why it matters
- Hint
- Example only if needed

## Teaching Defaults

- Assume students know basic C# unless the user says otherwise.
- Prioritize game-client thinking: frame update flow, input, UI, scene loading, prefabs, assets, memory, and debugging.
- Keep examples readable over clever.
- Mention common Unity pitfalls such as lifecycle order, serialized references, event cleanup, null references, per-frame allocation, and prefab/scene coupling when relevant.
- For mobile-oriented lessons, include GC allocation, draw calls, texture memory, UI rebuild cost, and loading spikes.

## References

Read `references/unity-teaching-patterns.md` when building a full lecture, assignment, or student feedback template.
