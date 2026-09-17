---
title: "Product Brief: AI Study Buddy"
status: draft
created: 2026-09-15
updated: 2026-09-15
---

# Product Brief: AI Study Buddy

## Executive Summary

AI Study Buddy is a web app prototype for the IBE160 Programming with AI course at Høgskolen i Molde (autumn 2026). It helps higher-education students process curriculum material into useful study resources more efficiently.

The project establishes a clear, realistic product direction and requirements before detailed planning and implementation.

## The Problem

Higher-education students may need to manually process and structure lecture notes, slides, and other curriculum material before they can turn it into effective study resources. This takes time and can make working with curriculum material less useful and less efficient.

AI Study Buddy is intended to provide concrete learning support by turning supplied curriculum material into study resources. Lost time and lack of structure are relevant consequences.

**Undecided:**

- The primary study scenario. Assessment or exam preparation may be a use case, but the assignment does not define one primary scenario.
- The relative priority of lost time and lack of structure against other possible consequences, including understanding and recall.
- A more specific initial student segment or course type.

## Confirmed Project Constraints

- Inputs: uploaded lecture notes, slides, or curriculum material in PDF or text format; course code or subject; desired detail level; and language or other preferences.
- Outputs: summaries, flashcards, quiz questions and answers, key concepts, and source or page references.
- Login and security are required if user material is stored or shared.
- Online purchasing and selling are out of scope.

**Undecided technical decision points:** LLM and confidence level; summary granularity; handling of tables and figures; and local versus cloud processing.

## The Solution

AI Study Buddy is a web app that accepts the confirmed curriculum-material inputs and provides the confirmed output types that students can view as learning support.

**Undecided:**

- Whether output generation is automatic or selected by the student.
- Whether students can edit or regenerate outputs.
- Whether outputs can be downloaded or exported.
- Whether outputs are saved for later access.
- Whether one or multiple uploaded files can be combined into a single set of outputs.

## What Makes This Different

*Draft — for team review. No specific differentiator is defined by the assignment; the comparison below is a proposed starting point, not a confirmed team decision.*

| Alternative today | Why students tolerate it | Why AI Study Buddy is better |
|---|---|---|
| Manual note review and highlighting | Free, no new tool to learn, full control over the material | Automates the structuring step: turns raw uploaded material directly into summaries, flashcards, and quiz questions instead of requiring manual rework |
| General-purpose AI chatbots (e.g. ChatGPT) | Already available and flexible | Not built for a repeatable study workflow — no dedicated flashcard/quiz output format and no consistent source/page referencing; the student has to rebuild the workflow by hand every time |
| Flashcard/quiz apps (e.g. Anki, Quizlet) | Purpose-built for flashcards and quizzes, familiar habit | Requires the student to author the content first; AI Study Buddy generates that content directly from their own uploaded course material |
| Study groups / shared peer notes | Social, low cost, no tool needed | Depends on peer availability and quality, and does not scale to arbitrary course material on demand |

**Primary user, in one sentence:** A higher-education student who uploads their own lecture notes or slides and wants a structured, source-referenced set of study material (summary, flashcards, quiz questions, key concepts) without manually reorganizing it themselves.

**Honesty note:** the advantage here is a tighter, purpose-built workflow and source-grounded output (page/section references), not a defensible moat — any of the alternatives above could add similar AI features over time.

**Still undecided:** whether the team confirms this comparison, or defines a different/additional differentiator once the MVP is built and tested.

## Who This Serves

The MVP serves higher-education students using their own curriculum material. Lecturers and administrators are out of scope.

**Undecided:**

- Whether use beyond individual student use is intended.
- Whether students can share source material or generated resources with each other.
- The specific user outcome that defines a useful single use of the product.

## Success Criteria

The MVP is functionally complete when a student can provide the confirmed inputs and receive every assignment-specified output type: summaries, flashcards, quiz questions and answers, key concepts, and source or page references. Providing source or page references is itself a confirmed success criterion.

*Draft — for team review. Targets below are proposed starting points, not confirmed standards.*

| Signal | Metric / evidence | Target (proposed) | When measured |
|---|---|---|---|
| User outcome | Student produces a usable set of outputs (summary, flashcards, quiz Q&A, key concepts, references) from one uploaded file without manual rework | All confirmed output types generated per upload, with no manual restructuring needed | MVP demo / walkthrough |
| Adoption / behavior | A test student completes a full upload → output cycle unassisted | Student completes the cycle without needing help from the team | Usability check with a few target students before submission |
| Quality / trust | Generated summaries, flashcards, and quiz answers correctly cite the source page or section they were derived from | Every output includes a source/page reference; spot-checked outputs are consistent with the source material | Manual review across at least a few different uploaded documents |
| Business / mission | Prototype meets the IBE160 assignment requirements | All assignment-specified inputs and outputs work end-to-end | Before submission deadline |

**Undecided:** specific numeric standards for output usefulness, correctness, relevance, usability, reliability, processing time, privacy, and security beyond the stated conditional login/security requirement. The targets above are proposed as a starting point for the team to confirm, tighten, or replace.

## MVP Scope

In scope for the web app MVP is the confirmed input-to-output learning-support workflow for higher-education students.

Explicitly out of scope:

- Online purchasing and selling.
- Lecturer and administrator user roles.

**Undecided, not excluded:** editing or regenerating outputs; downloading or exporting outputs; saving outputs or accounts; sharing between students; combining multiple files; and processing tables and figures. The assignment specifically identifies table and figure handling as a decision point.

## Vision

*Draft — for team review. Grounded in the confirmed problem, users, and MVP value; not a confirmed team decision.*

**Now:** Prove that a student can turn one uploaded set of course material into a complete, source-referenced set of study outputs (summary, flashcards, quiz Q&A, key concepts) without manually restructuring it first.

**Next:** Expand from single-file, single-session use toward combining multiple files for one course or topic, saving output history so a student can return to material they already generated, and refining output quality based on real student feedback.

**2-3 years:** If the core workflow proves valuable, AI Study Buddy could grow into a study companion students return to across a whole course or semester — combining material from multiple lectures into cohesive study sets, tracking which concepts a student has already reviewed, and surfacing gaps before an exam. This stays grounded in the same problem (turning raw course material into structured, trustworthy study support) rather than expanding into unrelated territory such as course administration or a content marketplace — both already out of scope.

**Undecided:** whether the team adopts this direction, or defines a different vision once the MVP is built and tested.

## Open Decisions

- Primary study scenario and the relative priority of study outcomes such as time saved, structure, understanding, and recall.
- A more specific initial student segment or course type.
- Automatic versus student-selected generation of outputs.
- Editing, regeneration, export, persistence, accounts, sharing, and multi-file processing.
- Whether the team will define a product differentiator.
- Success standards for quality, usability, reliability, processing time, privacy, and security beyond the stated conditional login/security requirement.
- LLM choice and confidence level; summary granularity; table and figure handling; and local versus cloud processing.
