# Product Requirements Document: Exam Review Question Generator

## Purpose & Users

Build a simple browser-based web application for university and graduate students preparing for academic course exams. Students upload course materials and receive relevant practice questions, correct answers, short explanations, and source citations. The prototype supports multiple subject areas and reduces manual question-writing effort while helping students identify central concepts. It does not claim to predict what an instructor will test.

## Core Workflow

1. Upload and validate text-based PDFs; remove invalid files and continue with valid files.
2. Select question types, difficulty levels, question count, and output language. Optionally enter “Focus on these topics” and “Exclude these topics.”
3. Generate a practice set grounded exclusively in the uploaded materials. Display any limitations and source warnings.
4. Answer one question at a time. After submission, immediately display feedback, the correct/model answer, a short explanation, and supporting citations.
5. Show a final score and allow review of answered questions without changing submissions or scores.

## Functional Requirements

### Uploads & Session

- Accept 1–3 text-based PDFs, at most 100 pages total and 20 MB per file. Enforce these hard limits before generation.
- Reject password-protected PDFs and PDFs without usable extractable text; explain each rejection and allow removal of the affected file.
- No accounts, login, or long-term storage of uploaded materials or study history. Refreshing or closing the page discards the current practice session.
- Clearly disclose that extracted PDF text is sent to an external AI provider for generation. Provider selection remains open; there is no strict prototype budget constraint.

### Generation & Grounding

- Let users request 5–30 questions, selecting one or more question types and difficulty levels. Automatically distribute questions across their selections; exact count controls per category are unnecessary.
- Support multiple-choice (four plausible options, exactly one correct answer), true/false, and short-answer questions. Avoid trick wording. Distractors must derive from concepts in the sources.
- Difficulty: **easy** recalls definitions/basic concepts; **medium** explains or applies concepts; **hard** combines concepts or solves more complex problems. All levels must require only knowledge supported by the uploads.
- Support English, Korean, and Simplified Chinese source materials and output. Users choose output language independently of source language, including cross-language generation.
- Prioritize emphasized or repeated concepts, honoring topic focus and exclusions. Flag requested topics absent from the sources and continue with supported topics.
- Every generated answer must include at least one supporting source file name and PDF page number. Text references are sufficient for launch.
- Exclude ambiguous or contradictory material from scored questions; show separate warnings citing relevant source pages. Flag uncertainty rather than present a confident unsupported answer.
- Omit questions lacking reliable support. If fewer questions than requested are possible, show the available set—even fewer than five—and explain the shortfall. If none are possible, explain why and prompt topic adjustments or additional uploads.

### Practice & Feedback

- Allow one submission per question and display progress, such as “4 of 10.”
- Automatically mark multiple-choice and true/false responses correct or incorrect and show the score. Calculate the final score using only these question types.
- Label short-answer questions “self-check”; show a model answer and explanation after submission without automatic grading or inclusion in the score. For short-answer-only sets, show completion without a graded score.
- Review mode permits revisiting answered questions, feedback, and citations; submitted responses and scores remain fixed.

## Prototype Acceptance Criteria

- Manually review at least 100 generated questions spanning all three output languages, question types, and difficulty levels, including cross-language generation and representative course materials.
- At least 95% of reviewed questions have correct, source-supported answers. Every generated answer includes a source citation; review verifies citation relevance and accuracy.
- Typical practice sets from 1–3 PDFs totaling 20–100 pages generate within about 60 seconds.
- Validate upload limits, rejected-file recovery, absent topics, conflicting sources, insufficient material, immediate feedback, scoring exclusions, and immutable review behavior.
- A student can complete upload, configuration, practice, and review without an account. Show clear processing and failure messages, with a way to retry generation.

## Out of Scope for Launch

PowerPoint, standalone typed notes, Word documents, scanned PDFs, handwritten notes, images, exam-outline/past-exam uploads, automatic short-answer grading, accounts, persistent history, download/print exports, and clickable citations opening exact PDF pages. These may be considered later.
