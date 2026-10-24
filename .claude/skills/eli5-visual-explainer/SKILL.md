---
name: eli5-visual-explainer
description: Creates a simple visual explanation with a strong central diagram, few words, progressive disclosure, and an optional technical layer. Use when the user asks for a visual explanation, simple causal diagram, self-contained HTML explainer, or an at-a-glance explanation of a process, tradeoff, incident, failure, architecture, algorithm, or abstract idea.
metadata:
  version: 1.0.0
---

# ELI5 Visual Explainer

Teach with pictures and spatial relationships. Text supports the visual instead of carrying the lesson.

## Core instruction

Find the simplest truthful picture that helps an intelligent adult understand the central idea quickly.

Do not make the explanation childish. Reduce unnecessary complexity while preserving the cause, sequence, tradeoff, or relationship that makes the concept true.

## Workflow

### 1. Ground the explanation

Inspect the relevant sources before explaining code, products, incidents, research, or evidence-dependent events.

Separate:

- confirmed facts;
- reasonable inferences;
- unknowns;
- details that may have changed and need current verification.

Do not guess from filenames, comments, headlines, or common patterns when better evidence is available.

### 2. Choose one visual mode

Select the format that best matches the concept:

- **Process:** a left-to-right or top-to-bottom sequence.
- **Cause and effect:** a chain showing what triggers what.
- **Input and output:** what enters, what changes, and what comes out.
- **Architecture:** a small number of boxes with clear relationships.
- **Tradeoff:** a direct side-by-side comparison.
- **Incident or failure:** normal state, triggering event, failure path, and recovery.
- **Algorithm:** input, repeated decision or transformation, and output.
- **Abstract idea:** a concrete analogy followed by an explicit mapping and its limits.
- **Before and after:** the important difference between two states.

Use one primary visual mode. Add a second only when it explains a different necessary layer.

### 3. Find the simplest truthful picture

Show the important path before supporting systems.

Ask:

- What is the one relationship the learner must see?
- Which details can wait?
- What would make the visual misleading if removed?
- Where does uncertainty need to be visible?

One major idea belongs in each section.

### 4. Build the visual first

Use diagrams, arrows, sequence, scale, position, grouping, contrast, before and after, cause and effect, input and output, or a physical analogy.

Add only the words needed to remove ambiguity.

Keep labels short. Make direction obvious. Avoid decorative elements that compete with the lesson.

### 5. Reveal depth progressively

When relevant, reveal information in this order:

1. The big idea.
2. The important pieces.
3. How they interact.
4. Why the interaction matters.
5. What can go wrong.
6. Where the analogy or simplification stops matching.
7. An optional technical layer.

Do not show every layer at once.

### 6. Create a viewable result

Use the output format the user requested or the simplest format available:

- an in-conversation diagram;
- an annotated image;
- a single-page visual;
- a short slide sequence;
- a self-contained HTML explainer.

For standalone HTML, keep the result portable and self-contained unless external assets are necessary. Make the first view understandable before interaction.

Use motion or interaction only when it teaches sequence, causality, comparison, or hidden detail.

### 7. Validate

Check that:

- the central idea is clear in the first view;
- arrows and sequence cannot be misread;
- text is readable at ordinary viewing size;
- the visual works on narrow and wide screens when relevant;
- color is not the only carrier of meaning;
- reduced-motion preferences are respected;
- uncertainty and analogy limits are visible;
- technical simplification remains truthful;
- the delivered result opens and renders correctly.

## Nonnegotiable behavior

- Assume no topic-specific knowledge, but write for an intelligent adult.
- Explain the simple idea before naming the technical term.
- Keep cause, sequence, and direction visually obvious.
- Do not create a giant architecture map, dense dashboard, or wall of cards.
- Do not use complexity as decoration.
- Do not invent evidence or imply that an untested workflow has been verified.
- Mark important uncertainty directly in the visual.
- State where an analogy stops matching.
- Preserve accessibility and readability.

## Default output shape

Use this structure when it fits:

1. **One-sentence setup**
2. **Central visual**
3. **Short mapping or explanation**
4. **Where the simplification breaks**
5. **Why it matters**
6. **Optional technical layer**
7. **One-sentence mental model**

## Completion

The explainer is complete when the first view communicates the central idea, the visual carries more teaching weight than the prose, the direction and relationships are unambiguous, the simplification remains truthful, the result is viewable, and the relevant accessibility and rendering checks pass.
