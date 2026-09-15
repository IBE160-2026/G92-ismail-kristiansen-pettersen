---
title: "PRD: AI Study Buddy"
status: draft
created: 2026-09-15
updated: 2026-09-15
---

# PRD: AI Study Buddy

*Draft in progress. Requirements are being captured section by section through the Coaching workflow.*

## 0. Document Purpose

This PRD defines the confirmed course-project MVP for the student, course team, and downstream UX, architecture, and story-planning work. It is grounded in the Product Brief and official assignment supplied by Mai. Confirmed requirements are separated from explicitly **Undecided** choices; no inferred requirements are included.

## 1. Vision

AI Study Buddy is a web app prototype for the IBE160 Programming with AI course at Høgskolen i Molde (autumn 2026). It helps higher-education students process their curriculum material by creating summaries, flashcards, quiz questions and answers, key concepts, and reference pointers to sources or pages from supplied material.

The product provides concrete and useful learning support in the study situation and demonstrates how AI can be used for text processing. A vision, roadmap, or feature direction beyond this course-project MVP is **Undecided**.

## 2. Target User

AI Study Buddy serves higher-education students using their own curriculum material. Lecturers and administrators are not users in the MVP.

### 2.1 Jobs To Be Done

- Help a higher-education student process curriculum material with concrete and useful learning support.
- **Undecided:** The primary study outcome or priority. The authoritative sources do not establish whether the product should prioritize time saved, structure, understanding, recall, exam preparation, or another outcome.

### 2.2 Key User Journeys

- **UJ-1. Alex turns curriculum material into study resources.**
  - **Persona + context:** Alex is a higher-education student who needs to process curriculum material for a course.
  - **Entry state:** **Undecided.**
  - **Path:** The student provides lecture notes, slides, or other curriculum material in PDF or text format; provides a course code or subject; and supplies a desired level of detail and language or other preferences. The application processes the provided material and generates a summary, flashcards, quiz questions and answers, key concepts, and reference pointers to relevant sources or pages.
  - **Climax:** The student receives the generated study resources and uses them as learning support for processing and reviewing curriculum material.
  - **Resolution:** **Undecided.** See §5.1 and Open Question 3 for the unresolved Study-Resource lifecycle.
  - **Usefulness threshold:** **Undecided.** No criteria define when generated resources are useful or sufficiently high quality.

## 3. Glossary

- **Curriculum Material** — Lecture notes, slides, or other course material supplied by a student in PDF or text format.
- **Study Resources** — The summaries, flashcards, quiz questions and answers, key concepts, and reference pointers to sources or pages generated from Curriculum Material.
- **Reference Pointer** — A pointer to a relevant source or page in Curriculum Material.

## 4. Features

### 4.1 Curriculum-Material Processing and Study-Resource Generation

**Description:** A student provides Curriculum Material, a course code or subject, a desired level of detail, and language or other preferences. The application processes the Curriculum Material and provides the required Study Resources. This realizes UJ-1. **Undecided:** whether processing begins automatically after inputs are provided or only after the student explicitly selects what to generate.

**Notes:**
- **Undecided:** Handling of tables and figures in Curriculum Material. It is not an MVP requirement.
- **Undecided:** LLM choice and confidence-level behavior. No specific model, confidence threshold, or confidence-related user behavior is an MVP requirement.
- **Undecided:** Summary granularity. No summary length, structure, granularity choice, or set of options is an MVP requirement.
- **Undecided:** Local versus cloud processing. Neither processing location is an MVP requirement.
- **Undecided:** Whether one or multiple uploaded files can be combined into a single set of Study Resources. It is not an MVP requirement.

**Functional Requirements:**

#### FR-1: Provide Curriculum Material and Study Preferences

A higher-education student can provide Curriculum Material in PDF or text format, a course code or subject, a desired level of detail, and language or other preferences.

**Consequences (testable):**
- The application accepts Curriculum Material in PDF or text format.
- The application accepts a course code or subject, a desired level of detail, and language or other preferences with the Curriculum Material.

#### FR-2: Provide Required Study Resources

The application provides Study Resources from the provided Curriculum Material.

**Consequences (testable):**
- Study Resources include summaries.
- Study Resources include flashcards.
- Study Resources include quiz questions and answers.
- Study Resources include key concepts.
- Study Resources include Reference Pointers to relevant sources or pages.

## 5. Constraints and Guardrails

### 5.1 Security and Material Lifecycle

- **Undecided:** Whether Curriculum Material or Study Resources are stored or shared.
- Accounts, login, persistent storage, and sharing are not MVP requirements.
- If storage or sharing is later decided, login and security requirements must be defined for that behavior.

## 6. Non-Goals (Explicit)

- Online purchasing and selling.
- Lecturer and administrator user roles.

## 7. MVP Scope

### 7.1 In Scope

- The web-app workflow in FR-1 and FR-2: a higher-education student provides the confirmed inputs and receives every required Study Resource.

### 7.2 Out of Scope for MVP

- Online purchasing and selling.
- Lecturer and administrator user roles.

Other possible exclusions remain **Undecided** unless explicitly confirmed.

## 8. Success Metrics

**Primary**

- **SM-1: Functional completion** — A higher-education student can provide the confirmed inputs and receive summaries, flashcards, quiz questions and answers, key concepts, and Reference Pointers to relevant sources or pages. Validates FR-1 and FR-2.

**Undecided:** Measurable standards for usefulness, correctness, relevance, usability, reliability, processing time, privacy, and security. No thresholds or targets are defined.

## 9. Open Questions

1. **Primary study outcome and student segment:** What study outcome has priority, and is a more specific initial student segment or course type intended?
2. **Generation trigger:** Does processing begin automatically after inputs are provided, or only after the student selects what to generate?
3. **Study-Resource lifecycle:** Can students edit, regenerate, export, save, or share Curriculum Material or Study Resources, and what occurs when they leave the app?
4. **LLM and confidence level:** Which LLM, if any, and what confidence-level behavior should be used?
5. **Summary granularity:** What summary granularity, if any, should be provided?
6. **Tables and figures:** What handling, if any, should be provided for tables and figures in Curriculum Material?
7. **Processing location:** Should Curriculum Material be processed locally or in the cloud?
8. **Measurable standards:** What standards, if any, apply to usefulness, correctness, relevance, usability, reliability, processing time, privacy, and security?
9. **Long-term direction:** Is a product differentiator, vision, or roadmap beyond the course-project MVP intended?
10. **Multi-file processing:** Can one or multiple uploaded files be combined into a single set of Study Resources?

## 10. Assumptions Index

None. This PRD contains no inferred requirements or assumptions.
