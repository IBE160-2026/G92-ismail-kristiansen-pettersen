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

## Who This Serves

The MVP serves higher-education students using their own curriculum material. Lecturers and administrators are out of scope.

**Undecided:**

- Whether use beyond individual student use is intended.
- Whether students can share source material or generated resources with each other.
- The specific user outcome that defines a useful single use of the product.

## What Makes This Different

No specific differentiator is defined by the assignment beyond providing the specified study resources from uploaded curriculum material.

**Undecided:** Whether the team will define a product differentiator later.

Confirmed capabilities and MVP constraints are not a defined differentiator.

## Success Criteria

The MVP is functionally complete when a student can provide the confirmed inputs and receive every assignment-specified output type: summaries, flashcards, quiz questions and answers, key concepts, and source or page references. Providing source or page references is itself a confirmed success criterion.

**Undecided:** specific standards for output usefulness, correctness, relevance, usability, reliability, processing time, privacy, and security beyond the stated conditional login/security requirement.

## MVP Scope

In scope for the web app MVP is the confirmed input-to-output learning-support workflow for higher-education students.

Explicitly out of scope:

- Online purchasing and selling.
- Lecturer and administrator user roles.

**Undecided, not excluded:** editing or regenerating outputs; downloading or exporting outputs; saving outputs or accounts; sharing between students; combining multiple files; and processing tables and figures. The assignment specifically identifies table and figure handling as a decision point.

## Vision

**Undecided beyond the course-project MVP.** No future direction, roadmap, or future feature set has been confirmed.

## Open Decisions

- Primary study scenario and the relative priority of study outcomes such as time saved, structure, understanding, and recall.
- A more specific initial student segment or course type.
- Automatic versus student-selected generation of outputs.
- Editing, regeneration, export, persistence, accounts, sharing, and multi-file processing.
- Whether the team will define a product differentiator.
- Success standards for quality, usability, reliability, processing time, privacy, and security beyond the stated conditional login/security requirement.
- LLM choice and confidence level; summary granularity; table and figure handling; and local versus cloud processing.
