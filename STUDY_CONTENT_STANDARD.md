# Engineering Study Hub — Reusable Course Content Standard

## Purpose
This repository is the canonical source for bilingual, lecture-grounded engineering study pages, designed mobile-first and intended to expand to more Ain Shams Engineering subjects. The first course is CES251s Midterm 2024 Model B, under `ces251midterm/index.html`.

## Non-negotiable requirements

1. **Exams**: preserve the original question text, symbols, option wording and option order. Keep the answer index separate from the study explanation. Do not merge other exam years into this question bank silently.
2. **Sources first**: read the attached lecture PDF and cite real slide numbers. Explain its definitions, chart axes, curves, symbols and units. Do not replace a source chart with an unrelated generic illustration.
3. **Source identity**: a simplified SVG is explicitly labelled "redrawn from slide N"; do not describe it as the original exact image. Exact graph values should not be inferred from schematic curves.
4. **Incomplete labels**: never invent a definition for an abbreviation missing from the lecture. Q13 on the 2024 exam offers CF, PF, FF and MF, while slide 41 has Fine / Medium / Coarse grading. The source does not define PF; identify that limitation.
5. **Bilingual**: Arabic Cairo with `dir="rtl"`; English with `dir="ltr"`; keep the two explanations separate and readable. Never reverse English maths or question text through RTL inheritance.
6. **Visual explanations**: use a suitable slide-derived illustration, plot, flowchart, actual numerical table, or comparison matrix. Select by the *question's concept*, not its general subject label.
7. **Mathematical quality**: use stacked fractions, normal superscripts and subscripts, responsive wrapping, and a Symbols / الرموز table defining all variables in Arabic and English and their units. Use MathML or accessible HTML where supported; never show ambiguous plain-text division.
8. **Learning before testing**: explanation → visual/table → formula and symbols → original question → self-selected answer → detailed feedback on all options. Avoid giving an explicit answer-key badge before the learner makes a selection.
9. **Exam mode**: do not reveal answers before submission. Keep 30-minute timing for the CES251s model and 0.5 mark per question, storing progress in localStorage.
10. **Feedback**: after the final review question and after exam submission, ask whether students want the rest of the year's materials and free access. Do not claim feedback collection worked unless the external form is accessible.
11. **Responsive**: verify 360px, 390px, tablet and desktop; respect reduced motion; maintain tap targets, focus states, and sufficiently large mathematical glyphs.
12. **Do not break live sites**: preview/validate in the dedicated materials repository and update the Pages-backed mirror only after checks. Never change TIQAN or NATIGATAK workers to serve a study page.

## Content record
`exam-data` JSON includes:
- `questions[].q`: original MCQ text (English).
- `questions[].o`: the unchanged array of four original choices.
- `questions[].a`: correct choice's zero-based index, sourced from the reviewed answer key.
- `questions[].topic` and `questions[].unit`: lesson topic and course section.
- `questions[].slide`: citation to lecture slide.
- `questions[].en` / `questions[].ar`: plain-English and clear Egyptian-Arabic explanations.
- `questions[].key`: high-yield concepts.
- `questions[].formula`: original supporting formula, if present.
- `questions[].why`: reasons for all four answer choices.

## Reusable rendering helpers
The current standalone HTML app includes:
- `topicViz(index)`: concept-specific diagram and graph.
- `lessonTable(title, headings, rows, note, focus)`: responsive accessible table component.
- `specialNotes(index)`: factual source-derived tables matched to the question.
- `lectureNote(q,index)`: source-slide provenance.
- `mathFor(q,index)` / `formulaSymbols(index)`: consistently formatted equations and bilingual symbol-unit legends.
- `bulkingViz()`: Q13 slide-41-based moisture-versus-volume graph.
- `packingViz()`: Q1 slide-33-based grading comparison.

For a **new subject**, create a separate folder (e.g., `ces262/`) and use the same structure/style, a new data set, its own slide references and visual registry. Do not reuse CES251s-specific assumptions or figures.

## Verified source touchpoints for CES251s
- Aggregate slides 33 (packing), 35–36 (OD/SSD/moisture), 40 (dry/damp/wet), 41 (bulking curves), 44 (clay fines), 52 (graded/single-size), 53 (CP/MP/FP), 54 (FM), 62 (ASR prevention).
- Cement slides 5 (clinker manufacturing), 11–12 (XRD/Bogue), 13 (alkalis), 14 (insoluble residue), 20 (C₃S strength), 22–25 (gypsum/ettringite/DEF), 28–33 (gypsum/heat), 46–48 (soundness/free lime).

## Deployment
The study source stays in `MaxHeadroom1/nategah`. Its GitHub Pages site is not yet enabled. The current working GitHub Pages copy is under `MaxHeadroom1/athadmoadlah/ces251midterm/`. Do not assume canonical source and published copy are automatically synchronized.
