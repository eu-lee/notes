
---
name: pdf-to-latex-lecture-notes
description: Convert lecture-note PDFs, including diagrams, into clean LaTeX following this repository's formatting conventions.
---

# PDF to LaTeX Lecture Notes

## Objective

Convert lecture-note PDFs into accurate, clean, editable LaTeX.

Preserve mathematical content, explanations, diagrams, and document structure. The goal is faithful transcription, not summarization or rewriting.

## Reference Material

Before converting:

1. Read the formatting reference document provided in `./samples`
2. Inspect `lecturestyle.sty` for available environments and macros.
3. Follow the formatting conventions demonstrated by existing `.tex` files.

Treat these files as the source of truth for formatting.

## Conversion Rules

### 1. Mathematical Diagrams

All diagrams must be recreated using TikZ:

\begin{tikzpicture}
...
\end{tikzpicture}

- Preserve graph structure, edges, labels, and mathematical relationships.
- Prefer clean, symmetrical layouts with no overlapping edges.
- Do not use screenshots or raster images in place of diagrams.
- Keep diagrams readable and consistent in size.

### 2. Mathematical Environments

Use the corresponding LaTeX environments for:

- `theorem`
- `lemma`
- `corollary`
- `proposition`
- `definition`
- `example`
- `exercise`
- `remark`
- `proof`

For example:

\begin{theorem}{Handshaking Lemma}
...
\end{theorem}

Never manually format these headings.

All mathematical statements are unnumbered.

### 3. Lists

Use `itemize` for bulleted lists and `enumerate` for numbered lists.

\begin{itemize}
    \item First item
    \item Second item
\end{itemize}

Do not manually insert bullet characters.

### 4. Important Terminology

Use `\textit{}` to emphasize key terms and terminology being defined.

Do not use bold text for defined terms unless the reference document specifically requires it.

### 5. Mathematical Expressions

Use inline math `$...$` for short expressions.

For inline summations or large fractions, use `\displaystyle`:

$\displaystyle\sum_{i=1}^{n} i$

For expressions that are long or disrupt line spacing, use display math:

\[
\sum_{i=1}^{n} i = \frac{n(n+1)}{2}
\]

Use `align*` for multi-line derivations.

### 6. Document Structure

- Use `\section`, `\subsection`, and `\subsubsection` for headings.
- Preserve the logical structure of the source notes.
- Use existing commands and packages from `lecturestyle.sty`.
- Avoid unnecessary formatting commands.
- Make sure to point out if there is any factually incorrect / ambiguous information you would like the user to clarify.

- Try not to dump figures into the main file. It is preferred to have a main document, subsectioned accordingly, with diagrams stored separately.
## Workflow

1. Inspect the original PDF page visually.
2. Identify headings, paragraphs, mathematical statements, equations, lists, and diagrams.
3. Transcribe the content faithfully into LaTeX.
4. Recreate diagrams using TikZ.
5. Apply the repository's formatting conventions.
6. Compile the LaTeX.
7. Compare the rendered output against the original PDF and correct errors.

## Accuracy Requirements

- Never invent or silently omit mathematical content.
- Preserve notation, indices, signs, and equation steps.
- Do not simplify or rewrite proofs unless explicitly requested.
- Mark genuinely ambiguous handwritten content with `% TODO: verify`.
- Ensure all generated LaTeX compiles successfully whenever compilation is available.
