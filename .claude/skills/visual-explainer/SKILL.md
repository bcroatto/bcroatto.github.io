---
name: visual-explainer
description: Builds a visual explanation around one central diagram, with few words and depth revealed in layers. Use when the user explicitly asks to see something rather than read it — "visual explanation", "diagram this", "show me how X works", "help me picture", "ELI5 with a picture", "one-page explainer" — for a process, tradeoff, incident, architecture, algorithm, or abstract idea. Do not use for ordinary "explain X" questions that a few sentences answer well.
metadata:
  version: 2.0.0
---

# Visual Explainer

Teach with pictures and spatial relationships. Text supports the visual; it does not carry the lesson.

## Core instruction

Find the **simplest truthful picture** that helps an intelligent adult grasp the central idea quickly.

Simple is not childish. Cut complexity that doesn't matter; keep the cause, sequence, tradeoff, or relationship that makes the idea true.

## Workflow

### 1. Ground it

Before explaining code, products, incidents, research, or anything evidence-dependent, inspect the actual sources. Sort what you find into:

- **confirmed** — seen in the source;
- **inferred** — reasonable, but not verified;
- **unknown** — or may have changed since the source was written.

Don't guess from filenames, comments, headlines, or common patterns when better evidence is available. Pure concepts (e.g. "what is recursion") can skip this step.

### 2. Pick the one relationship and one visual mode

Answer three questions:

- What is the **one relationship** the learner must see?
- What would make the picture **misleading** if removed?
- Where must **uncertainty** be visible?

Then pick one primary mode:

| Mode | Shape |
|---|---|
| Process | left→right or top→bottom sequence |
| Cause and effect | chain of what triggers what |
| Input / output | what enters, what changes, what leaves |
| Architecture | 3–6 boxes, clear relationships |
| Tradeoff | direct side-by-side |
| Incident | normal → trigger → failure path → recovery |
| Algorithm | input → repeated decision/transform → output |
| Abstract idea | concrete analogy + explicit mapping + its limits |
| Before / after | the one difference that matters |

Add a second mode only if it explains a different, necessary layer.

### 3. Checkpoint (optional, recommended for non-trivial topics)

Before building, state in two lines: the central relationship and the chosen mode. Ask the user to confirm or redirect. A wrong central idea makes everything after it worthless; this check costs ten seconds. Skip it when the user asked for speed or the topic is unambiguous.

### 4. Build the visual first, then the words

Use position, arrows, grouping, scale, contrast, and sequence. Add only the words needed to remove ambiguity.

Hard limits for the first view:

- labels ≤ 4 words;
- ≤ 120 words of prose;
- ≤ 7 nodes in the central diagram;
- body text ≥ 16px, labels ≥ 14px;
- direction of every arrow obvious without reading the caption.

No decoration that competes with the lesson. No giant architecture maps, dense dashboards, or walls of cards.

### 5. Structure and progressive depth

Use this order. The first three are the first view; the rest sit below or behind a disclosure, revealed one layer at a time.

1. **Setup** — one sentence.
2. **Central visual.**
3. **Mapping** — short: what each piece is and how they interact.
4. **Why it matters.**
5. **What can go wrong.**
6. **Where the simplification breaks** — always present when an analogy or simplification is used. Name the exact point it stops matching.
7. **Technical layer** (optional) — introduce the real terms here, after the simple idea is established.
8. **Mental model** — one sentence to take away.

### 6. Output format

Default, unless the user asks otherwise:

- **Self-contained HTML with inline SVG** — single file, no external assets unless necessary. Must be understandable before any interaction.
- **Mermaid in chat** — when the answer stays in conversation and a file would be overkill.

Use motion or interaction only when it teaches sequence, causality, comparison, or hidden detail. Respect `prefers-reduced-motion`.

### 7. Validate — by looking, not by assuming

For HTML output, render it and take screenshots at ~390px and ~1280px wide (Playwright is usually available: `require('playwright')`, `chromium.launch()`). Look at them, then check:

- [ ] central idea is clear from the first view alone;
- [ ] arrows and sequence cannot be misread;
- [ ] text readable, no overflow or horizontal scroll on narrow screens;
- [ ] color is never the only carrier of meaning (use labels, shape, or pattern too);
- [ ] reduced-motion respected;
- [ ] uncertainty and analogy limits visible in the page, not just the chat;
- [ ] technical simplification still true.

If you could not render it, say so explicitly. Never imply a check ran when it didn't.

## Example

> **Request:** "Show me how DNS works."
>
> - **Relationship:** a name gets turned into an address by asking a chain of servers, and answers are remembered.
> - **Mode:** cause and effect (4 nodes: browser → resolver → authoritative server → IP back to browser), with a small cache marker on the resolver.
> - **Analogy:** asking a reception desk for someone's room number.
> - **Where it breaks:** a receptionist knows everyone; a resolver usually doesn't and has to ask others — and its remembered answers can be stale (TTL).
> - **Mental model:** DNS is a phone book that's split across many offices, with everyone keeping sticky notes.

## Done when

The first view communicates the central idea, the visual carries more weight than the prose, direction is unambiguous, the simplification is still true and its limits are stated, and the result has been rendered and checked — or you've said plainly that it wasn't.
